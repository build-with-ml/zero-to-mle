# ❓ Q&A: Linear Algebra (Week 1)

Questions and answers collected during study. Useful as self-test flashcards and interview prep.

---

### Q: What's the geometric intuition behind eigenvectors?

**Context**: Watching 3Blue1Brown's linear algebra series, trying to understand why eigenvectors matter for PCA.

**Answer**: 
An eigenvector is a direction that doesn't change when a linear transformation is applied — it only gets scaled (stretched or compressed) by the eigenvalue. Geometrically:
- Most vectors get rotated AND scaled by a transformation
- Eigenvectors ONLY get scaled — they stay on the same line
- The eigenvalue tells you how much stretching happens

For PCA: the eigenvectors of the covariance matrix are the directions of maximum variance in your data. The largest eigenvalue corresponds to the direction with the most "spread."

**Key Insight**: Eigenvectors are the "natural axes" of a transformation. PCA finds the natural axes of your data's variance.

**Tags**: `#linear-algebra` `#pca` `#interview-relevant`

---

### Q: Why does SVD matter for machine learning?

**Context**: Seeing SVD used in dimensionality reduction, recommender systems, and image compression.

**Answer**: 
SVD decomposes any matrix A into A = UΣVᵀ where:
- U = left singular vectors (patterns in rows/samples)
- Σ = singular values (importance of each pattern)
- Vᵀ = right singular vectors (patterns in columns/features)

ML applications:
1. **Dimensionality reduction**: Keep top-k singular values → low-rank approximation
2. **Recommender systems**: Decompose user-item matrix → find latent factors
3. **Image compression**: Keep top-k components → reconstruct with less data
4. **Noise reduction**: Small singular values ≈ noise, remove them
5. **LoRA fine-tuning**: Low-rank weight updates (ΔW = AB) are inspired by SVD thinking

**Key Insight**: SVD gives you the "most important patterns" in any data matrix, ranked by importance. Keeping the top-k patterns is the optimal rank-k approximation (Eckart-Young theorem).

**Tags**: `#linear-algebra` `#svd` `#dimensionality-reduction` `#lora` `#interview-relevant`

---

### Q: What's the difference between dot product and matrix multiplication, intuitively?

**Context**: Implementing from scratch in NumPy, trying to build intuition beyond just "multiply and add."

**Answer**: 
- **Dot product** (two vectors): Measures how much two vectors point in the same direction. Result is a scalar. If dot product is 0, vectors are perpendicular (orthogonal).
  
- **Matrix multiplication** (matrix × vector): Applies a linear transformation — rotates, scales, and/or shears the vector.

- **Matrix × matrix**: Composition of two transformations. AB means "first apply B, then apply A."

In ML:
- Dot product → similarity (cosine similarity in embeddings, attention scores)
- Matrix multiply → linear layers in neural networks (Wx + b)

**Key Insight**: Every linear layer in a neural network is just matrix multiplication — a learned transformation. Attention is dot products between queries and keys.

**Tags**: `#linear-algebra` `#neural-networks` `#attention` `#interview-relevant`

---

<!-- 
ADD MORE Q&A BELOW 
Use format:
### Q: [Question]
**Context**: [When this came up]
**Answer**: [Explanation]
**Key Insight**: [One-line takeaway]
**Tags**: `#tag1` `#tag2`
-->
