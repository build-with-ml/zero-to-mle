---
id: q-0005-symlink-detects-deps
title: If it's just a symlink, how does Python find the right dependencies?
kind: fork
concepts: [venv, sys-path, imports, pyvenv-cfg]
entry_point: false
parent_anchor:
  node: env-02-symlink-mechanism
  text: "just a symlink"
question: "if its just symlink, how its able to detect this, how python detects dependencies"
related: [env-02-symlink-mechanism, env-01-version-in-import]
verified_with: "readlink -f .venv/bin/python (same binary); sys.prefix differs; cat .venv/pyvenv.cfg; sys.executable = the venv path"
source_session: 2026-10-20
---

# If it's just a symlink, how does Python find the right libraries?

## Context

`.venv/bin/python` and the system python are the *same binary file* (proven with
`readlink -f`), yet only the venv one finds numpy.

## Hooks

- Same program, different behavior — what changed, if not the binary?
- Who tells Python which folder to import from?
- A symlink stores nothing — where does "I'm a venv" live?

## Answer — library path is COMPUTED from the launch path

Python computes its library folders at startup, beginning from the path you
launched it by (`sys.executable`), not the resolved binary. Launching via the venv
symlink:

1. `sys.executable` = the venv path (verified).
2. Python looks beside it for **`pyvenv.cfg`** (verified it exists).
3. Present → "I'm a venv" → set `sys.prefix` to the venv.
4. That makes the venv's `site-packages` the search path (`sys.path`).

`import numpy` walks `sys.path` and loads the first match. Only the venv's path has
numpy, so only the venv python finds it. `pyvenv.cfg` contents that drive it:
`home = <base python>` and `include-system-site-packages = false` (the isolation
switch).

```
run .venv/bin/python
  -> sys.executable = venv path
  -> pyvenv.cfg next to it?  YES -> sys.prefix = .venv -> site-packages = .venv's  -> numpy found
                             NO  -> system prefix       -> system site-packages     -> ModuleNotFoundError
```

## "Detect dependencies"? No.

The interpreter never analyzes dependencies. The installer (`pip`/`uv`) resolves and
places files into `site-packages` *before* runtime; Python only searches `sys.path`
and loads. Installer resolves + places; interpreter searches + loads.

## Next

- Back to: **env-02** — the node this forked from.
- Related: **env-01** — name-only resolution is why only one version can be on the path.
