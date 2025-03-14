# Simple Linear Regression

Simple linear regression is a statistical method used to model the relationship between a dependent variable (\( y \)) and an independent variable (\( x \)) using a straight-line equation:

\[
y = mx + b
\]

where:
- \( y \) = dependent variable (output)
- \( x \) = independent variable (input)
- \( m \) = slope of the line
- \( b \) = intercept

The goal is to find the best values for \( m \) and \( b \) so that the predicted values (\( \hat{y} \)) are as close as possible to the actual values.

## Methods to Find \( m \) and \( b \)

### 1. Ordinary Least Squares (OLS)
OLS is a direct method that finds \( m \) and \( b \) by minimizing the sum of squared differences between actual and predicted values.

The loss function (Mean Squared Error - MSE) is:

*J(m, b) = (1/n) Σ [yᵢ - (m xᵢ + b)]²*

The optimal values of \( m \) and \( b \) can be obtained using the following formulas:

*m = [ n Σ(xy) - Σx Σy ] / [ n Σ(x²) - (Σx)² ]*

*b = ( Σy - m Σx ) / n*

- OLS provides a **closed-form solution**, meaning it directly calculates the optimal parameters without iteration.
- It is computationally efficient for small datasets but can be slow for very large datasets.

---

### 2. Gradient Descent
Gradient descent is an **iterative optimization method** that minimizes the loss function by updating \( m \) and \( b \) in small steps.

1. **Initialize** \( m \) and \( b \) randomly.
2. Compute the gradient (partial derivatives of the loss function):

   *∂J/∂m = (-2/n) Σ [x (y - (m x + b))]*

   *∂J/∂b = (-2/n) Σ [y - (m x + b)]*

3. Update the parameters using the learning rate (\( \alpha \)):

   *m = m - α (∂J/∂m) b = b - α (∂J/∂b)*

4. Repeat until convergence.

- **Pros:** Works well for large datasets where OLS is computationally expensive.
- **Cons:** Requires tuning the learning rate and can get stuck in local minima if not chosen properly.

---

## Comparison: OLS vs. Gradient Descent

| Feature            | OLS                           | Gradient Descent |
|--------------------|-----------------------------|-----------------|
| Solution Type     | Closed-form (exact)         | Iterative (approximate) |
| Computational Cost | Expensive for large data   | Efficient for large data |
| Complexity        | Requires matrix operations | Requires hyperparameter tuning (learning rate, iterations) |
| Convergence Speed | Fast for small data        | Slower, depends on step size |

---

## When to Use Which?
- **OLS**: Best for small to medium datasets where matrix inversion is feasible.
- **Gradient Descent**: Preferred for large datasets or when working with high-dimensional data.
