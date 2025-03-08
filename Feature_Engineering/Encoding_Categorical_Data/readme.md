# **Nominal and Ordinal Data**
Categorical data can be classified into two types: **Nominal** and **Ordinal**.

## **1. Nominal Data**  
- Categories have no inherent order.  
- Examples: Colors (Red, Blue, Green), Gender (Male, Female, Other), Cities (New York, London, Tokyo).

## **2. Ordinal Data**  
- Categories have a meaningful order or ranking, but the differences between them are not necessarily uniform.  
- Examples: Education Level (High School < Bachelor's < Master's < PhD), Customer Satisfaction (Poor < Average < Good < Excellent).

---

# **Encoding Categorical Variables**
Since machine learning models work with numerical data, categorical variables must be converted into a numerical format. This process is called **encoding categorical variables**.

## **Types of Encoding**
### **1. One-Hot Encoding (OHE)**
- Converts categorical values into multiple binary (0/1) columns.
- Used for **nominal data**.
- Example:  

  | Color  | Red | Green | Blue |
  |--------|-----|-------|------|
  | Red    | 1   | 0     | 0    |
  | Green  | 0   | 1     | 0    |
  | Blue   | 0   | 0     | 1    |

---

### **2. Label Encoding**
- Assigns a unique integer to each category.
- Used for **ordinal data**.
- Example:

  | Education Level  | Label Encoding |
  |-----------------|---------------|
  | High School     | 0             |
  | Bachelor's      | 1             |
  | Master's        | 2             |
  | PhD            | 3             |

---

### **3. Ordinal Encoding**
- Similar to label encoding but ensures the numerical values reflect the inherent order in **ordinal** data.

---

### **4. Binary Encoding**
- Converts categories into binary representations and then encodes them as numerical features.

---

### **5. Target Encoding (Mean Encoding)**
- Replaces categories with the mean of the target variable for each category.
- Used in supervised learning.

---

# **Why Do We Encode Categorical Variables?**
✅ **Machine Learning Models Require Numerical Input**: Most ML models cannot process categorical variables directly.  
✅ **Improves Model Performance**: Proper encoding allows models to learn relationships effectively.  
✅ **Handles Feature Importance**: Encoding preserves relationships in ordinal data.  
✅ **Reduces Dimensionality**: Label or ordinal encoding prevents excessive feature expansion (unlike one-hot encoding for high-cardinality data).


