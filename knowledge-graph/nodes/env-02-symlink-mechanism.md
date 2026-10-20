---
id: env-02-symlink-mechanism
title: How a venv works when python is "just a symlink"
kind: node
concepts: [venv, sys-path, imports, pyvenv-cfg]
entry_point: true
anchors:
  - text: "just a symlink"
    fork: q-0005-symlink-detects-deps
  - text: "pyvenv.cfg"
    fork: q-0005-symlink-detects-deps
related: [env-00-why-not-share-venv, env-01-version-in-import]
verified_with: "readlink -f .venv/bin/python; .venv/bin/python -c 'import sys; print(sys.prefix)'; cat .venv/pyvenv.cfg"
source_session: 2026-10-20
---

# How a venv works when python is "just a symlink"

## Context

The apparent paradox: `.venv/bin/python` resolves to the *identical binary file*
as the system Python (proven with `readlink -f` — byte-for-byte the same program),
yet one finds numpy and the other doesn't. If it's ? **"just a symlink"** to the
same program, how can the behavior differ?

## Hooks — try to answer before reading on

- Same binary, different result. The difference can't be in the program itself —
  so what changed?
- When you type `import numpy`, who tells Python *which folder* to load it from?
- A symlink stores nothing. So where does the "I am a venv" information live?

## Answer — Python computes its library path from the LAUNCH path

When Python starts it does not have a hardcoded library list; it **computes** one,
starting from the path you launched it by (`sys.executable`), not from where the
real binary lives. So launching via `.venv/bin/python`:

1. Python records that launch path as `sys.executable`.
2. It looks in the same folder for a file named ? **"pyvenv.cfg"**.
3. Finding one means "I'm in a virtual environment."
4. That sets `sys.prefix` to the venv and makes the venv's `site-packages` the
   import location (this is `sys.path`).

**Measured difference (same binary):**

| | sys.prefix | site-packages searched |
|---|---|---|
| venv python | the `.venv` folder | `.venv/.../site-packages` (has numpy) |
| system python | the system prefix | system site-packages (no numpy) |

`import numpy` walks `sys.path` and loads the first `numpy/` it finds. Only the
venv's path contains it.

## Does Python "detect dependencies"? No.

The interpreter never analyzes dependencies. The **installer** (`pip`/`uv`)
resolves versions and places files into `site-packages` *before* runtime. At
runtime Python only searches `sys.path` and loads what's there. Installer resolves
and places; interpreter searches and loads — two jobs, two tools.

## Next

- Explore: **q-0005** — the full mechanism (symlink → pyvenv.cfg → sys.prefix →
  sys.path), with the diagram and the "installer vs interpreter" split.
- Back to: **env-00** — why the built `.venv` isn't shared.
- Next on the path: set up the environment yourself (SETUP), then Week 1 Exercise 1.
