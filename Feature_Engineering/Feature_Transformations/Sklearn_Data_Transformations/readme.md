# **Data Transformations in Scikit-learn**  

Data transformations in Scikit-learn are preprocessing techniques used to **modify the distribution of data, handle skewness, and improve the performance** of machine learning models. This process ensures that data is not just fed to the model but is **crafted and tailored** to enhance its predictive prowess. By applying **mathematical or custom functions**, we transform raw data into a more suitable format, improving **model accuracy, handling outliers, and ensuring algorithms like linear regression, k-means clustering, and PCA perform optimally**.  

---

## **Why Do We Need to Use Data Transformation?**  

Machine learning models perform best when data is **well-distributed** and follows a **normal distribution** (Gaussian curve). However, real-world data is often **skewed**, meaning values are concentrated more on one side.  

### **What is Normal Distribution?**  
- The **normal distribution** is a **bell-shaped curve** that is **symmetrical around its mean**.  
- It is widely used in **machine learning and statistics** because many natural phenomena follow this pattern.  
- **Key properties**: **Mean ≈ Median ≈ Mode**  

### **What Happens When Data is Skewed?**  
- **Right-Skewed (Positive Skew)**: More values are on the **left**, and extreme values (**outliers**) pull the **mean higher than the median**.  
- **Left-Skewed (Negative Skew)**: More values are on the **right**, and extreme values pull the **mean lower than the median**.  

### ** Why is Skewed Data a Problem?**  
- **ML models learn from patterns**, and extreme values can **bias predictions**.  
- Algorithms like **linear regression, k-means, and PCA** assume **normal distribution** for **optimal performance**.  
- **Transformations help** in making data **balanced and fair**, improving **model accuracy**.  

---

## **Types of Data Transformations**  

1. **Function Transformations**: Use **mathematical functions** (e.g., **log, sqrt**) to modify data distribution.  
2. **Power Transformations**: Apply **exponentiation** (**Box-Cox, Yeo-Johnson**) to **normalize skewed data**.  

**Goal:** Ensure the model sees the **full story** instead of being influenced by extreme values, leading to **better learning and predictions**. 🚀  
