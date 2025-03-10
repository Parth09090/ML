# **Missing Category Imputation**  
Missing category imputation replaces missing categorical values with a placeholder like `"Missing"` or `"Unknown"` instead of estimating them.

## **Advantages** 
- **Preserves Data Integrity** – No row deletion, keeps all observations.  
- **Prevents Bias** – Avoids distorting category distribution like mode imputation.  
- **Works for Any Cardinality** – Suitable for both low and high unique category counts.  
- **Retains Missing Information** – Allows models to recognize missingness as a separate category.  

## **Disadvantages**   
- **May Introduce Noise** – If missing values are not meaningful, treating them as a separate category can mislead models.  
- **Less Effective for Ordinal Data** – Doesn't work well when categorical values have an inherent order.  
- **May Require Extra Handling** – Some models may interpret `"Missing"` as a regular category, affecting predictions.  

### **Best for:**  
 Situations where missing values may carry meaning.  
 Features with high cardinality where mode imputation is unsuitable.  

### **Avoid when:**  
 The missingness is purely random and has no pattern.  
 The categorical variable has a strict ordinal relationship.  

Need a better approach for your data? 🚀  
