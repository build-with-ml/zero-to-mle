# ❓ Q&A: Model Evaluation (Week 7)

Questions and answers collected during study.

---

### Q: My fraud detection model has 99.9% accuracy. Is it good?

**Context**: Classic interview trap question — understanding class imbalance.

**Answer**: 
Almost certainly not. If only 0.1% of transactions are fraudulent, a model that predicts "not fraud" for EVERYTHING gets 99.9% accuracy.

What to look at instead:
- **Precision**: Of predicted frauds, how many are real? (false alarm rate)
- **Recall**: Of actual frauds, how many did we catch? (miss rate)
- **PR-AUC**: Better than ROC-AUC for imbalanced data
- **Confusion matrix**: See actual numbers (100 missed frauds > 10K false alarms?)

The right metric depends on business cost:
- If missing fraud costs $10K but false alarm costs $1 → optimize recall
- If false alarms annoy customers → balance precision and recall
- Use **cost-sensitive evaluation**: assign different costs to FP vs FN

**Key Insight**: Accuracy is misleading on imbalanced data. Always ask "what's the class distribution?" and "what's the cost of each error type?"

**Tags**: `#evaluation` `#imbalanced-data` `#precision-recall` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
