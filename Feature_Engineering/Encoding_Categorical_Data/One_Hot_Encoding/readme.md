# Why Not Use Ordinal Encoding for Nominal Data?

Ordinal encoding assigns numerical values (0, 1, 2, …) to categories, implying a meaningful order or ranking. However, nominal data has no inherent order, so applying ordinal encoding introduces a false numerical relationship.

For example, if colors are encoded as **Red → 0, Blue → 1, Green → 2**, a model might interpret this as **Green > Blue > Red**, which is incorrect.

This can negatively affect models like **linear regression, SVM, and neural networks**, which may assume a relationship between encoded values.

Instead, **one-hot encoding** is preferred for nominal data since it represents each category as a separate binary variable, avoiding misleading assumptions.

---

# One-Hot Encoding (OHE)

**One-Hot Encoding (OHE)** is a technique used to convert categorical data into a numerical format that machine learning models can understand. It represents each category as a **binary vector**, ensuring that no false ordinal relationships are introduced.

## How One-Hot Encoding Works

For a categorical feature with **N unique categories**, OHE creates **N binary columns**, where each column represents a category. A value of **1** indicates the presence of a category, while **0** indicates its absence.

For example, if we have a feature **"Color"** with three categories (**Red, Blue, Green**), one-hot encoding would transform it as follows:

| Color  | Red | Blue | Green |
|--------|-----|------|-------|
| Red    |  1  |  0   |  0    |
| Blue   |  0  |  1   |  0    |
| Green  |  0  |  0   |  1    |

## Why Use One-Hot Encoding?

- **Prevents false ordinal relationships** (unlike label or ordinal encoding).
- **Works well for nominal categorical data** (categories with no inherent order).
- **Essential for models that assume numerical relationships** (e.g., linear regression, neural networks).
- **Commonly used in deep learning and tree-based models** like decision trees and random forests.

## Potential Issues & Solutions

### 1. High Cardinality (Too Many Categories)
- OHE creates **many new columns** for features with a large number of unique values, increasing memory usage.
- **Solution**: Use **target encoding** or **embedding layers** for high-cardinality data.

### 2. Dummy Variable Trap (Redundant Features)
- The dummy variable trap is a problem that occurs when one-hot encoding creates multicollinearity, meaning one feature is completely determined by the others. This happens because all encoded columns are linearly dependent, which can confuse regression-based models.
- If all one-hot encoded columns are used, they sum to **1**, making one column redundant.
- This leads to perfect multicollinearity, where one variable is a linear combination of the others, causing issues in models like linear regression. 
- **Solution**: Use `drop_first=True` in `pandas.get_dummies()` to remove one column and avoid multicollinearity.

---

# One-Hot Encoding Using Most Frequent Variables

In cases where a categorical feature has **too many unique values** (high cardinality), **one-hot encoding** can create **too many columns**, making the dataset sparse and increasing memory usage. A common solution is to **encode only the most frequent categories** and group the rest into an "Other" category.

## Why Use Most Frequent Variables in OHE?

- **Reduces dimensionality** by limiting the number of new columns.  
- **Prevents overfitting** in models by avoiding unnecessary sparse features.  
- **Improves computational efficiency** by reducing memory usage and training time.  

## Steps to Perform OHE with Most Frequent Categories  

1. **Identify the top N most frequent categories** in a feature.  
2. **One-hot encode only these N categories**, treating less frequent ones as "Other."  


