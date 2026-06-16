# Phase 2: Core Machine Learning (Weeks 5–10)

## Overview

Master classical ML algorithms — not just using sklearn, but understanding the internals. This phase covers what's tested most heavily in ML fundamentals rounds.

**Key principle**: Implement from scratch first, THEN use sklearn/XGBoost. Know the tradeoffs.

---

## Week 5: Linear Models & Regularization

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Andrew Ng ML Specialization — Course 1, Weeks 1–3 | 6 hrs |
| 📺 Video | StatQuest: Regularization, Ridge, Lasso | 2 hrs |
| 📖 Book | Géron "Hands-On ML" Ch. 4 | 2 hrs |

### What to Build
- Linear regression: OLS (closed-form) + gradient descent
- Ridge regression (L2) from scratch
- Lasso regression (L1) with coordinate descent
- Logistic regression from scratch
- Regularization path visualization (coefficients vs lambda)

### Interview Connection
- "When would you use L1 vs L2?" (Amazon, Meta) — L1 for feature selection, L2 for multicollinearity
- "Implement logistic regression" — common Amazon coding round

---

## Week 6: Trees & Ensembles

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | StatQuest: Decision Trees + Random Forest + XGBoost (full series) | 4 hrs |
| 📖 Book | Géron Ch. 6–7 | 3 hrs |
| 📖 Docs | XGBoost documentation | Reference |

### What to Build
- Decision tree from scratch (Gini + entropy split criteria)
- Tree visualization: animate splits on 2D data
- XGBoost on Kaggle tabular competition
- SHAP values: explain individual predictions
- Feature importance comparison (impurity vs permutation vs SHAP)

### Interview Connection
- "How does XGBoost handle overfitting?" (Amazon, Meta)
- "Explain gradient boosting" — top 3 most-asked ML algorithm question
- SHAP explanations → model interpretability (Amazon LP: Dive Deep)

---

## Week 7: Model Evaluation & Selection

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Book | Géron Ch. 2–3 | 2 hrs |
| 📺 Course | Kaggle Learn: Intermediate ML | 3 hrs |
| 📺 Video | StatQuest: ROC, AUC, Cross-Validation | 2 hrs |

### What to Build
- Precision-Recall threshold tuner (interactive)
- ROC curve comparison across models
- K-fold cross-validation from scratch
- Hyperparameter tuning comparison (Grid vs Random vs Bayesian)
- Calibration curves for probabilistic models

### Interview Connection
- "How would you evaluate this model?" — EVERY system design interview
- "Your model has 99% accuracy on fraud detection. Is it good?" — classic trap question
- "When would you optimize for recall over precision?" (Amazon, Meta)

---

## Week 8: Feature Engineering & Data

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Kaggle Learn: Feature Engineering | 3 hrs |
| 📖 Book | "Feature Engineering for ML" (Alice Zheng) | Reference |
| 📺 Course | Made With ML: Data section | 2 hrs |

### What to Build
- Take a messy dataset and show before/after feature engineering
- Encoding comparison: one-hot vs target vs embedding
- Missing data strategies comparison (imputation methods)
- Feature selection pipeline (filter + wrapper + embedded)
- Data leakage detector

### Interview Connection
- "What features would you use for X?" — Meta, Amazon system design
- "How do you prevent data leakage?" — fundamental ML judgment question
- Feature engineering is often where competitions are won/lost

---

## Week 9: Unsupervised Learning

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Book | Géron Ch. 8–9 | 3 hrs |
| 📺 Video | StatQuest: K-Means, PCA, t-SNE | 2 hrs |
| 📄 Paper | UMAP paper (McInnes 2018) | 1 hr |

### What to Build
- K-Means from scratch + convergence animation
- DBSCAN vs K-Means on non-spherical data
- PCA vs t-SNE vs UMAP comparison on same dataset
- Customer segmentation project (real business application)
- Anomaly detection with Isolation Forest

### Interview Connection
- "How would you find customer segments?" (Amazon)
- "How does t-SNE differ from PCA?" (Google, Meta)
- Anomaly detection → fraud, abuse detection system design

---

## Week 10: End-to-End Project #1 ⭐

### The Project
Build a **complete ML pipeline** on a real dataset:

1. **EDA**: Understand the data, find patterns, identify issues
2. **Feature Engineering**: Create meaningful features, handle messy data
3. **Model Comparison**: Linear → Tree → Ensemble → best model
4. **Hyperparameter Tuning**: Systematic optimization
5. **Evaluation**: Multiple metrics, error analysis, failure modes
6. **Documentation**: Clean README, reproducible results

### Suggested Datasets
- Kaggle active competition (for leaderboard motivation)
- UCI ML Repository (classic, well-understood)
- Real-world dataset from your domain/interest

### Deliverables
- [ ] GitHub repo with clean code and README
- [ ] Kaggle submission (if competition)
- [ ] Blog post: project write-up with insights
- [ ] LinkedIn post with key finding/visualization

---

## 🎯 Phase 2 Completion Criteria

You're ready for Phase 3 when you can:
- [ ] Implement logistic regression from scratch in under 30 minutes
- [ ] Explain XGBoost's algorithm step-by-step
- [ ] Choose between precision/recall/F1/AUC for a given problem (and explain why)
- [ ] Take a raw dataset → features → model → evaluation in one session
- [ ] Explain bias-variance tradeoff with concrete examples
- [ ] Published 2+ blog posts from this phase
