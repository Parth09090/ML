# **1. Label Encoding**

- Assigns a **unique integer** to each category.  
- Does **not** consider any inherent order.  
- Used for **nominal data** (e.g., names, colors, cities).  


## **When to Use Label Encoding?**

### **1. For Output (Target) Variables in Classification Problems**
- Many machine learning models (like decision trees, neural networks) require numerical labels for classification tasks.
- **Example**: Converting `"Spam"` and `"Not Spam"` into **0** and **1** for binary classification.

### **2. For Input Features with Low Cardinality (But Not Ordinal Data)**
- It can be used for input features when categories don’t have a meaningful order, **but only if the model doesn't interpret numeric values as ordered**.
- **Example**: Decision trees can handle label encoding well, but **linear models might struggle** if they assume an inherent order in the numbers.

---

# **2.Ordinal Encoding**

- Converts categorical values into **numerical values based on order**.  
- Used for **ordinal data** (e.g., education levels, satisfaction ratings).  
- Requires **manual ordering** based on domain knowledge.


## **When to Use Ordinal Encoding?**

### **1. For Categorical Features with a Meaningful Order**
- Some categories have a natural ranking where higher numbers indicate a higher level or intensity.  
- **Example**: Education levels


### **2. When the Difference Between Categories is Not Uniform**
- Even though the categories have an order, the difference between them may not be equal.  
- **Example**: Customer satisfaction levels  

Here, the gap between `Poor` and `Average` may not be the same as between `Good` and `Excellent`, but the ranking still matters.


