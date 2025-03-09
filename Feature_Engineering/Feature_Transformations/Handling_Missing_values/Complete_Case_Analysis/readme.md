# **Complete Case Analysis (Listwise Deletion)**  

## **What is Complete Case Analysis?**  
Complete Case Analysis (CCA), also known as **listwise deletion**, involves removing any row (observation) that contains missing values from the dataset. Only rows with no missing data are used for analysis.  

## **When to Apply?**  
- When the dataset has very few missing values (less than 5-10%).  
- When missing data is **completely random** (Missing Completely at Random - MCAR), meaning the missingness does not depend on observed or unobserved data.  
- When removing missing values does not significantly reduce the sample size.  
- Distribution remains nearly same before and after.
## **Advantages**  
 **Simple & Easy:** No complex imputation techniques are required.  
 **Prevents Bias:** If data is missing completely at random (MCAR), removing missing values does not introduce bias.  
 **Compatible with Most Models:** Works with standard machine learning and statistical models without additional preprocessing.  

## **Disadvantages**  
 **Data Loss:** Can significantly reduce the dataset size, leading to lower statistical power.  
 **Biased Results:** If data is not missing completely at random, removing rows can introduce bias.  
 **Not Suitable for Large Missing Data:** If many rows have missing values, this method may not be practical as it could result in losing too much valuable data.  
