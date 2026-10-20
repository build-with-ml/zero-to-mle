---
id: q-0004-library-full-forms-and-demand
title: Full forms of numpy/matplotlib/sklearn — and what each is demanded for
kind: fork
concepts: [numpy, matplotlib, sklearn, tooling]
entry_point: true
parent_anchor:
  node: env-00-why-not-share-venv
  text: "numpy + matplotlib + sklearn"
question: "what's full form, for all things mention full form at the start, and what is demand / give the most-used functions it's for reusing"
related: [env-00-why-not-share-venv]
verified_with: ".venv/bin/python -c 'import sklearn; print(sklearn.__version__)' + imported LinearRegression, KMeans, train_test_split, cosine_similarity, etc."
source_session: 2026-10-20
---

# Full forms, and what each library is demanded for

**Rule set here:** give the full form of every tool at first mention, and justify
"what it's for" with the actual reusable pieces — not just a role.

## Full forms

- **numpy** = "Numerical Python" — fast arrays and matrix math.
- **matplotlib** = "MATLAB plotting library" (MATLAB = "Matrix Laboratory"); its core
  module `pyplot` = "Python plot".
- **sklearn / scikit-learn** = "SciKit for learning"; a SciKit = "Scientific Kit" built
  on SciPy = "Scientific Python".
- **venv** = "virtual environment". **pip** = "Pip Installs Packages". **uv** = tool
  name (not an acronym).

## What each is demanded for

- **numpy** → fast math (compiled C, 10–100× faster than plain Python lists). Every ML
  library sits on it.
- **matplotlib** → *seeing* data/concepts (plot a curve, draw vectors + the angle).
- **sklearn** → ready-made, tested ML algorithms (+ an "answer key" to check our
  from-scratch code).

## sklearn — the actual functions you reuse (verified imports)

| Import | Does |
|---|---|
| `from sklearn.linear_model import LinearRegression, LogisticRegression` | predict a number / classify |
| `from sklearn.ensemble import RandomForestClassifier` | strong general classifier |
| `from sklearn.cluster import KMeans` | group unlabeled data |
| `from sklearn.metrics import accuracy_score, mean_squared_error` | score a model |
| `from sklearn.metrics.pairwise import cosine_similarity` | the Exercise-1 answer key |
| `from sklearn.preprocessing import StandardScaler` | rescale features |
| `from sklearn.model_selection import train_test_split` | split train/test (almost every script) |

Every model follows the same `.fit(X, y)` then `.predict(X)` pattern — that
consistency is why it's reused everywhere. In Phase 1 we *rewrite* the simple ones
from scratch, then import sklearn's as the answer key.

## Next

- Back to: **env-00** — these are the three libraries in the venv.
- Related: **q-0006** — "what is Rust" (why uv, the installer, is fast).
