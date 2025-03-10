# **AddMissingIndicator (Missing Indicator Imputation)**  
The `AddMissingIndicator()` method creates a **binary column** (missing indicator) for each feature, marking whether a value is missing (`1`) or not (`0`). It works for both **categorical and numerical** variables and is commonly used to help machine learning models detect missing patterns.

---

## **How It Works**  
- **Automatically detects missing values** in the dataset.  
- **Creates a new binary column** indicating the presence (`1`) or absence (`0`) of missing data.  
- **Leaves the original feature unchanged** (missing values remain).  
- **Can be applied to selected variables** by specifying them in the `variables` parameter.  
- The `missing_only` parameter controls whether indicators are added for **all variables** or **only those with missing data in the training set**.

---

## **Key Parameters**  
- **`variables`** → List of columns where missing indicators should be added.  
  - If not specified, all variables are considered.  
- **`missing_only` (default: `True`)** → Controls which variables get missing indicators:  
  - `True` → Adds indicators **only for columns with missing values in the train set**.  
  - `False` → Adds indicators **for all selected variables**, even if they have no missing values.  

---

## **Benefits** 
- **Captures missingness patterns** that might be meaningful for the model.  
- **Works well with tree-based models** (e.g., Random Forest, XGBoost).  
- **Does not alter the original data**, avoiding imputation bias.  
- **Can be combined with other imputation methods** to enhance model performance.  

## **When to Apply?** 
- When missing values **may carry meaningful information**.  
- When using **tree-based models**, which can leverage missing indicators.  
- When there are **many missing values**, and other imputation methods might introduce bias.  

## **Disadvantages**   
- **Not always effective for linear models** (e.g., Linear Regression).  
- **Increases dataset size** by adding extra columns.  
- **Does not fill missing values**, so missing data must still be handled separately if needed.  
