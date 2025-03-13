## **Handling Missing Values**  

### **What is it & Why do we do it?**  
Handling missing values keeps the dataset accurate and reliable. If we don't address missing data, it can lead to incorrect analysis and predictions. By either filling in the missing values (imputation) or removing them, we ensure the data remains useful and unbiased. Ignoring missing values can distort results and make models less trustworthy.

---

### **Types of Handling Missing Values**  

#### **1. Remove Missing Values**  
- If the missing data is minimal, dropping rows or columns with missing values can be an option.  
- However, this can lead to loss of valuable information.  

#### **2. Impute Missing Values**  
Instead of removing data, we replace missing values with estimated values. Imputation is done in two ways:  

##### **(a) Univariate Imputation** (Uses only one feature)  
- **For Categorical Data:**  
  - **Mode Imputation:** Replace missing values with the most frequent category.  
- **For Numerical Data:**  
  - **Mean/Median Imputation:** Replace with the mean or median of the column.  

##### **(b) Multivariate Imputation** (Uses multiple features)  
- **KNN Imputer:** Estimates missing values based on the nearest neighbors' values.  
- **Iterative Imputer:** Predicts missing values using regression models trained on other features.  

Choosing the right method depends on the dataset, missing value pattern, and impact on model performance. 
