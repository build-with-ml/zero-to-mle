# Phase 2: Core Machine Learning (Weeks 5–10)

## Overview

Master classical ML algorithms — not just using sklearn, but understanding the internals. This phase covers what's tested most heavily in ML fundamentals rounds.

**Key principle**: Implement from scratch first, THEN use sklearn/XGBoost. Know the tradeoffs.

---

## Week 5: Linear Models & Regularization

### Learning Objectives
- Implement linear and logistic regression from scratch
- Understand L1/L2 regularization geometrically and mathematically
- Know when and why to use regularization

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Andrew Ng ML Specialization — Course 1, Weeks 1–3 | 6 hrs |
| 📺 Video | StatQuest: Regularization, Ridge, Lasso | 2 hrs |
| 📖 Book | Géron "Hands-On ML" Ch. 4 | 2 hrs |

### Exercises

#### Exercise 1: Linear Regression — Three Ways
Implement linear regression three different ways on the same dataset:
1. **Closed-form (Normal Equation)**: θ = (XᵀX)⁻¹Xᵀy
2. **Gradient Descent**: Iterative update with learning rate
3. **Stochastic Gradient Descent**: Mini-batch updates
- **Test**: All three should produce the same θ (within tolerance)
- **Visualize**: Plot convergence of GD and SGD (loss vs iterations)
- **Experiment**: How does batch size affect SGD convergence?

#### Exercise 2: Logistic Regression from Scratch
- Implement binary logistic regression with gradient descent:
  1. Sigmoid function
  2. Binary cross-entropy loss
  3. Gradient computation
  4. Training loop with learning rate
- Train on the [Breast Cancer Wisconsin dataset](https://scikit-learn.org/stable/datasets/toy_dataset.html#breast-cancer-wisconsin-diagnostic-dataset)
- **Test**: Achieve >95% accuracy, compare to `sklearn.linear_model.LogisticRegression`
- **Visualize**: Decision boundary on 2D PCA projection of the data
- **Extend**: Add L2 regularization. Show how decision boundary changes with λ.

#### Exercise 3: Regularization Path
- Train Ridge regression on the [Boston Housing](https://scikit-learn.org/stable/datasets/toy_dataset.html) (or California Housing) dataset
- Vary λ (alpha) from 0.001 to 10000 (log scale, 50 values)
- **Visualize**: Plot all coefficients vs log(λ) — this is the "regularization path"
- Repeat with Lasso (L1) — show how some coefficients go to exactly zero
- **Question to answer**: Why does L1 produce sparsity but L2 doesn't? (geometric explanation)

#### Exercise 4: Polynomial Regression & Overfitting
- Generate noisy sine wave data: y = sin(x) + noise (30 points)
- Fit polynomial regression with degree = 1, 3, 5, 9, 15
- **Visualize**: All fits overlaid on data — show underfitting → good fit → overfitting
- Add Ridge regularization to degree-15 polynomial — show it prevents overfitting
- **Visualize**: Train error vs test error vs polynomial degree (bias-variance tradeoff curve)

#### Exercise 5: Multi-class Logistic Regression (Softmax)
- Implement softmax regression from scratch (one-vs-all is also fine)
- Train on Iris dataset (3 classes)
- **Test**: Compare to `sklearn.linear_model.LogisticRegression(multi_class='multinomial')`
- **Visualize**: Decision regions in 2D (use first 2 features or PCA)

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | Derive the gradient of MSE loss for linear regression (by hand) | Gradient derivation |
| 2 | Derive the gradient of binary cross-entropy for logistic regression | Gradient derivation |
| 3 | Prove: Ridge regression has a unique solution even when XᵀX is singular | Regularization theory |
| 4 | Why does L1 regularization produce sparse solutions? Draw the constraint regions. | Geometric intuition |
| 5 | Implement ElasticNet (L1 + L2 combined) from scratch | Implementation |
| 6 | What happens to Ridge coefficients as λ → ∞? Prove mathematically. | Limiting behavior |
| 7 | Compare Normal Equation vs GD: when is each preferred? (consider n, p) | Complexity analysis |
| 8 | Implement feature scaling (standardization vs normalization). Show effect on GD convergence. | Preprocessing |
| 9 | What's the difference between Lasso and feature selection with correlation? | Feature selection |
| 10 | Implement logistic regression with early stopping. Plot train/val loss to find optimal point. | Regularization via stopping |

### Interview Connection
- "Implement logistic regression" — common Amazon/Google coding round
- "When would you use L1 vs L2?" — L1 for feature selection, L2 for multicollinearity
- "Explain the bias-variance tradeoff" — your Exercise 4 visualization answers this perfectly

---

## Week 6: Trees & Ensembles

### Learning Objectives
- Implement a decision tree from scratch (understand splits)
- Know the difference between bagging, boosting, and stacking
- Master XGBoost for tabular data

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | StatQuest: Decision Trees + Random Forest + XGBoost (full series) | 4 hrs |
| 📖 Book | Géron Ch. 6–7 | 3 hrs |
| 📖 Docs | [XGBoost documentation](https://xgboost.readthedocs.io/) | Reference |

### Exercises

#### Exercise 1: Decision Tree from Scratch
- Implement a binary classification decision tree:
  1. Gini impurity calculation
  2. Information gain calculation
  3. Best split finder (iterate all features and thresholds)
  4. Recursive tree building with max_depth limit
  5. Prediction (traverse tree)
- Train on Iris dataset
- **Test**: Compare accuracy to `sklearn.tree.DecisionTreeClassifier`
- **Visualize**: Print tree structure (feature, threshold, left/right children)
- **Bonus**: Implement entropy-based splits too. Compare trees.

#### Exercise 2: Visualize Tree Decisions
- Train sklearn DecisionTreeClassifier on 2D toy datasets:
  1. Linearly separable (two Gaussians)
  2. XOR pattern (4 clusters)
  3. Concentric circles (`make_circles`)
- **Visualize**: Decision boundary for each (colored regions + data points)
- **Experiment**: Vary max_depth (1, 3, 5, None) — show overfitting progression
- **Question to answer**: Why are trees axis-aligned? What patterns can't they capture well?

#### Exercise 3: Random Forest vs Bagging
- Implement bagging from scratch: train N trees on bootstrap samples, majority vote
- Compare to `sklearn.ensemble.RandomForestClassifier`
- **Experiment**: Vary n_estimators (1, 5, 10, 50, 100) — plot accuracy vs # trees
- **Visualize**: OOB (out-of-bag) error convergence as trees are added
- **Question to answer**: Why does random feature subsampling help? (decorrelation)

#### Exercise 4: XGBoost Deep Dive
- Train XGBoost on a Kaggle tabular dataset (Titanic, House Prices, or similar)
- Systematic hyperparameter tuning:
  1. First: max_depth (3–7), min_child_weight (1–7)
  2. Then: subsample (0.6–0.9), colsample_bytree (0.6–0.9)
  3. Then: learning_rate (0.01–0.1), increase n_estimators
- Use early stopping with validation set
- **Visualize**: Feature importance (3 methods: weight, gain, SHAP)
- **Test**: Beat a default Random Forest by at least 2% AUC

#### Exercise 5: SHAP Explanations
- Install SHAP library: `pip install shap`
- Train XGBoost model on any dataset
- Generate:
  1. SHAP summary plot (beeswarm)
  2. SHAP waterfall plot for a single prediction
  3. SHAP dependence plot for top feature
  4. SHAP force plot for a single prediction
- **Visualize**: All 4 plots. Include in your blog.
- **Question to answer**: Pick one prediction the model got wrong. Use SHAP to explain why.

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | Compute Gini impurity for a node with [40 cats, 60 dogs]. What split gives max info gain? | Split criterion |
| 2 | Why is max_depth the most impactful regularization hyperparameter for trees? | Overfitting |
| 3 | Explain the difference between bagging and boosting (diagram the process) | Ensemble methods |
| 4 | XGBoost uses second-order Taylor expansion of the loss. Why is this better than first-order? | Boosting theory |
| 5 | What's the computational complexity of finding the best split? (O(n·p·log n) — explain why) | Complexity |
| 6 | Random Forest uses max_features=sqrt(p). Why this default? What happens if you use all features? | Feature subsampling |
| 7 | How does XGBoost handle missing values? (built-in — explain the algorithm) | Missing data |
| 8 | Compare permutation importance vs impurity-based importance. When do they disagree? | Feature importance |
| 9 | What's gradient boosting's relationship to gradient descent? (hint: functional gradient descent) | Theory |
| 10 | You have 100 features, 80% are irrelevant. Which handles this better: Random Forest or XGBoost? Why? | Feature selection |

### Interview Connection
- "How does XGBoost handle overfitting?" — top 3 most-asked question (Amazon, Meta)
- "Explain gradient boosting step by step" — ML fundamentals rounds
- "How would you explain this model's prediction to a business stakeholder?" — SHAP (Amazon LP: Earn Trust)

---

## Week 7: Model Evaluation & Selection

### Learning Objectives
- Choose the right metric for any problem
- Implement cross-validation properly
- Understand calibration and threshold selection

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Book | Géron Ch. 2–3 | 2 hrs |
| 📺 Course | Kaggle Learn: Intermediate ML | 3 hrs |
| 📺 Video | StatQuest: ROC, AUC, Cross-Validation, F1 Score | 3 hrs |

### Exercises

#### Exercise 1: Metrics Comparison on Imbalanced Data
- Create an imbalanced dataset: 95% class 0, 5% class 1 (use `make_classification` with `weights=[0.95, 0.05]`)
- Train a model. Compute: Accuracy, Precision, Recall, F1, PR-AUC, ROC-AUC
- Train a dummy model that always predicts majority class
- **Compare**: Which metrics are fooled by the dummy? Which aren't?
- **Visualize**: Confusion matrix heatmap for both models
- **Question to answer**: Your fraud model has 99.9% accuracy. Is it good?

#### Exercise 2: Precision-Recall Threshold Tuner
- Train a logistic regression on imbalanced data (fraud or medical diagnosis)
- Get predicted probabilities (`predict_proba`)
- Vary classification threshold from 0.0 to 1.0 (100 values)
- **Visualize**: Plot Precision and Recall vs Threshold on the same chart
- **Visualize**: Plot the PR curve (Precision vs Recall)
- **Mark**: The threshold that maximizes F1 score
- **Question to answer**: A hospital wants <1% false negatives. What threshold do you use?

#### Exercise 3: Cross-Validation from Scratch
- Implement K-Fold cross-validation from scratch (k=5):
  1. Split data into k folds
  2. For each fold: train on k-1 folds, evaluate on held-out fold
  3. Return mean and std of scores
- Implement Stratified K-Fold (preserves class distribution per fold)
- **Test**: Compare your results to `sklearn.model_selection.cross_val_score`
- **Experiment**: Compare K=3, 5, 10, LOOCV — how does variance change?
- **Visualize**: Box plot of scores across folds for k=5 and k=10

#### Exercise 4: Learning Curves (Bias vs Variance Diagnosis)
- Train a model (e.g., SVM or polynomial regression) with increasing training set sizes
- For each size: record train score and validation score
- **Visualize**: Plot train score and val score vs training set size
- Generate 3 scenarios:
  1. High bias (underfitting): both scores are low, converge early
  2. High variance (overfitting): train high, val low, big gap
  3. Good fit: both scores high, small gap
- **Question to answer**: Given a learning curve, how do you decide: more data vs more complex model?

#### Exercise 5: Hyperparameter Tuning Comparison
- Pick XGBoost with 5 hyperparameters to tune
- Implement and compare 3 search strategies:
  1. Grid Search (exhaustive, 3 values per param)
  2. Random Search (same budget as grid: ~243 evaluations)
  3. Bayesian Optimization (using `optuna` or `hyperopt`, same budget)
- **Record**: Best score, time taken, evaluations needed
- **Visualize**: Scatter plot of score vs evaluation number for each method
- **Question to answer**: Why does Random Search often beat Grid Search?

#### Exercise 6: Model Calibration
- Train a Random Forest on a binary classification task
- Plot calibration curve: predicted probability vs actual frequency (reliability diagram)
- Apply Platt scaling (logistic regression on predictions) and isotonic regression
- **Visualize**: Calibration curve before and after calibration
- **Test**: Compute Brier score before and after
- **Question to answer**: When does calibration matter? (hint: when you USE the probabilities, not just the ranking)

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | Your fraud model: 99.9% accuracy, 0.1% fraud rate. Compute precision & recall if it catches 60% of fraud. | Metrics on imbalanced data |
| 2 | ROC-AUC = 0.5. What does this mean? When can AUC be misleading? | AUC interpretation |
| 3 | You have 3 models with F1 = 0.82, 0.84, 0.83. Are they significantly different? How would you test? | Statistical significance |
| 4 | Explain why PR-AUC is better than ROC-AUC for imbalanced data | Metric selection |
| 5 | A model's train accuracy = 99%, val accuracy = 70%. Diagnose and propose 3 fixes. | Overfitting diagnosis |
| 6 | Cross-val gives [0.91, 0.72, 0.89, 0.88, 0.90]. One fold is low. What could cause this? | CV troubleshooting |
| 7 | Random Search with 60 trials vs Grid Search with 60 trials (3 params, each with 4 values). Which explores more? Why? | Tuning strategy |
| 8 | Your model predicts P(click)=0.8 for 100 items, but only 50 are clicked. Is it well-calibrated? | Calibration |
| 9 | When should you use macro-F1 vs micro-F1 vs weighted-F1? Give example for each. | Multi-class metrics |
| 10 | Design a validation strategy for time-series data. Why is random K-fold wrong? | Temporal validation |

### Interview Connection
- "How would you evaluate this model?" — EVERY ML system design interview
- "Your model has high accuracy but business complains. What might be wrong?" — metric mismatch
- "How do you choose between precision and recall?" — depends on business cost (Amazon LP: Customer Obsession)

---

## Week 8: Feature Engineering & Data Processing

### Learning Objectives
- Master encoding strategies for different data types
- Handle messy real-world data confidently
- Understand feature stores and data leakage

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | [Kaggle Learn: Feature Engineering](https://www.kaggle.com/learn/feature-engineering) (free) | 3 hrs |
| 📖 Book | Géron Ch. 2 (end-to-end project with data prep) | 2 hrs |
| 📺 Course | Made With ML: Data section | 2 hrs |

### Exercises

#### Exercise 1: Encoding Strategies Comparison
Using a dataset with mixed types (Kaggle's [Titanic](https://www.kaggle.com/c/titanic) or [House Prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)):
- Implement 4 encoding methods for categorical features:
  1. One-hot encoding
  2. Label/ordinal encoding
  3. Target encoding (mean of target per category)
  4. Frequency encoding
- Train the same model (XGBoost) with each encoding
- **Compare**: Accuracy/AUC for each. Which won?
- **Question to answer**: When does one-hot fail? (hint: high cardinality)

#### Exercise 2: Missing Data Strategies
- Take a dataset and artificially introduce 20% missing values (MCAR, MAR, MNAR)
- Implement 5 imputation strategies:
  1. Drop rows with missing values
  2. Mean/median/mode imputation
  3. KNN imputation
  4. Iterative imputation (MICE)
  5. Add "is_missing" indicator column + simple imputation
- **Compare**: Model accuracy with each strategy
- **Visualize**: Distribution of imputed values vs original for each method
- **Question to answer**: When is dropping rows dangerous? When is mean imputation biased?

#### Exercise 3: Feature Creation & Interaction
- Using House Prices dataset, create 10+ new features:
  1. Ratios: price_per_sqft, rooms_per_floor
  2. Aggregations: mean_price_by_neighborhood
  3. Temporal: years_since_renovation, season_sold
  4. Interactions: bedrooms × bathrooms
  5. Polynomial: sqft², log(sqft)
- **Compare**: Model performance with original features vs original + engineered
- **Visualize**: Feature importance of new features — do they rank high?
- **Record**: Which engineered features provided the most lift?

#### Exercise 4: Data Leakage Detector
- Create 3 scenarios of data leakage:
  1. Feature that encodes the target (e.g., "approved_amount" for loan default)
  2. Preprocessing (scaling) before train/test split
  3. Target encoding computed on full data (including test set)
- For each: train model WITH and WITHOUT the leak
- **Show**: Unrealistically high performance with leak vs realistic without
- **Build**: A simple leakage detection script that flags suspicious features (100% correlated with target, or only available after prediction time)

#### Exercise 5: Feature Selection Pipeline
- Implement 3 feature selection methods on a high-dimensional dataset (50+ features):
  1. Filter: correlation with target + mutual information
  2. Wrapper: Recursive Feature Elimination (RFE)
  3. Embedded: L1 regularization (Lasso) + XGBoost importance
- **Compare**: Final feature sets from each method — how much overlap?
- **Visualize**: Model accuracy vs number of features (diminishing returns curve)
- **Question to answer**: 100 features → what's the sweet spot for this dataset?

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | You have a "zip_code" feature with 40,000 unique values. How do you encode it? | High cardinality |
| 2 | Target encoding on training data leaks. How do you prevent this? (hint: fold-based) | Leakage prevention |
| 3 | 30% of a feature is missing. Correlation with target is 0.5. Drop it or impute? | Missing data decision |
| 4 | Feature A has importance=0.01 but removing it drops accuracy by 3%. Why? | Feature interactions |
| 5 | You join a customer table to a transaction table. What temporal leakage risks exist? | Time-based leakage |
| 6 | Numerical feature is heavily right-skewed. What transformations would you try? | Distribution handling |
| 7 | You have 1000 features, 50 samples. What problems arise? What do you do? | Curse of dimensionality |
| 8 | When should you standardize (z-score) vs normalize (min-max)? Give examples. | Scaling choice |
| 9 | Design a feature store schema for a recommendation system (user + item features) | Feature stores |
| 10 | A feature is constant in training but varies in production. What happens? What's the fix? | Train-serve skew |

### Interview Connection
- "What features would you use for X?" — Meta, Amazon ML system design
- "How do you prevent data leakage?" — fundamental judgment question
- "Walk me through your feature engineering process" — shows production maturity

---

## Week 9: Unsupervised Learning

### Learning Objectives
- Implement clustering algorithms from scratch
- Compare dimensionality reduction methods
- Detect anomalies in real datasets

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Book | Géron Ch. 8–9 | 3 hrs |
| 📺 Video | StatQuest: K-Means, PCA, t-SNE | 2 hrs |
| 📄 Paper | [UMAP paper (McInnes 2018)](https://arxiv.org/abs/1802.03426) | 1 hr |
