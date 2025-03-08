# **Different Types of Normalization in Machine Learning**

Normalization is a **feature scaling technique** that transforms numerical data into a **standardized range** to improve model performance.

---

## **📌 Why Normalize Data?**
- **Ensures all features contribute equally** to the model.
- **Speeds up convergence** of machine learning algorithms.
- **Improves performance** of distance-based models (e.g., KNN, SVM, K-Means).
- **Reduces bias** caused by features with different scales.

---

## **📊 Different Types of Normalization**

### **1️⃣ Min-Max Normalization (Feature Scaling)**
- **Formula:**  
  \[
  X_{\text{normalized}} = \frac{X - X_{\min}}{X_{\max} - X_{\min}}
  \]
- **Scales values between a fixed range** (commonly `[0,1]` or `[-1,1]`).
- **Sensitive to outliers** because extreme values affect \( X_{\min} \) and \( X_{\max} \).

✅ **Use When:**  
- Data should be in a **specific range** (e.g., **image pixel values [0,255] → [0,1]**).
- Used in **deep learning, KNN, K-Means, SVM**.


### **2️⃣ Mean Normalization**
- **Formula:**  
  \[
  X_{\text{normalized}} = \frac{X - \mu}{X_{\max} - X_{\min}}
  \]
- **Centers the data around 0** but keeps it within a bounded range.  
- **Less common than Min-Max scaling**.

✅ **Use When:**  
- You want **centered data (mean = 0)** while keeping it within a range.

### **3️⃣ Z-score Normalization (Standardization)**

- **Formula:**  
  \[
  X_{\text{standardized}} = \frac{X - \mu}{\sigma}
  \]
- **Centers data at 0** with a **standard deviation of 1**.  
- **Not bound to a specific range**, making it **less sensitive to outliers**.

✅ **Use When:**  
- Data follows a **normal distribution**.  
- Used in **Linear Regression, Logistic Regression, PCA, SVM**.

### **4️⃣ Unit Vector Normalization (L2 Normalization)**

- **Formula:**  
  \[
  X_{\text{normalized}} = \frac{X}{\|X\|}
  \]
- **Scales data** so that **each sample has a unit norm (length = 1)**.  
- Common in **text processing (TF-IDF)** and **cosine similarity calculations**.

✅ **Use When:**  
- Data should be transformed into **unit vectors** for **angle-based distance calculations**.  
- Used in **NLP, information retrieval, and clustering**.

### **5️⃣ Log Normalization (Log Transform)**

- **Formula:**  
  \[
  X_{\text{normalized}} = \log(X + 1)
  \]
- **Reduces skewness** in **right-skewed (positively skewed) data**.  
- Useful for **datasets with a wide range of values**.

✅ **Use When:**  
- Data has a **right-skewed distribution** (e.g., **income, sales**).  
- Applied in **financial, economic, and biological datasets**.

### **🔑 Choosing the Right Normalization Technique**

| **Scenario**                                      | **Best Normalization Method**            |
|--------------------------------------------------|-----------------------------------------|
| Data has different ranges                        | Min-Max Scaling                        |
| Data should have mean = 0, std = 1               | Z-score Normalization (Standardization) |
| Data should have unit norm (vector length = 1)  | Unit Vector Normalization (L2)         |
| Data is right-skewed (e.g., income, sales)      | Log Normalization                      |
| Data has many outliers                          | Robust Scaling                         |


