# IQR Method for Outlier Detection

## Assumption  
- Works for **both skewed and non-skewed data**.  
- Does **not** assume a normal distribution.  

---

## How to Apply IQR for Outlier Detection  
1. **Compute Quartiles (Q1 & Q3)**  
   - **Q1 (25th percentile)**
   - **Q3 (75th percentile)**  

2. **Calculate Interquartile Range (IQR)**  

3. **Set Outlier Boundaries**  
- Data points **outside these bounds** are considered **outliers**.  

---

## How to Treat Outliers  

### **1. Trimming (Removing Outliers)**  
- **Remove** values **outside** the IQR range.  
- **Use when:** Data errors or irrelevant anomalies.  

### **2. Capping (Winsorization)**  
- **Replace extreme values**:  
- **Above Upper Bound → Q3 + 1.5 × IQR**  
- **Below Lower Bound → Q1 - 1.5 × IQR**  
- **Use when:** Outliers contain useful information but need limiting.  
