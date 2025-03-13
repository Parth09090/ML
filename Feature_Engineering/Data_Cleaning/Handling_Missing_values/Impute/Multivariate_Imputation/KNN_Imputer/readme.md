# **KNN Imputer (K-Nearest Neighbors Imputation)**  
K-Nearest Neighbors (KNN) Imputation replaces missing values by finding **K similar data points (neighbors)** and using their values to estimate the missing ones. It works by measuring the similarity between instances based on their feature values.

---

## **How It Works**  
1. Identify the **K closest neighbors** to the instance with missing values using a distance metric (e.g., Euclidean distance).  
2. Use their values to fill in the missing data.  
   - **Uniform Weights (`weights='uniform'`)** → Each neighbor contributes equally.  
   - **Distance Weights (`weights='distance'`)** → Closer neighbors get more weight, meaning their values have a stronger influence on imputation.  

---

## **Benefits**
- **Captures complex relationships** → Unlike mean/mode imputation, KNN considers patterns in data.  
- **Works well with numerical and categorical data** → Can be adapted using appropriate distance metrics.  
- **Preserves variability** → Imputed values are based on real observations, maintaining distribution.  
- **Does not require assumptions about data distribution** → Unlike mean/median imputation.  

---

## **Disadvantages**
- **Computationally expensive** → Finding K neighbors requires distance calculations for each missing value.  
- **Sensitive to outliers** → Anomalous data points can affect imputed values.  
- **Requires careful selection of K** → Too small K may cause overfitting, too large K may blur differences.  
- **Data must be scaled properly** → Features with large values can dominate distance calculations.  

---

## **Concept of Weights in KNN Imputation**  
KNN uses **two main weighting schemes** to determine how neighbors contribute to the missing value:  

### **1. Uniform Weights (`weights='uniform'`)**  
- All neighbors contribute **equally** to the imputation.  
- Simple but may not fully capture the importance of closer neighbors.  
- Best when **all neighbors are equally relevant** (e.g., evenly distributed data).  

### **2. Distance Weights (`weights='distance'`)**  
- Closer neighbors have **more influence** on imputation than farther ones.  
- Ensures that the most relevant data points contribute the most.  
- Works well when **nearby points are more similar than distant ones**.  

---

## **Example Usage in Python (Using Sklearn)**  
```python
import numpy as np
import pandas as pd
from sklearn.impute import KNNImputer

# Sample dataset with missing values
data = {
    'Age': [25, np.nan, 30, np.nan, 45, 50, np.nan],
    'Salary': [50000, 60000, np.nan, 80000, np.nan, 70000, 90000]
}
df = pd.DataFrame(data)

# Initialize KNN Imputer
knn_imputer = KNNImputer(n_neighbors=3, weights='distance')  # Using weighted distances

# Apply imputation
df_imputed = pd.DataFrame(knn_imputer.fit_transform(df), columns=df.columns)

print(df_imputed)
```
