# Systemic Crisis Prediction in Africa

## Project Overview
This project focuses on predicting the likelihood of **Systemic Crisis emergence** in 13 African countries using historical financial and economic indicators. The dataset, provided by Kaggle, contains information about **Banking, Debt, Financial, Inflation, and Systemic Crises** from 1860 to 2014.

The countries included in the dataset are:  
Algeria, Angola, Central African Republic, Ivory Coast, Egypt, Kenya, Mauritius, Morocco, Nigeria, South Africa, Tunisia, Zambia, and Zimbabwe.

The goal of this project is to apply **supervised classification methods** to predict systemic crises using features such as annual inflation rates, debt defaults, currency crises, and banking crises.

---

## Dataset Description
The dataset contains the following columns:

| Column | Description |
|--------|-------------|
| country_number | Numeric identifier for each country |
| country_code | ISO code of the country |
| country | Name of the country |
| year | Year of the observation |
| systemic_crisis | Target variable: 1 if a systemic crisis occurred, 0 otherwise |
| exch_usd | Exchange rate (USD) |
| domestic_debt_in_default | Indicator for domestic debt default |
| sovereign_external_debt_default | Indicator for sovereign external debt default |
| gdp_weighted_default | GDP-weighted debt default |
| inflation_annual_cpi | Annual inflation (CPI) |
| independence | Indicator for year of independence |
| currency_crises | Binary indicator for currency crises |
| inflation_crises | Binary indicator for inflation crises |
| banking_crisis | Binary indicator for banking crises |

---

## Project Instructions

### 1. Data Import & Exploration
- Import the dataset using `pandas`.
- Display general information about the dataset:
  - `.info()`, `.describe()`, `.head()`
- Check for missing values and duplicates.
- Use `pandas_profiling` (or `ydata-profiling`) to generate an exploratory data analysis report.

### 2. Data Preprocessing
- Handle missing or corrupted values:
  - Fill numerical NaNs with median or mean.
  - Fill categorical NaNs with mode or a separate category.
- Remove duplicates if present.
- Encode categorical variables (e.g., `country`) using **one-hot encoding**.
- Encode binary crisis columns (`banking_crisis`, `inflation_crises`, etc.) to 0/1 if not already numeric.

### 3. Feature Selection
- Select the target variable: `systemic_crisis`.
- Select relevant features based on domain knowledge and correlation analysis:
  - Economic indicators: `inflation_annual_cpi`, `exch_usd`, `gdp_weighted_default`
  - Crisis indicators: `banking_crisis`, `currency_crises`, `inflation_crises`
  - Country identifier (after encoding)

### 4. Train-Test Split
- Split the dataset into training and testing sets (e.g., 80%-20%) using `train_test_split`.
- Use **stratification** to ensure the class distribution is preserved.

### 5. Model Selection & Training
- Choose a **classification algorithm** based on data exploration:
  - Random Forest, Decision Tree, Logistic Regression, or XGBoost.
- Train the model on the training set.

### 6. Model Evaluation
- Assess model performance using:
  - **Accuracy**
  - **Precision, Recall, F1-score**
  - **Confusion Matrix**
  - ROC-AUC if needed


### 7. Discussion & Improvements
- Discuss alternative ways to improve model performance:
  - Feature engineering (e.g., lagged indicators)
  - Hyperparameter tuning
  - Ensemble methods
  - Incorporating additional external economic indicators

---

## Tools & Libraries
- Python 3.x
- Pandas
- NumPy
- Scikit-learn
- Matplotlib & Seaborn (for visualization)
- Pandas Profiling / ydata-profiling

---

