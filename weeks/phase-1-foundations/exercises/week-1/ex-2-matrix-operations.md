# Exercise 2: Matrix Operations

## Objective
Implement core matrix operations from scratch — understand what happens inside `np.matmul`.

## What to Implement

```python
def matrix_multiply(A, B):
    """Multiply two matrices. Return A @ B."""
    pass

def transpose(A):
    """Transpose a matrix."""
    pass

def determinant_2x2(A):
    """Compute determinant of a 2x2 matrix."""
    pass

def determinant_3x3(A):
    """Compute determinant of a 3x3 matrix using cofactor expansion."""
    pass

def inverse_2x2(A):
    """Compute inverse of a 2x2 matrix using adjugate formula."""
    pass

def is_invertible(A):
    """Check if a matrix is invertible (det != 0)."""
    pass
```

## Steps

1. Start with the triple nested loop for matrix multiply:
   ```python
   for i in range(rows_A):
       for j in range(cols_B):
           for k in range(cols_A):
               C[i][j] += A[i][k] * B[k][j]
   ```
2. Then optimize using NumPy broadcasting (eliminate the inner loop)
3. Implement determinant recursively (base case: 2×2)
4. Implement 2×2 inverse: A⁻¹ = (1/det) × [[d, -b], [-c, a]]

## Test Criteria

```python
A = np.random.randn(4, 3)
B = np.random.randn(3, 5)

assert np.allclose(your_matmul(A, B), np.matmul(A, B))
assert np.allclose(your_inverse_2x2(M), np.linalg.inv(M))  # for 2x2 M
assert np.isclose(your_det_3x3(M), np.linalg.det(M))       # for 3x3 M
```

## Visualize

- Time your triple-loop vs NumPy `@` operator for increasing matrix sizes (10×10 to 1000×1000)
- Plot execution time vs matrix size — show why NumPy's BLAS is critical

## Connection to ML

- **Matrix multiply** → every linear layer in a neural network (Y = XW + b)
- **Inverse** → normal equation for linear regression: θ = (XᵀX)⁻¹Xᵀy
- **Determinant** → measures how a transformation scales volume (0 = singular/non-invertible)
