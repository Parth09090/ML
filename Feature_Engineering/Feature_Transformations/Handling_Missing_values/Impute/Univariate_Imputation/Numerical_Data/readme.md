## **Types of Univariate Imputation for Numerical Data**  

Univariate imputation replaces missing values in a single feature **without considering other features**. Below are the main types for numerical data:  

### **1. Mean & Median Imputation**  
- **Mean Imputation:** Replace missing values with the **average** (mean) of the column.  
  - Works well for **normally distributed** data.  
  - Affected by **outliers**, which can skew the imputed values.  
- **Median Imputation:** Replace missing values with the **middle value** (median).  
  - Preferred for **skewed distributions** or data with **outliers**.  

### **2. Arbitrary Value Imputation**  
- Missing values are replaced with a specific **constant value** (e.g., -999, 0, or 99).  
- Useful when missing values have **a specific meaning** (e.g., "unknown" or "not applicable").  
- Can introduce **bias** if the chosen value influences model predictions.  

### **3. End-Value Imputation**  
- Replace missing values with **the lowest or highest value** in the dataset.  
- Used when missing values **represent extreme cases** (e.g., income data where missing values may indicate either the richest or the poorest individuals).  
- Helps distinguish missing values from normal values but **can distort distributions**.  

### **When to Use Each Method?**  
| **Method**  | **Best For** | **Limitations** |
|-------------|-------------|-----------------|
| **Mean**  | Normally distributed data | Sensitive to outliers |
| **Median**  | Skewed data, data with outliers | May not always reflect actual missing values |
| **Arbitrary**  | When missing values have a distinct meaning | Introduces artificial values |
| **End-Value**  | When missing values likely belong to extremes | Can distort distributions |

For a more robust approach, consider **multivariate imputation** when missing values depend on multiple variables.

