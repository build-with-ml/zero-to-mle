# Exercise 5: SVD & Image Compression

## Objective
Use SVD to compress an image and visually show the quality-vs-compression tradeoff.

## Steps

1. Load a grayscale image as a NumPy matrix (use any photo, or `sklearn.datasets.load_sample_image`)
2. Compute SVD: `U, S, Vt = np.linalg.svd(image, full_matrices=False)`
3. Reconstruct using only top-k singular values:
   ```python
   def reconstruct(U, S, Vt, k):
       return U[:, :k] @ np.diag(S[:k]) @ Vt[:k, :]
   ```
4. Try k = 1, 5, 10, 20, 50, 100, 200
5. For each k, compute:
   - Compression ratio: `(m*k + k + k*n) / (m*n)`
   - Reconstruction error: `np.linalg.norm(original - reconstructed) / np.linalg.norm(original)`

## Visualize

Create a grid showing:
- Row 1: Reconstructed images for k = 1, 5, 10, 20, 50, 100, original
- Row 2 (optional): Difference images (what's lost at each k)
- Separate plot: Error vs k, with compression ratio on secondary y-axis
- Separate plot: Cumulative energy (sum of top-k singular values / sum of all) — find k for 90%, 95%, 99%

## Test Criteria

- k = rank(image) should perfectly reconstruct (error ≈ 0)
- k = 1 should show only the dominant pattern
- Compression ratio should decrease as k increases

## Questions to Answer

1. How many singular values capture 90% of the image's "information"?
2. What does the first singular value/vector represent visually?
3. Why is SVD the OPTIMAL rank-k approximation? (Eckart-Young theorem)
4. How does this relate to LoRA in LLM fine-tuning? (ΔW = A×B is a low-rank matrix)

## Connection to ML

- **LoRA fine-tuning**: Instead of updating a full weight matrix (m×n), update two small matrices (m×k) and (k×n) — same idea as SVD truncation
- **Embedding compression**: Reduce embedding dimensions while preserving most information
- **Noise reduction**: Small singular values ≈ noise. Truncating them denoises.
- **Recommender systems**: SVD on user-item matrix finds latent factors
