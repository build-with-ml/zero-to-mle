# Phase 1: Math Foundations (Weeks 1–4)

## Overview

Build the mathematical intuition that underpins all of ML. If you already know linear algebra and calculus, you can speed-run this phase in 2 weeks.

**Key principle**: Don't just watch — implement everything in code and visualize it.

---

## Week 1: Linear Algebra

### Learning Objectives
- Understand vectors, matrices, and linear transformations geometrically
- Implement core operations from scratch
- Connect linear algebra to ML applications (PCA, SVD, embeddings)

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [3Blue1Brown: Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) | 3.5 hrs |
| 📺 Lectures | MIT 18.06 (Gilbert Strang) — Lectures 1–8 | 8 hrs |
| 📖 Book | "Mathematics for Machine Learning" (Deisenroth) Ch. 2–4 — [free PDF](https://mml-book.github.io/) | Reference |
| 🔗 Practice | [Khan Academy: Linear Algebra](https://www.khanacademy.org/math/linear-algebra) | Supplementary |

### What to Build
1. **From-scratch implementations** (NumPy only):
   - Matrix multiplication
   - Dot product and projections
   - Eigenvalue decomposition
   - SVD (Singular Value Decomposition)
   - PCA (Principal Component Analysis)

2. **Visualizations**:
   - 2D transformation animations (rotation, scaling, shearing)
   - Eigenvectors staying on their span during transformation
   - PCA: show variance captured vs components

### Practice Problems
- Solve 10 problems from MML book Ch. 2–4
- Implement image compression using SVD (reduce rank, compare quality)

### Blog Ideas
- "Seeing Linear Algebra: Why Eigenvectors Matter for ML"
- "Image Compression with SVD in 20 Lines of NumPy"

### Connection to Interviews
- PCA is asked in ML fundamentals rounds (Amazon, Google)
- "How does SVD relate to recommendation systems?" (Meta)
- Understanding matrix operations is prerequisite for everything that follows

---

## Week 2: Probability & Statistics

### Learning Objectives
- Reason about uncertainty using probability
- Understand distributions and how to estimate parameters
- Know when and how to use hypothesis testing

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [StatQuest: Probability Playlist](https://www.youtube.com/c/joshstarmer) (all probability/stats videos) | 6 hrs |
| 📖 Book | "Think Stats" (Allen Downey) — [free online](https://greenteapress.com/thinkstats2/) | Reference |
| 📖 Book | "Probabilistic Machine Learning" (Kevin Murphy) Ch. 1–3 | Deep dive |
| 🔗 Practice | Khan Academy: Statistics & Probability | Supplementary |

### What to Build
1. **From-scratch implementations**:
   - Naive Bayes classifier (from first principles)
   - Maximum Likelihood Estimation for Gaussian parameters
   - A/B test simulator with p-value calculation
   - Bootstrap confidence intervals

2. **Visualizations**:
   - Bayesian prior → posterior animation (updating beliefs with each data point)
   - How sample size affects the width of confidence intervals
   - Distribution gallery: Normal, Poisson, Binomial, Beta

### Practice Problems
- Given a dataset, estimate parameters using MLE
- Design an A/B test: calculate required sample size for 80% power
- Solve 5 Bayesian inference problems

### Blog Ideas
- "Bayesian Thinking for ML Engineers: A Visual Primer"
- "A/B Testing Simulator: See Statistical Power in Action"

### Connection to Interviews
- "How would you design an A/B test for this feature?" (Amazon, Meta)
- "Explain the bias-variance tradeoff" (everywhere)
- Bayesian reasoning underpins many model decisions

---

## Week 3: Calculus & Optimization

### Learning Objectives
- Understand derivatives, gradients, and the chain rule
- Implement gradient-based optimization from scratch
- Compare optimizer behaviors visually

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [3Blue1Brown: Essence of Calculus](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr) | 3 hrs |
| 📖 Notes | Stanford CS229 Lecture 1–2 (gradient descent) | 2 hrs |
| 📺 Video | [StatQuest: Gradient Descent](https://www.youtube.com/watch?v=sDv4f4s2SB8) | 30 min |

### What to Build
1. **From-scratch implementations**:
   - Gradient descent for linear regression
   - SGD (Stochastic Gradient Descent)
   - Momentum
   - RMSProp
   - Adam

2. **Visualizations** (HIGH ENGAGEMENT potential):
   - 3D loss surface with optimizer trajectory overlay
   - Side-by-side GIF: SGD vs Momentum vs Adam converging
   - Saddle point escape: show how momentum helps

### Practice Problems
- Derive the gradient for logistic regression loss (by hand, then verify with code)
- Implement learning rate finder (plot loss vs learning rate)
- Show how Adam adapts learning rates per-parameter

### Blog Ideas
- "Watching Optimizers Think: Animated Comparisons on Loss Landscapes" ← HIGH VIRAL POTENTIAL
- "Gradient Descent from First Principles (with Proof)"

### Connection to Interviews
- "Explain how Adam optimizer works" (Amazon, Google, OpenAI)
- "Why might training diverge?" → learning rate, gradient explosion
- Understanding optimization = understanding why training succeeds or fails

---

## Week 4: Consolidation & First Content Push

### Learning Objectives
- Apply math foundations to a real ML problem
- Create polished, shareable content
- Establish your online presence

### What to Do
1. **Capstone mini-project**: Apply PCA to a real dataset
   - MNIST digits: reduce to 2D, visualize clusters
   - Face images: reconstruct with varying # of components
   - Show how much variance each component captures

2. **Blog series**: Publish "Math for ML Engineers" (3-part series)
   - Part 1: Linear Algebra (link to notebooks)
   - Part 2: Probability (link to notebooks)
   - Part 3: Optimization (link to notebooks + animations)

3. **GitHub cleanup**:
   - Add proper READMEs to all repos
   - Include rendered plots/GIFs in READMEs
   - Tag releases

4. **Start LeetCode habit**: 2 problems/day (Easy → Medium transition)

### Checklist
- [ ] All Phase 1 notebooks are clean and documented
- [ ] Blog series is live (Hashnode/Dev.to/Medium)
- [ ] GitHub profile README exists with project links
- [ ] First LinkedIn post about the journey published
- [ ] LeetCode streak established

---

## 🎯 Phase 1 Completion Criteria

You're ready for Phase 2 when you can:
- [ ] Explain what eigenvalues mean geometrically (without looking it up)
- [ ] Implement PCA from scratch and explain each step
- [ ] Calculate the gradient of a loss function by hand
- [ ] Explain why Adam converges faster than vanilla SGD
- [ ] Code Naive Bayes from scratch in under 30 minutes
- [ ] Published at least 1 blog post
