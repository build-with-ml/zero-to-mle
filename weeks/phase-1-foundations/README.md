# Phase 1: Math Foundations (Weeks 1–4)

## Overview

Build the mathematical intuition that underpins all of ML. If you already know linear algebra and calculus, speed-run this in 2 weeks.

**Key principle**: Don't just watch — implement everything in code and visualize it.

---

## Structure

```
phase-1-foundations/
├── README.md              ← You are here (index)
├── exercises/
│   ├── week-1/            ← Linear Algebra (6 exercises)
│   ├── week-2/            ← Probability & Statistics (5 exercises)
│   ├── week-3/            ← Calculus & Optimization (5 exercises)
│   └── week-4/            ← Consolidation & Capstone (3 exercises)
└── qa/
    ├── linear-algebra.md  ← Q&A collected during Week 1
    ├── probability.md     ← Q&A collected during Week 2
    └── optimization.md    ← Q&A collected during Week 3
```

---

## Week 1: Linear Algebra

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [3Blue1Brown: Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) | 3.5 hrs |
| 📺 Lectures | MIT 18.06 (Gilbert Strang) — Lectures 1–8 | 8 hrs |
| 📖 Book | [Mathematics for Machine Learning](https://mml-book.github.io/) Ch. 2–4 | Reference |

### Exercises
| # | Exercise | Key Skill |
|---|---|---|
| 1 | [Vector Operations](exercises/week-1/ex-1-vector-operations.md) | Dot product, cosine similarity, projection |
| 2 | [Matrix Operations](exercises/week-1/ex-2-matrix-operations.md) | Matmul, inverse, determinant |
| 3 | [Linear Transformations](exercises/week-1/ex-3-linear-transformations.md) | Rotation, scaling, shear (visual) |
| 4 | [Eigendecomposition](exercises/week-1/ex-4-eigendecomposition.md) | Power iteration, eigenvectors |
| 5 | [SVD & Image Compression](exercises/week-1/ex-5-svd-image-compression.md) | SVD, low-rank approximation |
| 6 | [PCA from Scratch](exercises/week-1/ex-6-pca-from-scratch.md) | Full PCA implementation |

### Practice Problems
From [Mathematics for Machine Learning](https://mml-book.github.io/) — solutions at [github.com/ilmoi/MML-Book](https://github.com/ilmoi/MML-Book):

| # | Problem | Chapter | Topic |
|---|---|---|---|
| 1 | Exercise 2.1 | Ch. 2 | Prove vectors form a basis |
| 2 | Exercise 2.4 | Ch. 2 | Linear independence check |
| 3 | Exercise 2.6 | Ch. 2 | Matrix inverse computation |
| 4 | Exercise 3.1 | Ch. 3 | Inner product properties |
| 5 | Exercise 3.4 | Ch. 3 | Orthogonal projection |
| 6 | Exercise 3.7 | Ch. 3 | Gram-Schmidt orthogonalization |
| 7 | Exercise 4.1 | Ch. 4 | Compute determinant |
| 8 | Exercise 4.4 | Ch. 4 | Find eigenvalues and eigenvectors |
| 9 | Exercise 4.6 | Ch. 4 | Diagonalization |
| 10 | Exercise 4.9 | Ch. 4 | SVD decomposition |

---

## Week 2: Probability & Statistics

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [StatQuest: Probability Playlist](https://www.youtube.com/c/joshstarmer) | 6 hrs |
| 📖 Book | [Think Stats](https://greenteapress.com/thinkstats2/) (Allen Downey, free) | Reference |
| 📖 Book | [MML Book](https://mml-book.github.io/) Ch. 6 | Reference |

### Exercises
| # | Exercise | Key Skill |
|---|---|---|
| 1 | [Probability Distributions](exercises/week-2/ex-1-probability-distributions.md) | PDF/PMF implementation, CLT |
| 2 | [Naive Bayes Spam Classifier](exercises/week-2/ex-2-naive-bayes-spam.md) | Bayes theorem applied |
| 3 | [Maximum Likelihood Estimation](exercises/week-2/ex-3-maximum-likelihood.md) | MLE vs MAP |
| 4 | [A/B Test Simulator](exercises/week-2/ex-4-ab-test-simulator.md) | Hypothesis testing, power |
| 5 | [Bootstrap Confidence Intervals](exercises/week-2/ex-5-bootstrap-confidence.md) | Non-parametric inference |

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | Compute posterior given prior and likelihood | Bayes rule |
| 2 | Prove E[X+Y] = E[X] + E[Y] | Expectation linearity |
| 3 | Compute variance of a Bernoulli(p) | Variance |
| 4 | MLE for exponential distribution parameter λ | MLE derivation |
| 5 | P(disease\|positive test) given sensitivity=0.99, specificity=0.95, prevalence=0.01 | Bayes |
| 6 | How many samples for A/B test: 80% power, 5% significance, 2% effect size? | Power analysis |
| 7 | Prove: if X ~ N(μ,σ²) then (X-μ)/σ ~ N(0,1) | Standardization |
| 8 | Compute KL divergence between N(0,1) and N(1,2) | Information theory |
| 9 | Prove MLE for Gaussian mean = sample mean | MLE |
| 10 | 100 coin flips, 62 heads. Is it fair? (compute p-value) | Hypothesis test |

---

## Week 3: Calculus & Optimization

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [3Blue1Brown: Essence of Calculus](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr) | 3 hrs |
| 📖 Notes | Stanford CS229 Lectures 1–2 | 2 hrs |
| 📺 Video | [StatQuest: Gradient Descent](https://www.youtube.com/watch?v=sDv4f4s2SB8) | 30 min |

### Exercises
| # | Exercise | Key Skill |
|---|---|---|
| 1 | [Gradient Descent for Linear Regression](exercises/week-3/ex-1-gradient-descent-linreg.md) | GD implementation |
| 2 | [Five Optimizers](exercises/week-3/ex-2-five-optimizers.md) | SGD, Momentum, RMSProp, Adam, AdamW |
| 3 | [Chain Rule & Backprop Preview](exercises/week-3/ex-3-chain-rule-backprop.md) | Manual differentiation |
| 4 | [Learning Rate Finder](exercises/week-3/ex-4-learning-rate-finder.md) | Leslie Smith method |
| 5 | [Convexity Exploration](exercises/week-3/ex-5-convexity-exploration.md) | Local minima, saddle points |

### Practice Problems
| # | Problem | Topic |
|---|---|---|
| 1 | Compute gradient of f(x,y) = x²y + y³ | Partial derivatives |
| 2 | Chain rule: f(g(x)) where f(z)=z², g(x)=x³+1 | Chain rule |
| 3 | Compute Jacobian of f(x,y) = [x²+y, xy] | Jacobian |
| 4 | Derive gradient of MSE loss for linear regression | ML loss gradient |
| 5 | Derive gradient of binary cross-entropy loss | Classification loss |
| 6 | Prove Adam's bias correction is needed | Adam optimizer |
| 7 | Newton's method converges in 1 step for quadratic functions — prove | Second-order |
| 8 | Compute Hessian of f(x,y) = x³ + xy² | Hessian |
| 9 | Why does momentum help escape saddle points? | Optimization |
| 10 | Derive gradient of softmax cross-entropy loss | Deep learning prereq |

---

## Week 4: Consolidation & Capstone

### Exercises
| # | Exercise | Key Skill |
|---|---|---|
| 1 | [PCA on Real Data (Capstone)](exercises/week-4/ex-1-pca-capstone.md) | Apply PCA to MNIST/faces |
| 2 | [Math Concept Map](exercises/week-4/ex-2-concept-map.md) | Connect all topics visually |
| 3 | [Blog Series](exercises/week-4/ex-3-blog-series.md) | Publish "Math for ML Engineers" |

---

## 🎯 Phase 1 Completion Criteria

You're ready for Phase 2 when you can:
- [ ] Explain what eigenvalues mean geometrically (without looking it up)
- [ ] Implement PCA from scratch and explain each step
- [ ] Calculate the gradient of a loss function by hand
- [ ] Explain why Adam converges faster than vanilla SGD
- [ ] Code Naive Bayes from scratch in under 30 minutes
- [ ] Published at least 1 blog post with visualizations
- [ ] LeetCode: 40+ problems solved (Easy → transitioning to Medium)
