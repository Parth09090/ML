# **Random Value Imputation**  
Random value imputation replaces missing values with randomly selected values from the **same feature's existing (non-missing) values**.

## **When to Apply?** 
- When missing values are **randomly distributed** (MCAR - Missing Completely At Random).  
- When keeping the **original distribution** of the feature is important.  
- When **variability** in imputed values is desired instead of a fixed mean/mode.  

## **Advantages**  
- **Preserves feature distribution** – Imputed values come from real data points.  
- **Introduces variability** – Unlike mean/mode imputation, it prevents overuse of a single value.  
- **Simple and easy to implement** – No need for complex models.  

## **Disadvantages**  
- **Inconsistent results** – Each run may yield different imputed values unless a fixed seed (`random_state`) is used.  
- **Not suitable for structured patterns** – If missing values follow a specific trend, random imputation can misrepresent the data.  
- **Might add noise** – Can lead to misleading patterns if too many values are missing.  

---

## **Problem with Random Sampling for Missing Value Imputation**  
If we randomly select values to fill in missing data, every time we run the code, we might get **different results**. This makes our model **inconsistent** because the same missing value can be replaced with different numbers each time.

### **Solution: Using a Fixed Seed (`random_state`)**  
We **control** randomness by using a fixed number (seed) based on something in the data. In this case, we use:  
```python
sampled_value = X_train['Age'].dropna().sample(1, random_state=int(observation['Fare']))
```
This means:
- If two rows have the same Fare, they will always get the same imputed Age.Running the code multiple times will always give the same results for missing values.

Why This Works?
- Without random_state → Different Age values every time → Inconsistent model
- With random_state=int(observation['Fare']) → Same missing values get the same Age → Stable model
