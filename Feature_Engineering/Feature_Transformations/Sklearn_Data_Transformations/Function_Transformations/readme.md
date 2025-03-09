# **Function Transformations in Scikit-learn**  

Function transformations apply **mathematical functions** to modify data distributions, handle skewness, and improve model performance. Common transformations include **log, reciprocal, square, and square root**.

---

## **1. Log Transformation**  
🔹 **Purpose:** Reduces the impact of extreme values, making data more interpretable and suitable for modeling.  
🔹 **Formula:** `y = log_e(x)`  
🔹 **Key Points:**  
✅ Helps approximate a normal distribution but doesn’t ensure it.  
✅ Works well for **right-skewed data**.  
✅ Cannot be applied to **negative or zero values**.  

---

## **2. Reciprocal Transformation**  
🔹 **Purpose:** Used when large values dominate a dataset, helping to **scale them down**.  
🔹 **Formula:** `y = 1/x`  
🔹 **Key Points:**  
✅ Works well for **right-skewed data**.  
✅ Not defined for **zero values**.  
✅ Reverses the order of positive numbers (small values become larger).  

---

## **3. Square Transformation**  
🔹 **Purpose:** Spreads out data, reducing skewness and making distributions more symmetrical.  
🔹 **Formula:** `y = x^2`  
🔹 **Key Points:**  
✅ Useful for **left-skewed data**.  
✅ Squaring negative values results in positive values.  
✅ Can amplify differences, so careful application is needed.  

---

## **4. Square Root Transformation**  
🔹 **Purpose:** Helps compress larger values, making right-skewed data more symmetric.  
🔹 **Formula:** `y = sqrt(x)`  
🔹 **Key Points:**  
✅ Works well for **right-skewed data**.  
✅ Weaker than log transformation.  
✅ Defined **only for positive values**.  

---

### **✅ Summary**  
Function transformations adjust data distributions, helping machine learning models learn better. Choosing the right transformation depends on whether the data is **right-skewed or left-skewed** and whether it contains **negative or zero values**. 🚀  
