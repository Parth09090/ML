# Z-Score Method for Outlier Detection  

## Assumption  
- This method is applicable **only when the data follows a normal distribution** or is **approximately normal**.  
- If the data is heavily skewed or follows a different distribution, Z-score may not be reliable for detecting outliers.  

---

## How to Apply Z-Score for Outlier Detection  
1. **Compute Mean & Standard Deviation** – Calculate the **mean (µ)** and **standard deviation (σ)** of the dataset.  
2. **Calculate Z-Scores** – Use the formula:  
  **Z = (X - µ) / σ**  
   where **X** is the individual data point, **µ** is the mean, and **σ** is the standard deviation.  
4. **Set a Threshold** –  
   - A common threshold is **|Z| > 3** (data points beyond 3 standard deviations are considered outliers).  
   - Some domains may use **|Z| > 2.5** or **|Z| > 3.5** based on the dataset characteristics.  
5. **Identify Outliers** – Mark data points with Z-scores **beyond the chosen threshold** as outliers.  

---

## How to Treat Outliers?  
Once outliers are detected, they can be handled using:  

### **1. Trimming (Removing Outliers)**  
- **When to use:** If the dataset is large, and outliers are due to data entry errors, noise, or anomalies that do not contribute useful information.  
- **How to apply:** Simply remove data points **beyond the threshold** and proceed with the analysis.  
- **Risk:** If outliers contain meaningful information (e.g., rare but important cases), removing them may lead to loss of valuable insights.  

### **2. Capping (Winsorization)**  
- **When to use:** If outliers are extreme but still relevant, instead of removing them, they can be **capped** at a predefined limit.  
- **How to apply:** Replace values above the upper threshold (e.g., **Z > 3**) with the value at the **95th percentile** and values below the lower threshold (e.g., **Z < -3**) with the **5th percentile**.  
- **Risk:** Reduces the impact of extreme values but may distort the natural distribution of the data.  
