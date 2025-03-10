# **Automatic Selection Imputer**  
The **Automatic Selection Imputer** is a technique that **automatically selects an appropriate imputation strategy** for each feature based on its data type or missing patterns. It is commonly used in data preprocessing pipelines to streamline the handling of missing values.

---

## **How It Works**  
- Automatically detects **numerical and categorical** variables.  
- Applies a **predefined imputation strategy** for each variable type:  
  - **Numerical Features** → Typically uses mean, median, or mode imputation.  
  - **Categorical Features** → Uses mode (most frequent) or a placeholder value (e.g., "Missing").  
- The user can specify whether to apply the imputation to **all variables** or **only those with missing values** (`missing_only=True`).  
- Reduces manual effort by automatically identifying and handling missing data.

---

## **Benefits**  
- **Reduces manual work** by selecting the best imputation method automatically.  
- **Ensures consistency** in handling missing values across different variable types.  
- **Works well in automated machine learning (AutoML) pipelines**.  
- **Prevents errors** that might occur when manually selecting imputation strategies.

## **When to Apply?** 
- When working with **large datasets** with mixed data types.  
- When using **automated ML pipelines** where manual imputation selection is impractical.  
- When missing data patterns are **not well understood** at the start of preprocessing.

## **Disadvantages**  
- **Less control** over imputation methods.  
- **Might not be optimal for specific datasets** where a custom strategy is preferred.  
- **May introduce bias** if the automatically chosen strategy does not fit the data distribution.
