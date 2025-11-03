# MSCS-634 Project Deliverable 1 – Data Collection, Cleaning, and Exploratory Data Analysis (EDA)
**Author:** *Nitish Dhinaharan* 

## Dataset Summary
**Dataset:** [Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn)  
**Records:** 7,043 customer entries  
**Features:** 21 attributes covering demographics, account details, and telecom service usage.  
**Objective:** Analyze customer behavior to identify factors influencing churn (customer loss) and prepare a clean dataset for predictive modeling.

The dataset contains both **categorical** and **numeric** variables, enabling exploration of both **regression** and **classification** tasks in later deliverables. The target variable for classification is `Churn` (Yes/No), and potential regression targets include `MonthlyCharges` and `TotalCharges`.

---

## Data Cleaning Summary
The raw data required several preprocessing steps to ensure accuracy and consistency:

1. **Converted Data Types:**  
   The `TotalCharges` column was incorrectly stored as text. It was converted to numeric using `pd.to_numeric(errors='coerce')`.

2. **Handled Missing Values:**  
   Missing values in `TotalCharges` were identified (≈11 rows) and imputed using the **median** to preserve data distribution.

3. **Normalized Binary Values:**  
   The `SeniorCitizen` column was converted from numeric (0/1) to categorical (“No”/“Yes”) for clarity.

4. **Removed Duplicates:**  
   Verified and dropped any duplicate records to maintain data integrity.

5. **Validated Structure:**  
   Confirmed correct data types, consistent value ranges, and absence of nulls post-cleaning.

---

## Exploratory Data Analysis (EDA)
Key steps in the EDA process included:

- **Univariate Analysis:** Examined distributions of numeric variables (`MonthlyCharges`, `TotalCharges`, `tenure`) to identify outliers and skewness.  
- **Bivariate Analysis:** Explored churn relationships with major features such as `Contract`, `InternetService`, and `PaymentMethod`.  
- **Correlation Heatmap:** Identified moderate correlation among numeric variables—`tenure`, `MonthlyCharges`, and `TotalCharges`—which are potential predictors.  
- **Visualization Highlights:**
  - Churn rate ≈ 26%.  
  - Customers with **month-to-month contracts** and **higher monthly charges** churn more frequently.  
  - **Longer-tenure customers** tend to stay subscribed.  

---

## Insights and Implications
The EDA suggests that **contract type**, **tenure**, and **monthly spending** are strong indicators of churn behavior. These findings will guide model development:
- Regression models will use `MonthlyCharges` or `TotalCharges` as dependent variables to understand spending patterns.  
- Classification models will predict `Churn`, focusing on categorical features such as `Contract` and `PaymentMethod`.  

---

## Challenges and Resolutions
| Challenge | Resolution |
|------------|-------------|
| `TotalCharges` stored as string | Converted to numeric and imputed missing values with median. |
| Inconsistent binary encoding (`SeniorCitizen`) | Replaced 0/1 with “No”/“Yes” for better readability. |
| Slight class imbalance in `Churn` variable | Noted for future modeling—will address using sampling or weighting. |
| Mixed data types and varied feature scales | Documented; will normalize and encode in Deliverable 2. |

---

## Next Steps
- Feature engineering (encoding categorical variables, scaling).  
- Regression modeling (`MonthlyCharges`, `TotalCharges`).  
- Classification modeling (`Churn`).  
- Further validation and performance optimization.

---
