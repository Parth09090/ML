### **Power Transformer**  
A **Power Transformer** is used to make data more **normally distributed** by reducing **skewness** and **stabilizing variance**. It is useful for models like **linear regression, k-means, and PCA**, which assume normally distributed data.  

#### **Types of Power Transformation:**  
1. **Box-Cox Transformation** – Works **only for positive values**.  
2. **Yeo-Johnson Transformation** – Works for **both positive and negative values**.  

---

### **Box-Cox Transformation**  
Transforms **right-skewed data** to make it more symmetric.  

#### **Formula:**  

- If `λ ≠ 0`: `y = (x^λ - 1) / λ`
- If `λ = 0`: `y = log(x)` 

✅ **Only for positive values**  
✅ **Stabilizes variance and normalizes distribution**  

---

### **Yeo-Johnson Transformation**  
Extends Box-Cox to handle **zero and negative values**.  

#### **Formula:**  
- If `x ≥ 0`:
  - `y = ((x + 1)^λ - 1) / λ`, if `λ ≠ 0`
  - `y = log(x + 1)`, if `λ = 0`
- If `x < 0`:
  - `y = ((1 - x)^(2 - λ) - 1) / (2 - λ)`, if `λ ≠ 2`
  - `y = -log(1 - x)`, if `λ = 2` 

✅ **Works for both positive and negative values**  
✅ **Handles zero values effectively**  

---

### **Comparison**  

| Transformation  | Works for | Best Used For |
|---------------|-----------|---------------|
| **Box-Cox**   | Positive values only | Right-skewed data |
| **Yeo-Johnson** | Positive & negative values | Data with zeros/negatives |

Both are implemented in **scikit-learn’s** `PowerTransformer` for preprocessing data before applying machine learning models.
