---
id: env-01-version-in-import
title: Why not just put the version in the import?
kind: node
concepts: [venv, dependencies, imports, cross-language, versioning]
entry_point: true
anchors:
  - text: "one version of each package per environment"
    fork: q-0003-version-in-import-why-not
related: [env-00-why-not-share-venv, env-02-symlink-mechanism]
verified_with: "python -c \"import sys; print('numpy' in sys.modules)\"  # cache key is name-only, no version"
source_session: 2026-10-20
---

# Why not just put the version in the import?

## Context

A natural idea: store each version in its own folder (`numpy-1.26/`, `numpy-2.5/`)
and let the import say which one (`import numpy==2.5`). Then one shared Python
could hold every version and we'd never need isolation.

People *have* built exactly this — so why doesn't Python? The answer is a real
design choice, and ? **"one version of each package per environment"** is the side
Python picked.

## Hooks — try to answer before reading on

- If `numpy 2.5` itself imports `scipy`, and `scipy` does `import numpy` — how does
  scipy know *which* numpy it should see? It never wrote `==`.
- Library A (wants numpy 1.26) hands a numpy array to library B (wants numpy 2.5).
  What happens when B's code touches an object built by A's numpy?
- You pin `import numpy==2.5` in every file. A security patch ships as 2.5.1. How
  many files must you now hand-edit?

## Answer — why Python can't easily do per-import versions

Python caches imported modules **by name only** — the key is the string `"numpy"`,
with no version in it. Two *compiled* versions of numpy in one process would be two
incompatible C types; passing an object from one to the other corrupts memory.
Python chose safety: ? **"one version of each package per environment"**, which is
exactly what forces the venv-per-project model.

## The global picture — how OTHER languages decide

| Language | Strategy | Two versions in one app? | Cost |
|---|---|---|---|
| Python | one version per environment; isolate with venv | No | a venv per project |
| JavaScript/Node | nested `node_modules` — each library carries its own deps | Yes | huge disk use |
| Rust | multiple major versions can link; type namespaced by version | Yes (majors) | compiler complexity |
| Java | classpath: one version wins | Mostly no | "JAR hell" |
| Go | major version in the import path (`.../v2`) | Yes (majors) | version-in-path (your idea!) |

Two takeaways: your instinct *is* how Node and Go work — you reinvented a real,
shipping design. And nobody gets coexistence free; the cost just moves (Node pays
in giant `node_modules`, Python pays in needing a venv).

## Next

- Explore: **q-0003** — the full answer to "why not version-in-import", with the
  memory-corruption reason and the cross-language comparison.
- Next concept: **env-02** — how the venv actually finds the right libraries.
- Back to: **env-00** — why we don't just share the built `.venv`.
