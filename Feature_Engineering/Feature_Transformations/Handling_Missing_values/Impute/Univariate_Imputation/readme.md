## **Univariate Imputation**  

Univariate imputation is a technique for handling missing values where each missing value is **replaced using only one feature (column) at a time**, without considering relationships with other features.  

### **Why Use Univariate Imputation?**  
- It is **simple and fast** to implement.  
- Works well when missing values are **randomly distributed** and do not depend on other features.  
- Helps maintain dataset size by filling missing values instead of removing rows.  

### **Types of Univariate Imputation**  

#### **1. For Numerical Data:**  
- **Mean Imputation:** Replace missing values with the **mean** of the column.  
- **Median Imputation:** Replace missing values with the **median**, useful for skewed data.  
- **Mode Imputation:** Replace with the most frequent value, best for discrete numerical values.  

#### **2. For Categorical Data:**  
- **Mode Imputation:** The missing values are filled with the most frequently occurring category.  

### **Limitations**  
- Does not consider relationships with other features.  
- Can **distort data distribution**, especially for large missing values.  
- Not suitable for datasets where missing values are dependent on multiple factors.  

For more robust imputations that consider multiple features, **multivariate imputation** techniques like **KNN Imputer** or **Iterative Imputer** are preferred.
