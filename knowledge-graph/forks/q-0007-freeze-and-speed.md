---
id: q-0007-freeze-and-speed
title: What is "freezing versions", and how is uv actually faster?
kind: fork
concepts: [dependencies, requirements, uv, pip, reproducibility]
entry_point: false
parent_anchor:
  node: env-01-version-in-import
  text: "The demand is speed"
question: "how is it speed, compare to others; and 'freeze versions' is not intuitive — justify your statement"
related: [q-0006-what-is-rust, q-0002-recipe-not-meal]
verified_with: "timed fresh no-cache install of numpy+matplotlib+sklearn: uv 3.06s vs pip 17.19s (5.6x); pip freeze prints numpy==2.0.2 etc."
source_session: 2026-10-20
---

# "Freezing versions", and the measured speed difference

## Context

Two vague phrases from earlier — "freeze versions" and "faster" — both needed to be
defined and proven.

## "Freeze versions" — the intuitive meaning

`pip install numpy` doesn't say *which* version — it grabs whatever is newest that
day. So you get numpy 2.0.2 today; a follower in 3 months gets 2.6; your code breaks
for them. **Freezing** = writing down the exact versions so everyone installs the
same ones.

`pip freeze` prints that pinned list (verified output):

```
numpy==2.0.2
matplotlib==3.9.4
joblib==1.5.3
```

Saved as `requirements.txt`, anyone running `pip install -r requirements.txt` gets
*your* exact versions. Recipe analogy: "add flour" → everyone's cake differs;
"add 200g flour" → everyone gets your cake. Forgetting to freeze = publishing the
vague recipe.

## "Faster" — justified with a measurement

Same 3 packages (numpy + matplotlib + sklearn), fresh, no cache, timed on a real
machine:

| Tool | Time | |
|---|---|---|
| pip (written in Python) | 17.19 s | |
| uv (written in Rust) | 3.06 s | **~5.6× faster** |

Not a blog claim — a reproducible measurement. On a 50+ package project the gap
widens because uv also downloads in parallel and resolves with a faster algorithm.
(See **q-0006** for *why* Rust makes the tool fast.)

## Next

- Related: **q-0006** — what Rust is.
- Related: **q-0002** — the recipe file that holds these frozen versions.
