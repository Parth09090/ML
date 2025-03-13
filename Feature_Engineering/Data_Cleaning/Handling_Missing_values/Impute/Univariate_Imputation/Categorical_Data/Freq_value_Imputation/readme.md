# **Frequent Value (Mode) Imputation**  
Mode imputation replaces missing categorical values with the most frequent category in a feature.  

## **Advantages** ✅  
- **Simple & Fast** – Easy to implement with low computational cost.  
- **Preserves Data** – No row deletion, maintains categorical integrity.  
- **Effective for Low-Cardinality Features** – Works well when few unique values exist.  

## **Disadvantages** ❌  
- **Introduces Bias** – Over-represents the most frequent category.  
- **Ignores Feature Relationships** – Doesn't account for dependencies between features.  
- **Ineffective for High-Cardinality Data** – Doesn't work well with many unique categories.  

### **Best for:**  
Low-cardinality categorical data with randomly missing values.  

### **Avoid when:**  
 Data is missing systematically or has high cardinality.  

