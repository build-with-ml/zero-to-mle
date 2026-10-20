# Knowledge Graph

This folder is the source of truth for the **discovery-based learning graph** — the
content a future website renders as an explorable map of concepts, questions, and
answers.

It is built from real learning sessions. Every time a learner quotes a specific
sentence and asks about it, that quote becomes a **fork**: a `?` marker on that exact
text that branches into a sub-explanation, then returns.

## The two structural rules (every node and fork follows them)

1. **Inline `?` anchors.** Inside the prose, specific statements or terms are marked
   so a reader can "explore more" without leaving the main thread. In the files these
   are recorded in the `anchors:` frontmatter (exact quoted text → the fork it opens).
2. **"Next" block at the end.** Every node/fork ends with follow-up questions and the
   next step on the learning path, so a reader always knows where they can go.

## The pieces

| Folder / file | What it holds |
|---|---|
| `nodes/` | One file per concept/lesson. A node is a place you can *be*. |
| `forks/` | One file per quoted-question fork. A fork is an *exploration* off an anchor. |
| `graph.json` | The edges: which anchor (in which node) opens which fork, plus concept cross-links. The website loads this to draw the map. |

## Node & fork frontmatter (schema)

```yaml
---
id: env-02-symlink-mechanism      # stable unique id; graph identity
title: How a venv works when python is "just a symlink"
kind: node                         # node | fork
concepts: [venv, sys-path, imports]# tags → cross-links AND entry points
entry_point: true                  # can a learner START here? (e.g. "just teach me venv")
anchors:                           # inline ? markers: quoted text → fork it opens
  - text: "just a symlink"
    fork: q-0005-symlink-detects-deps
related: [env-00-why-not-share-venv, env-01-version-in-import]  # lateral concept links
verified_with: "readlink -f .venv/bin/python; cat .venv/pyvenv.cfg"  # evidence (justify-every-claim rule)
source_session: 2026-10-20         # which session this came from (date only, no identity)
---
```

A **fork** adds two fields:

```yaml
kind: fork
parent_anchor:                     # where this fork was spawned FROM
  node: env-02-symlink-mechanism
  text: "just a symlink"
question: "if its just symlink, how its able to detect dependencies"  # learner's words, verbatim
```

## Navigation: where does "Back" go?

A node can be reached from **many** places (that is what makes this a graph, not a
tree). So **"back" is NOT stored in the file** — there is no single parent to hardcode.

- The **website** remembers the visitor's trail (a stack of how they got here).
  **Back = the immediate parent in *that* visitor's trail.**
- A node file only stores *stable* links (`related`, `concepts`, `anchors` → forks).
- There is **always** a "Home / root" jump as well, so a learner deep in a branch can
  escape in one click regardless of trail.

Rule of thumb: **graph edges are fixed and stored; the breadcrumb is per-visit and
computed.**

## Entry points

Any file with `entry_point: true` is a valid place to *start*. That is how the same
content serves two audiences:

- An MLE learner starts at Week 1 and walks the path.
- Someone who only wants "what is a venv" enters directly at `env-00` and explores
  the environment cluster — same files, a different door in.

## Paths in examples

Examples use `~` or `zero-to-mle` as the project root — never an absolute machine
path — so a command copy-pastes on any computer.
