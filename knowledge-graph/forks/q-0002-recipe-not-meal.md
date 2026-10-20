---
id: q-0002-recipe-not-meal
title: "The recipe, not the cooked meal" — what we actually commit
kind: fork
concepts: [dependencies, git, requirements, reproducibility]
entry_point: false
parent_anchor:
  node: env-00-why-not-share-venv
  text: "the recipe, not the cooked meal"
question: "(implied) if we don't commit .venv, what DO we commit so others can reproduce it?"
related: [env-00-why-not-share-venv]
source_session: 2026-10-20
---

# "The recipe, not the cooked meal"

## Context

We don't commit the 201 MB of installed packages. We commit a small text file that
*describes how to rebuild them*.

## Hooks

- If the meal (installed binaries) doesn't travel, what does?
- How does a follower turn the recipe back into a working environment?

## Answer

Each tool shares a small **text file** — the recipe — and rebuilds the environment
locally from it:

| Tool | Recipe file | Rebuild command |
|---|---|---|
| venv + pip | `requirements.txt` | `pip install -r requirements.txt` |
| uv | `pyproject.toml` + `uv.lock` | `uv sync` |
| conda | `environment.yml` | `conda env create -f environment.yml` |
| docker | `Dockerfile` | `docker build` |

The recipe is portable text that works on any OS; the "meal" (compiled binaries) is
machine-specific and stays local. This is also why `.venv/` is git-ignored.

## Next

- Back to: **env-00** — the three reasons the meal can't be shared.
- Related: **q-0007** — "freeze versions" is how the recipe pins exact versions.
