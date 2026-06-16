# Exercise 6: PCA from Scratch

## Objective
Implement PCA without sklearn — understand every step of dimensionality reduction.

## What to Implement

```python
class PCAFromScratch:
    def __init__(self, n_components):
        self.n_components = n_components
        self.components = None      # eigenvectors (principal directions)
        self.explained_variance = None
        self.mean = None
    
    def fit(self, X):
        """Compute principal components from data X (n_samples, n_features)."""
        # 1. Center the data (subtract mean)
        # 2. Compute covariance matrix
        # 3. Compute eigenvalues/eigenvectors of covariance matrix
        # 4. Sort by eigenvalue (descending)
        # 5. Keep top n_components
        pass
    
    def transform(self, X):
        """Project X onto the principal components."""
        pass
    
    def inverse_transform(self, X_reduced):
        """Reconstruct from reduced representation."""
        pass
```

## Steps

1. Implement the class above
2. Test on Iris dataset (4D → 2D):
   - Fit PCA
   - Transform data to 2D
   - Plot scatter colored by species
3. Test on MNIST (784D → 2D):
   - Reduce 28×28 images to 2 dimensions
   - Plot scatter colored by digit (0–9)
4. Reconstruction: reduce MNIST to k components, then inverse_transform back to 784D
   - Show reconstructed digit images for k = 2, 10, 50, 100, 200

## Visualize

1. **Iris 2D scatter**: 3 species should form visible clusters
2. **MNIST 2D scatter**: 10 digits as colored clusters
3. **Explained variance ratio**: Bar chart of variance per component + cumulative line
4. **Reconstruction grid**: Original digit → k=2 → k=10 → k=50 → k=100 (getting better)
5. **Scree plot**: Eigenvalues in decreasing order — find the "elbow"

## Test Criteria

```python
from sklearn.decomposition import PCA

# Your implementation should match sklearn
sklearn_pca = PCA(n_components=2).fit(X)
your_pca = PCAFromScratch(n_components=2).fit(X)

# Explained variance should match
assert np.allclose(
    your_pca.explained_variance, 
    sklearn_pca.explained_variance_, 
    atol=1e-6
)

# Transformed data should match (up to sign flip — eigenvectors can be ±)
X_yours = your_pca.transform(X)
X_sklearn = sklearn_pca.transform(X)
assert np.allclose(abs(X_yours), abs(X_sklearn), atol=1e-6)
```

## Questions to Answer

1. How many components do you need to capture 95% of MNIST's variance?
2. What does the first principal component "look like" for MNIST? (reshape to 28×28 and display)
3. Why do we center the data before PCA?
4. What's the relationship between PCA and SVD? (hint: they give the same result)
5. When would you use PCA in a real ML pipeline? When would you NOT?

## Connection to ML

- **Dimensionality reduction** → preprocessing before training (faster, less overfitting)
- **Visualization** → reduce any high-dim data to 2D for exploratory analysis
- **Compression** → store data more efficiently (same idea as SVD on images)
- **Feature extraction** → PCA components can be features for downstream models
- **Whitening** → PCA + scaling to unit variance (used in some preprocessing pipelines)
