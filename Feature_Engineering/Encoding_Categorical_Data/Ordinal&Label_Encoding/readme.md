# **1. Label Encoding**

- Assigns a **unique integer** to each category.  
- Does **not** consider any inherent order.  
- Used for **nominal data** (e.g., names, colors, cities).  

---

## **When to Use Label Encoding?**

### **1. For Output (Target) Variables in Classification Problems**
- Many machine learning models (like decision trees, neural networks) require numerical labels for classification tasks.
- **Example**: Converting `"Spam"` and `"Not Spam"` into **0** and **1** for binary classification.

### **2. For Input Features with Low Cardinality (But Not Ordinal Data)**
- It can be used for input features when categories don’t have a meaningful order, **but only if the model doesn't interpret numeric values as ordered**.
- **Example**: Decision trees can handle label encoding well, but **linear models might struggle** if they assume an inherent order in the numbers.
