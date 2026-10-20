---
id: q-0007-freeze-and-speed
title: What is "freezing versions", and when is uv actually faster than pip?
kind: fork
concepts: [dependencies, requirements, uv, pip, reproducibility]
entry_point: false
parent_anchor:
  node: env-01-version-in-import
  text: "The demand is speed"
question: "how is it speed, compare to others; and 'freeze versions' is not intuitive — justify your statement"
related: [q-0006-what-is-rust, q-0002-recipe-not-meal]
verified_with: "2 cases, caches purged. Loose names: uv 3.06s vs pip 17.19s (uv 5.6x, resolution-heavy). Pinned requirements.txt, 3 cold trials: uv ~2.9-3.6s vs pip ~1.6s (pip faster, little to resolve)."
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

## "Faster" — justified with a measurement (and where it's NOT faster)

The honest answer is: **it depends on whether there's resolution work to do.**
Two measurements on the same machine, both fresh with caches purged.

**Case 1 — loose names, resolution-heavy:** `install numpy matplotlib scikit-learn`
(no versions pinned, so the tool must figure out compatible versions):

| Tool | Time | |
|---|---|---|
| pip (written in Python) | 17.19 s | |
| uv (written in Rust) | 3.06 s | **~5.6× faster** |

**Case 2 — the pinned `requirements.txt` (this repo), 3 cold trials:**

| Tool | Trial 1 | Trial 2 | Trial 3 | |
|---|---|---|---|---|
| uv | 2.87 s | 3.18 s | 3.55 s | |
| pip | 1.62 s | 1.65 s | 1.68 s | **pip faster here** |

**Why the flip?** uv's big win is *dependency resolution* — choosing compatible
versions from loose names (Case 1, where pip spent ~15s deciding). When versions
are already pinned (Case 2), there's almost nothing to resolve: both just download
and install, and pip was actually quicker on this small pinned set.

**The honest takeaway:** uv shines on large, unpinned installs where resolution
dominates. For a tiny pre-pinned list the difference is small and can go either way.
Don't state "uv is always faster" — state *where* it's faster and show the number.
(See **q-0006** for *why* Rust makes resolution fast.)

## Next

- Related: **q-0006** — what Rust is.
- Related: **q-0002** — the recipe file that holds these frozen versions.
