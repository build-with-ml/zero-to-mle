---
id: q-0003-version-in-import-why-not
title: Why not put the version in the import? (full answer + cross-language)
kind: fork
concepts: [imports, versioning, cross-language, dependencies]
entry_point: false
parent_anchor:
  node: env-01-version-in-import
  text: "one version of each package per environment"
question: "why not in imports they put version and in install folder, so that we dont care about this mapping, and people have to explicitly say in import"
related: [env-01-version-in-import]
verified_with: ".venv/bin/python -c \"import sys; print('numpy' in sys.modules)\"; ls site-packages (folder is 'numpy', version only in numpy-*.dist-info)"
source_session: 2026-10-20
---

# Why not put the version in the import?

## Context

The idea: `import numpy==2.5`, with each version in its own folder, so one Python
holds all versions. Why doesn't Python work this way?

## Hooks

- If scipy does `import numpy` internally, which numpy does it get? It never said `==`.
- Two versions loaded at once: A's numpy array handed to B's numpy 2.5 code — what breaks?
- A patch ships as 2.5.1. How many files with `==2.5` must you edit?

## Answer

**Verified fact:** Python caches modules by *name only* — the key is `"numpy"`, no
version in it. The on-disk folder is just `numpy/`; the version lives only in the
sibling `numpy-*.dist-info` metadata folder, which imports ignore.

- **The scipy problem:** `import numpy` resolves the *name* and returns the single
  numpy on the path. Versioned imports would force every transitive dependency to
  become version-aware too — a cascade through the whole ecosystem.
- **The killer (compiled types):** a numpy-1.26 array and a numpy-2.5 array are two
  incompatible C types in one process. Mixing them corrupts memory, not a clean
  error. Two compiled versions cannot safely coexist in one process.
- **The maintenance problem:** scattering `==2.5` across files makes a security
  patch a mass find-replace. Real tools centralize the version in ONE file.

## Global picture — the two camps

- **Python / Java:** one version per environment/classpath. Safe, small; needs
  isolation (venv).
- **Node / Go / Rust:** multiple versions coexist (nested `node_modules`,
  version-in-path `.../v2`). Flexible; pay in disk/complexity.

Your "version in the import" instinct is literally Go's design (`import ".../v2"`).
It's a real camp, not a naive idea — the tradeoff just moves; nobody gets it free.

## Next

- Back to: **env-01** — the summary table of all five languages.
- Related: **env-02** — how name-only resolution walks `sys.path` to find the one numpy.
