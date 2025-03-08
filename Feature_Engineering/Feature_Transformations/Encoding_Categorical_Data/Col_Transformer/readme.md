# ColumnTransformer in Scikit-Learn

## **What is ColumnTransformer?**
`ColumnTransformer` is a feature transformation tool in Scikit-Learn that allows applying different preprocessing techniques to specific columns in a dataset. It is useful when handling mixed data types (categorical and numerical) in a single transformation pipeline.

## **Why Use ColumnTransformer?**
- Enables applying multiple transformations to different columns in **one step**.
- Prevents **data leakage** by ensuring consistent transformations during training and testing.
- Works seamlessly with **Scikit-Learn Pipelines**.
- Helps in handling **both numerical and categorical data** efficiently.

## **How Does ColumnTransformer Work?**
1. Define the transformations for different column types.
2. Pass them into `ColumnTransformer` along with the column names.
3. Apply `fit_transform()` to preprocess the data.

## **Example: Applying One-Hot Encoding and Scaling**

```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder, StandardScaler
import numpy as np
import pandas as pd

# Sample Data
data = {
    'brand': ['Toyota', 'Honda', 'Ford', 'BMW'],
    'km_driven': [50000, 30000, 70000, 20000],
    'price': [15000, 12000, 18000, 25000]
}
df = pd.DataFrame(data)

# Define ColumnTransformer
preprocessor = ColumnTransformer(
    transformers=[
        ('ohe', OneHotEncoder(drop='first'), ['brand']),  # One-Hot Encoding
        ('scaler', StandardScaler(), ['km_driven'])       # Standard Scaling
    ],
    remainder='passthrough'  # Keeps 'price' column unchanged
)

# Apply Transformations
X_train_final = preprocessor.fit_transform(df)

# Convert to DataFrame with Correct Column Names
ohe_categories = preprocessor.named_transformers_['ohe'].get_feature_names_out(['brand'])
columns = np.concatenate((ohe_categories, ['km_driven', 'price']))
df_new = pd.DataFrame(X_train_final, columns=columns)

print(df_new)
```
