# ❓ Q&A: Trees & Ensembles (Week 6)

Questions and answers collected during study.

---

### Q: How does XGBoost handle overfitting?

**Context**: Using XGBoost on a Kaggle competition, model was overfitting badly.

**Answer**: 
XGBoost has multiple regularization mechanisms:
1. **max_depth**: Limits tree depth (most impactful)
2. **min_child_weight**: Minimum samples per leaf (prevents learning noise)
3. **lambda (L2 reg)**: Penalizes large leaf values
4. **alpha (L1 reg)**: Sparsity on leaf values
5. **subsample**: Only use fraction of data per tree (like dropout for trees)
6. **colsample_bytree**: Only use fraction of features per tree
7. **learning_rate (eta)**: Shrinks each tree's contribution (slower = more trees needed but better generalization)
8. **early_stopping_rounds**: Stop training when validation metric stops improving

Practical tuning order:
1. Set learning_rate=0.1, n_estimators=1000, early_stopping=50
2. Tune max_depth (3–7) and min_child_weight
3. Tune subsample and colsample_bytree (0.6–0.9)
4. Reduce learning_rate to 0.01–0.05, increase n_estimators

**Key Insight**: XGBoost's strength isn't just accuracy — it's that regularization is built into the algorithm's objective function (not just post-hoc pruning).

**Tags**: `#xgboost` `#regularization` `#overfitting` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
