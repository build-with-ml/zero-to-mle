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

### Exercises

#### Exercise 1: Vector Operations
Implement from scratch in NumPy (no `np.dot`, `np.matmul` etc.):
- Dot product of two vectors
- Cross product of two 3D vectors
- Vector projection of **a** onto **b**
- Cosine similarity between two vectors
- **Test**: Verify your cosine similarity matches `sklearn.metrics.pairwise.cosine_similarity`

#### Exercise 2: Matrix Operations
Implement from scratch:
- Matrix multiplication (triple nested loop, then optimize with NumPy broadcasting)
- Matrix transpose
- Matrix determinant (2×2 and 3×3)
- Matrix inverse (2×2 using adjugate formula)
- **Test**: Verify `your_matmul(A, B)` matches `np.matmul(A, B)` for random matrices

#### Exercise 3: Linear Transformations (Visual)
- Create a 2D grid of points (unit square or circle)
- Apply rotation matrix: `[[cos θ, -sin θ], [sin θ, cos θ]]`
- Apply scaling matrix: `[[sx, 0], [0, sy]]`
- Apply shear matrix: `[[1, k], [0, 1]]`
- **Visualize**: Plot before/after for each transformation using matplotlib
- **Bonus**: Animate the transformation (interpolate from identity to final matrix)

#### Exercise 4: Eigendecomposition
- Implement power iteration to find the largest eigenvalue/eigenvector
- Verify against `np.linalg.eig`
- **Visualize**: Plot a transformation matrix, overlay its eigenvectors. Show that eigenvectors only get scaled (not rotated)
- **Question to answer**: Why do eigenvectors matter for PCA?

#### Exercise 5: SVD & Image Compression
- Load a grayscale image as a matrix
- Compute SVD: `U, S, Vt = np.linalg.svd(image)`
- Reconstruct using only top-k singular values (k = 1, 5, 10, 20, 50, 100)
- **Visualize**: Grid of reconstructed images with compression ratio and error
- **Question to answer**: What % of singular values captures 90% of the "information"?

#### Exercise 6: PCA from Scratch
- Load a dataset (use Iris or MNIST digits)
- Center the data (subtract mean)
- Compute covariance matrix
- Find eigenvalues/eigenvectors of covariance matrix
- Project data onto top-2 eigenvectors
- **Visualize**: 2D scatter plot colored by class labels
- **Verify**: Compare your result to `sklearn.decomposition.PCA`

### Practice Problems (from MML Book)
Solve these from [Mathematics for Machine Learning](https://mml-book.github.io/) — answers available in [solutions repo](https://github.com/ilmoi/MML-Book):

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

### Blog Ideas
- "Seeing Linear Algebra: Why Eigenvectors Matter for ML" (with your Exercise 4 visualizations)
- "Image Compression with SVD in 20 Lines of NumPy" (your Exercise 5 results)

### Interview Connection
- PCA is asked in ML fundamentals rounds (Amazon, Google)
- "How does SVD relate to recommendation systems?" (Meta)
- "What's cosine similarity and where is it used?" (everywhere — embeddings, search, attention)

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
| 📖 Book | "Mathematics for Machine Learning" Ch. 6 — [free PDF](https://mml-book.github.io/) | Reference |
| 🔗 Practice | Khan Academy: Statistics & Probability | Supplementary |

### Exercises

#### Exercise 1: Probability Distributions
- Implement PDF/PMF from scratch for: Bernoulli, Binomial, Poisson, Gaussian
- For each: generate 10,000 samples, plot histogram, overlay your PDF
- **Verify**: Compare to `scipy.stats` distributions
- **Visualize**: Show how Binomial → Gaussian as n increases (Central Limit Theorem)

#### Exercise 2: Bayes' Theorem — Spam Classifier
- Implement a Naive Bayes spam classifier from scratch (no sklearn)
- Dataset: [SpamAssassin public corpus](https://spamassassin.apache.org/old/publiccorpus/) or any text classification dataset
- Steps: tokenize → compute P(word|spam), P(word|ham) → apply Bayes rule
- **Test**: Achieve >90% accuracy, compare to `sklearn.naive_bayes.MultinomialNB`

#### Exercise 3: Maximum Likelihood Estimation
- Generate 1000 samples from a Gaussian with unknown μ and σ
- Implement MLE to estimate μ and σ from the samples
- **Visualize**: Plot the likelihood function, show the maximum
- **Extend**: Compare MLE vs MAP estimation (add a prior on μ)

#### Exercise 4: A/B Test Simulator
- Build a simulator that:
  1. Simulates two groups (control/treatment) with known conversion rates
  2. Computes p-value using z-test
  3. Calculates required sample size for given power (80%) and effect size
  4. Runs 1000 simulations to show false positive rate ≈ 5% (at α=0.05)
- **Visualize**: Plot p-value distribution under null hypothesis (should be uniform!)
- **Visualize**: Show how power increases with sample size

#### Exercise 5: Bootstrap Confidence Intervals
- Take a real dataset (median income, average height, etc.)
- Implement bootstrap: resample with replacement 10,000 times
- Compute 95% confidence interval from bootstrap distribution
- **Visualize**: Histogram of bootstrap means with CI marked
- **Compare**: Bootstrap CI vs parametric CI (t-distribution)

### Practice Problems
| # | Problem | Source | Topic |
|---|---|---|---|
| 1 | Compute posterior given prior and likelihood | MML Ch. 6, Ex. 6.1 | Bayes rule |
| 2 | Prove E[X+Y] = E[X] + E[Y] | MML Ch. 6, Ex. 6.3 | Expectation |
| 3 | Compute variance of a Bernoulli | MML Ch. 6, Ex. 6.4 | Variance |
| 4 | MLE for exponential distribution | Think Stats Ch. 8 | MLE |
| 5 | Given test sensitivity/specificity, compute P(disease\|positive test) | Classic Bayes | Conditional probability |
| 6 | Design A/B test: how many samples for 80% power, 5% significance, 2% effect? | Custom | Power analysis |
| 7 | Prove: if X ~ N(μ,σ²), then (X-μ)/σ ~ N(0,1) | MML Ch. 6, Ex. 6.6 | Standardization |
| 8 | Compute KL divergence between two Gaussians | MML Ch. 6, Ex. 6.9 | Information theory |
| 9 | Show that MLE for Gaussian mean = sample mean | Think Stats Ch. 8 | MLE derivation |
| 10 | Coin flipped 100 times, 62 heads. Is it fair? (hypothesis test) | Custom | Hypothesis testing |

### Blog Ideas
- "Bayesian Thinking for ML Engineers: A Visual Primer" (with Exercise 2)
- "A/B Testing Simulator: See Statistical Power in Action" (with Exercise 4)

### Interview Connection
- "How would you design an A/B test for this feature?" (Amazon, Meta)
- "Explain the bias-variance tradeoff" (everywhere)
- "What's the difference between Type I and Type II error?" (fundamentals)

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
| 📖 Book | MML Ch. 5 (Vector Calculus) | Reference |

### Exercises

#### Exercise 1: Gradient Descent for Linear Regression
- Generate synthetic data: y = 3x + 7 + noise
- Implement gradient descent to find w and b:
  1. Initialize randomly
  2. Compute loss (MSE)
  3. Compute gradients ∂L/∂w and ∂L/∂b (by hand first, then in code)
  4. Update: w = w - lr * ∂L/∂w
  5. Repeat until convergence
- **Visualize**: Plot loss curve over iterations
- **Visualize**: Animate the regression line fitting over time
- **Experiment**: Try learning rates 0.001, 0.01, 0.1, 1.0 — show convergence/divergence

#### Exercise 2: Implement 5 Optimizers
Implement from scratch on the Rosenbrock function `f(x,y) = (1-x)² + 100(y-x²)²`:
1. **Vanilla SGD**: `θ = θ - lr * gradient`
2. **Momentum**: `v = β*v + gradient; θ = θ - lr * v`
3. **RMSProp**: `s = β*s + (1-β)*gradient²; θ = θ - lr * gradient/√(s+ε)`
4. **Adam**: Combines momentum + RMSProp with bias correction
5. **AdamW**: Adam with decoupled weight decay

- **Visualize**: Plot all 5 optimizer trajectories on a contour plot of the loss surface (side-by-side or overlaid)
- **Bonus**: Create an animated GIF of all 5 converging simultaneously

#### Exercise 3: Chain Rule & Backprop Preview
- For the function f(x) = sigmoid(wx + b):
  1. Compute ∂f/∂w and ∂f/∂b by hand (using chain rule)
  2. Verify numerically: `(f(w+ε) - f(w-ε)) / (2ε)` ≈ your analytical gradient
  3. Extend to 2-layer: f(x) = sigmoid(w2 * sigmoid(w1*x + b1) + b2)
  4. Compute all gradients by hand, verify numerically
- **This is backpropagation** — you just did it manually!

#### Exercise 4: Learning Rate Finder
- Implement the Leslie Smith learning rate finder:
  1. Start with very small lr (1e-7)
  2. Train for one batch, record loss
  3. Increase lr exponentially
  4. Repeat until loss explodes
- **Visualize**: Plot loss vs learning rate — the optimal lr is just before the minimum
- **Test on**: Your linear regression from Exercise 1

#### Exercise 5: Convexity Exploration
- Plot 3 functions: `x²` (convex), `x⁴ - 3x² + x` (non-convex), `|x|` (convex but non-differentiable)
- Run gradient descent on each. Show:
  - Convex: always converges to global minimum
  - Non-convex: gets stuck in local minimum (depending on initialization)
  - Non-differentiable: what happens at x=0?
- **Visualize**: Multiple starting points → different final positions for non-convex

### Practice Problems
| # | Problem | Source | Topic |
|---|---|---|---|
| 1 | Compute gradient of f(x,y) = x²y + y³ | MML Ch. 5, Ex. 5.1 | Partial derivatives |
| 2 | Apply chain rule to f(g(x)) where f(z)=z², g(x)=x³+1 | MML Ch. 5, Ex. 5.3 | Chain rule |
| 3 | Compute Jacobian of f(x,y) = [x²+y, xy] | MML Ch. 5, Ex. 5.4 | Jacobian |
| 4 | Derive gradient of MSE loss: L = (1/n)Σ(yi - wxi - b)² | Custom | ML loss gradient |
| 5 | Derive gradient of cross-entropy loss: L = -[y·log(ŷ) + (1-y)·log(1-ŷ)] | Custom | Classification loss |
| 6 | Prove that Adam's bias correction is needed (show bias without it) | Custom | Adam optimizer |
| 7 | Show that Newton's method converges in 1 step for quadratic functions | MML Ch. 5 | Second-order methods |
| 8 | Compute Hessian of f(x,y) = x³ + xy² | MML Ch. 5, Ex. 5.6 | Hessian |
| 9 | Why does momentum help escape saddle points? (explain with gradient = 0) | Custom | Optimization intuition |
| 10 | Derive the gradient of softmax cross-entropy loss | Custom | Deep learning prerequisite |

### Blog Ideas
- "Watching Optimizers Think: Animated Comparisons on Loss Landscapes" ← HIGH VIRAL POTENTIAL (Exercise 2 output)
- "Gradient Descent from First Principles (with Proof)" (Exercise 1 + 3)

### Interview Connection
- "Explain how Adam optimizer works" (Amazon, Google, OpenAI)
- "Why might training diverge?" → learning rate too high, gradient explosion
- "What's the difference between convex and non-convex optimization?" (ML fundamentals)

---

## Week 4: Consolidation & First Content Push

### Learning Objectives
- Apply math foundations to a real ML problem
- Create polished, shareable content
- Establish your online presence

### Exercises

#### Exercise 1: PCA on Real Data (Capstone)
- Load MNIST digits (or Olivetti faces)
- Apply your PCA implementation from Week 1
- Reduce to 2D → visualize clusters colored by digit/person
- Reconstruct with varying components (2, 10, 50, 100, 784)
- **Visualize**: Grid of reconstructed images showing quality vs # components
- **Calculate**: Plot cumulative explained variance ratio — how many components for 95%?

#### Exercise 2: Math Concept Map
- Create a visual diagram connecting all concepts from Weeks 1–3:
  - Linear algebra → PCA → dimensionality reduction
  - Calculus → gradients → optimization → training
  - Probability → likelihood → MLE → loss functions
  - SVD → low-rank → embeddings → LoRA
- Use Excalidraw or draw.io
- **Publish**: This becomes a shareable asset for your blog

#### Exercise 3: Blog Series
Publish "Math for ML Engineers" (3 parts):
- Part 1: Linear Algebra (link to Exercise 4–6 from Week 1)
- Part 2: Probability (link to Exercises 2, 4 from Week 2)
- Part 3: Optimization (link to Exercise 2 from Week 3 — the animated optimizers)

### Checklist
- [ ] All Phase 1 exercises completed and notebooks are clean
- [ ] Blog series is live (Hashnode/Dev.to/Medium)
- [ ] GitHub profile README exists with project links
- [ ] First LinkedIn post about the journey published
- [ ] LeetCode: 40+ problems solved (Easy → transitioning to Medium)

---

## 🎯 Phase 1 Completion Criteria

You're ready for Phase 2 when you can:
- [ ] Explain what eigenvalues mean geometrically (without looking it up)
- [ ] Implement PCA from scratch and explain each step
- [ ] Calculate the gradient of a loss function by hand
- [ ] Explain why Adam converges faster than vanilla SGD
- [ ] Code Naive Bayes from scratch in under 30 minutes
- [ ] Published at least 1 blog post with visualizations
