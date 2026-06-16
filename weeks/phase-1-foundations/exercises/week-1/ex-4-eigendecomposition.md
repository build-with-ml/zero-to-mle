# Exercise 4: Eigendecomposition

## Objective
Implement power iteration to find eigenvalues/eigenvectors, and visually understand what they mean.

## What to Implement

```python
def power_iteration(A, num_iterations=100):
    """Find the largest eigenvalue and its eigenvector using power iteration.
    
    Algorithm:
    1. Start with random vector b
    2. Repeat: b = A @ b / ||A @ b||
    3. Eigenvalue = bᵀ @ A @ b
    """
    pass
```

## Steps

1. Implement power iteration (finds LARGEST eigenvalue/eigenvector)
2. Test on known matrix: `A = [[2, 1], [1, 3]]` — verify against `np.linalg.eig`
3. Extend: find ALL eigenvalues using deflation (subtract out each found eigenpair)
4. Test convergence: plot `|estimated_eigenvalue - true_eigenvalue|` vs iteration

## Visualize

The key visualization (this is the "aha!" moment):
1. Pick a 2×2 matrix with real eigenvalues
2. Plot 20 random unit vectors
3. Apply the matrix to each vector
4. **Show**: Most vectors get rotated AND scaled. Eigenvectors ONLY get scaled (stay on same line).
5. Draw the eigenvectors as thick arrows — they're the "fixed directions" of the transformation

```python
# Pseudocode for visualization
for v in random_unit_vectors:
    Av = A @ v
    plot_arrow(origin, v, color='blue')      # original
    plot_arrow(origin, Av, color='red')      # transformed

# Eigenvectors stay on same line (just scaled)
plot_arrow(origin, eigvec, color='green', linewidth=3)
plot_arrow(origin, eigenval * eigvec, color='green', linewidth=3)
```

## Test Criteria

```python
eigenvalues, eigenvectors = np.linalg.eig(A)

# Your power iteration should find the largest eigenvalue
assert np.isclose(your_eigenvalue, max(eigenvalues), atol=1e-6)

# Your eigenvector should be parallel to numpy's (might be flipped sign)
assert np.isclose(abs(np.dot(your_eigvec, true_eigvec)), 1.0, atol=1e-6)
```

## Questions to Answer

1. Why does power iteration converge to the LARGEST eigenvalue?
2. What happens if the two largest eigenvalues have the same magnitude?
3. How do eigenvalues relate to PCA? (hint: covariance matrix eigenvalues = variance along each PC)

## Connection to ML

- **PCA**: Eigenvectors of covariance matrix = principal components
- **Google PageRank**: Eigenvector of the web's link matrix
- **Spectral clustering**: Uses eigenvectors of the graph Laplacian
- **Stability of training**: Eigenvalues of the Hessian tell you about the loss landscape
