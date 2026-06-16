# Exercise 3: Linear Transformations (Visual)

## Objective
See what matrices DO to space — rotation, scaling, shearing — through animation.

## What to Build

A visualization showing how different matrices transform a set of 2D points.

## Steps

1. Create a set of 2D points: unit square vertices, or a grid, or a circle
2. Define transformation matrices:
   ```python
   # Rotation by θ
   rotation = [[cos(θ), -sin(θ)],
               [sin(θ),  cos(θ)]]
   
   # Scaling
   scaling = [[sx, 0],
              [0, sy]]
   
   # Shear
   shear = [[1, k],
            [0, 1]]
   
   # Reflection (across x-axis)
   reflection = [[1,  0],
                 [0, -1]]
   ```
3. Apply each matrix to all points: `new_points = matrix @ points`
4. Plot before and after side-by-side

## Visualize

- Create a 2×4 grid of plots: original → rotation, original → scale, original → shear, original → reflection
- Color-code points so you can track where each point goes
- **Bonus (high engagement)**: Animate the transformation — interpolate between identity matrix and final matrix over 30 frames. Save as GIF.

```python
# Animation hint: interpolate between I and M
for t in np.linspace(0, 1, 30):
    current_matrix = (1-t) * np.eye(2) + t * target_matrix
    transformed = current_matrix @ points
    # plot frame
```

## Test Criteria

- Rotation by 360° returns to original (within floating point)
- Scaling by [1,1] is identity
- Determinant of rotation matrix = 1 (area-preserving)
- Determinant of scaling = sx × sy (area changes by this factor)

## Connection to ML

- **Neural networks apply a sequence of linear transformations** (matrix multiplies) interleaved with non-linearities
- Understanding transformations visually helps debug why networks learn (or don't)
- Attention: Q, K, V are linear projections (transformations) of the input
