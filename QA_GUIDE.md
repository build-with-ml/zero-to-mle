# ❓ Q&A System — How It Works

## Overview

Every phase folder contains `qa-*.md` files alongside the weekly plan. These files grow over time as you (and the community) learn.

```
weeks/phase-1-foundations/
├── README.md                  ← Weekly plan (what to learn)
├── qa-linear-algebra.md       ← Q&A collected during Week 1
├── qa-probability.md          ← Q&A collected during Week 2
└── qa-optimization.md         ← Q&A collected during Week 3

weeks/phase-3-deep-learning/
├── README.md                  ← Weekly plan
└── qa-transformers.md         ← Q&A collected during Weeks 14–15
```

**Why here?** Co-location. When studying Phase 3, your plan and Q&A are in the same folder. No jumping between directories.

---

## How to Add Q&A

### During a Study Session

1. You're studying `weeks/phase-X/README.md`
2. You ask a question (to AI, Google, a book, or yourself)
3. At the end of your session, add the Q&A to the matching `qa-*.md` file

### With an AI Assistant (Kiro, Copilot, etc.)

After studying, tell your AI:

> "Summarize the key questions I asked today. Format each one like this:
> ```
> ### Q: [question]
> **Context**: [when it came up]
> **Answer**: [explanation]
> **Key Insight**: [one-line aha moment]
> **Tags**: `#tag1` `#tag2`
> ```
> Add them to `weeks/phase-X/qa-[topic].md`"

The AI will format and file them for you.

### Without AI (Manual)

Just open the relevant `qa-*.md` file and append your entry at the bottom (before the comment block).

---

## Q&A Format

```markdown
### Q: [Your question here]

**Context**: [When/why this question came up]

**Answer**: 
[Clear, concise answer — include code, tables, or diagrams if helpful]

**Key Insight**: [One-line takeaway — the "aha!" moment]

**Tags**: `#topic` `#subtopic` `#interview-relevant`
```

---

## What Makes a Good Q&A Entry?

✅ **Do add:**
- Questions that confused you (they'll confuse others too)
- "Why" questions (understanding > memorization)
- Misconceptions you had that were corrected
- Connections between topics ("How does X relate to Y?")
- Questions from mock interviews
- Tricky edge cases or gotchas

❌ **Don't add:**
- Questions with one-word answers (too simple for a Q&A entry)
- Highly specific debugging issues ("Why did my pip install fail?")
- Opinions without substance ("Is PyTorch better than TensorFlow?")

---

## Contributing Q&A Back to the Main Repo

Your Q&A helps everyone:

1. Collect Q&A in your fork's `weeks/phase-X/qa-*.md` files
2. When you have 3–5 good entries, open a PR to the upstream repo
3. Maintainers review for accuracy and clarity
4. Once merged, everyone pulling upstream gets your contributions

### PR Title Format
```
qa(phase-X): Add N questions on [topic]
```

### Example
```
qa(phase-3): Add 4 questions on transformer attention and KV-cache
```

---

## Using Q&A for Self-Testing

The Q&A files double as **flashcard decks**:

1. Open a `qa-*.md` file
2. Read only the `### Q:` line
3. Try to answer from memory
4. Check against the written answer
5. If you got it wrong, mark it for review

Questions tagged `#interview-relevant` are the most important to memorize.

---

## Current Q&A Files

| Phase | File | Topic |
|---|---|---|
| Phase 1 | `weeks/phase-1-foundations/qa-linear-algebra.md` | Vectors, matrices, eigen, SVD |
| Phase 1 | `weeks/phase-1-foundations/qa-probability.md` | Bayes, distributions, A/B tests |
| Phase 1 | `weeks/phase-1-foundations/qa-optimization.md` | Gradient descent, Adam, SGD |
| Phase 2 | `weeks/phase-2-core-ml/qa-trees-and-ensembles.md` | XGBoost, random forests |
| Phase 2 | `weeks/phase-2-core-ml/qa-evaluation.md` | Metrics, imbalanced data |
| Phase 3 | `weeks/phase-3-deep-learning/qa-transformers.md` | Attention, KV-cache, architectures |
| Phase 4 | `weeks/phase-4-llms/qa-rag.md` | RAG failure modes, evaluation |
| Phase 4 | `weeks/phase-4-llms/qa-fine-tuning.md` | When to fine-tune vs prompt vs RAG |
| Phase 5 | `weeks/phase-5-mlops/qa-serving.md` | Batch vs real-time, serving patterns |
| Phase 6 | `weeks/phase-6-interview/qa-system-design.md` | Cold start, design patterns |
