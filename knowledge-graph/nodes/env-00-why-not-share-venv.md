---
id: env-00-why-not-share-venv
title: Why each person builds their own .venv (instead of sharing one)
kind: node
concepts: [venv, dependencies, git, portability]
entry_point: true
anchors:
  - text: "compiled C/Fortran code"
    fork: q-0001-what-is-compiled-code
  - text: "the recipe, not the cooked meal"
    fork: q-0002-recipe-not-meal
related: [env-01-version-in-import, env-02-symlink-mechanism]
verified_with: "du -sh .venv  # 201M ;  ls -la .venv/bin/python  # symlink"
source_session: 2026-10-20
---

# Why each person builds their own `.venv`

## Context

When you set up this project, a folder called `.venv` appeared. A **venv**
("virtual environment") is a project's *private toolbox* of libraries, kept
separate from every other project's.

Measured on a real machine, this `.venv` was **201 MB** just for numpy +
matplotlib + sklearn, and its `python` is a *symlink* (a pointer) back to a
Python already installed on the machine — ? **"compiled C/Fortran code"** is why
that 201 MB can't simply be shared.

## The question

"I already installed 201 MB. Why should the next person redo it? Why not commit
`.venv/` to git so everyone gets it for free?"

## Hooks — try to answer before reading on

- If numpy contains code *built for one specific operating system and CPU*, what
  happens when someone on a different OS runs your copy?
- The venv's `python` is a pointer to `/opt/homebrew/...` on the original machine.
  Does that path exist on anyone else's computer?

## Answer — three reasons sharing `.venv` breaks

**Reason A — it's platform-specific machine code, not portable text.**
numpy isn't pure Python; it ships ? **"compiled C/Fortran code"** built for one
OS + CPU (here: macOS + Apple Silicon/arm64). A follower on Windows, Linux, or an
Intel Mac would hit an architecture-mismatch error loading those `.so` files.

**Reason B — the symlink is absolute and personal.**
The venv's python points at a path that only exists on the original machine. On a
follower's computer that pointer dangles and nothing runs.

**Reason C — size and churn.**
201 MB of binaries in git history, re-downloaded on every clone, re-committed on
every package bump. Git is built for diffing *text*, not storing toolchains.

## What we commit instead

Not the 201 MB — a tiny **text file** listing *what to install* (`requirements.txt`).
That is ? **"the recipe, not the cooked meal"**: the recipe is a few lines of text
that rebuilds the same environment on any machine; the meal is machine-specific
binaries that don't travel.

## Next

- Explore: **q-0001** — what does "compiled code" actually mean?
- Explore: **q-0002** — the "recipe vs cooked meal" idea in full.
- Next concept: **env-01** — "why not just put the version in the import?"
- Next concept: **env-02** — how the venv works when python is "just a symlink".
