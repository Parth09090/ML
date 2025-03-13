# Principal Component Analysis (PCA) – When to Use & When Not to Use  

## When to Use PCA?  
 **Dimensionality Reduction:** Useful when dealing with high-dimensional data with redundant features.  
 **Noise Reduction:** Helps remove unnecessary variations while preserving important patterns.  
 **Visualization:** Converts high-dimensional data into **2D or 3D** for easy visualization.  
 **Feature Extraction:** Transforms correlated features into uncorrelated **principal components**.  
 **Improving Model Efficiency:** Reducing features speeds up model training and inference.  

---

## When Not to Use PCA?  
 **When Interpretability Matters:** PCA transforms features into principal components, making interpretation difficult.  
 **When Features Have Clear Meaning:** If each feature carries crucial standalone meaning, PCA may remove important insights.  
 **When Data is Not Linearly Correlated:** PCA works best when features are linearly related; otherwise, it may not be effective.  
 **When Model Performance Decreases:** Sometimes, reducing dimensions removes valuable information, leading to lower accuracy.  

---

## Example: Applying PCA on the MNIST Dataset (Handwritten Digits Classification)  

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score
from sklearn.datasets import fetch_openml
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Load MNIST dataset
mnist = fetch_openml('mnist_784', version=1)
X, y = mnist.data, mnist.target

# Split into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Standardize data
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Apply PCA (reduce to 50 principal components)
pca = PCA(n_components=50)
X_train_pca = pca.fit_transform(X_train)
X_test_pca = pca.transform(X_test)

# Train a KNN classifier
knn = KNeighborsClassifier(n_neighbors=5)
knn.fit(X_train_pca, y_train)

# Predict and calculate accuracy
y_pred = knn.predict(X_test_pca)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy with PCA (50 components): {accuracy:.4f}")
```
