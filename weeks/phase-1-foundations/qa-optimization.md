# ❓ Q&A: Calculus & Optimization (Week 3)

Questions and answers collected during study.

---

### Q: Why does Adam work better than SGD in practice?

**Context**: Implementing optimizers from scratch, comparing convergence speed.

**Answer**: 
Adam combines two ideas:
1. **Momentum** (first moment): Keeps a running average of past gradients → smooths out noise, escapes local minima
2. **RMSProp** (second moment): Keeps a running average of squared gradients → adapts learning rate per-parameter

This means:
- Parameters with small gradients get larger effective learning rate (helps sparse features)
- Parameters with large gradients get smaller effective learning rate (prevents explosion)
- Momentum helps traverse flat regions and escape saddle points

When SGD is actually better:
- With proper tuning, SGD + momentum often generalizes better than Adam (especially in vision)
- Adam can converge to sharper minima → sometimes worse test performance
- Solution: AdamW (decoupled weight decay) fixes most of Adam's generalization issues

**Key Insight**: Adam converges faster, SGD (with proper tuning) sometimes generalizes better. In 2026, AdamW is the default for most tasks, especially LLM training.

**Tags**: `#optimization` `#adam` `#sgd` `#training` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
