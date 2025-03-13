# **Multivariate Imputation by Chained Equations (MICE) / Iterative Imputation**  
Multivariate Imputation by Chained Equations (MICE), also known as **Iterative Imputation**, is an advanced method for handling missing data by modeling each missing feature as a function of the others.  

---

## **How It Works**  
1. **Initial Guess** → Missing values are initially replaced using a simple imputation method (e.g., mean, median).  
2. **Iterative Modeling** → Each feature with missing values is modeled as a dependent variable using the remaining features as predictors.  
3. **Predict & Update** → The missing values are predicted and updated iteratively, refining the imputation.  
4. **Repeat Until Convergence** → The process is repeated until values stabilize or a set number of iterations is reached.  

---

## **Key Benefits**   
- **Considers relationships between variables** → Unlike mean/mode imputation, it models dependencies.  
- **Works well with numerical and categorical data** → Can handle mixed data types.  
- **Handles large proportions of missing data** → More robust than simpler methods.  
- **Reduces bias** → Avoids artificially reducing variability in the dataset.  

---

## **Disadvantages**   
- **Computationally expensive** → Iterative modeling increases processing time.  
- **Sensitive to model choice** → Performance depends on the regression model used for imputation.  
- **Can introduce noise** → Poorly chosen predictors may lead to inaccurate imputations.  
- **Risk of overfitting** → Especially in small datasets with many missing values.  

---

## **When to Apply?** 
- When missing values are **not completely random** and can be predicted using other variables.  
- When working with **complex datasets** where variables have strong interdependencies.  
- When using **regression-based models**, as MICE preserves relationships between variables.  

---

## **Example Usage in Python (Using Sklearn)**  
```python
import numpy as np
import pandas as pd
from sklearn.impute import IterativeImputer
from sklearn.ensemble import RandomForestRegressor

# Sample dataset with missing values
data = {
    'Age': [25, np.nan, 30, np.nan, 45, 50, np.nan],
    'Salary': [50000, 60000, np.nan, 80000, np.nan, 70000, 90000]
}
df = pd.DataFrame(data)

# Initialize Iterative Imputer with a regression model (Random Forest)
iter_imputer = IterativeImputer(estimator=RandomForestRegressor(), max_iter=10, random_state=42)

# Apply imputation
df_imputed = pd.DataFrame(iter_imputer.fit_transform(df), columns=df.columns)

print(df_imputed)
```
