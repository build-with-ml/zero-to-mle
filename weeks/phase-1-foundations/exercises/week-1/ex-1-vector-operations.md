# Exercise 1: Vector Operations

## Objective
Implement fundamental vector operations from scratch in NumPy — no `np.dot`, `np.cross`, or sklearn allowed.

## What to Implement

```python
def dot_product(a, b):
    """Compute dot product of two vectors."""
    pass

def cross_product(a, b):
    """Compute cross product of two 3D vectors."""
    pass

def vector_projection(a, b):
    """Project vector a onto vector b."""
    pass

def cosine_similarity(a, b):
    """Compute cosine similarity between two vectors."""
    pass

def vector_norm(a, p=2):
    """Compute Lp norm of a vector."""
    pass
```

## Steps

1. Implement each function using only basic NumPy operations (`+`, `-`, `*`, `sum`)
2. Write test cases with known answers:
   - `dot_product([1,0,0], [0,1,0])` should be `0` (perpendicular)
   - `cosine_similarity([1,1], [1,1])` should be `1.0` (identical direction)
   - `cosine_similarity([1,0], [0,1])` should be `0.0` (perpendicular)
3. Test on 100 random vector pairs: compare your output to NumPy/sklearn

## Test Criteria

```python
from sklearn.metrics.pairwise import cosine_similarity as sklearn_cos

# Generate random vectors
a, b = np.random.randn(100), np.random.randn(100)

# Your implementation should match within floating point tolerance
assert np.isclose(your_dot(a, b), np.dot(a, b))
assert np.isclose(your_cosine(a, b), sklearn_cos([a], [b])[0][0])
```

## Visualize

- Plot two 2D vectors and their projection
- Show angle between vectors, annotate with cosine similarity value
- Create a grid: plot pairs with cos_sim = 1.0, 0.5, 0.0, -0.5, -1.0

## Connection to ML

- **Cosine similarity** → used in embeddings (word2vec, sentence embeddings), search ranking, recommendation systems
- **Dot product** → core of attention mechanism in Transformers (Q·K)
- **Projection** → PCA projects data onto principal components
