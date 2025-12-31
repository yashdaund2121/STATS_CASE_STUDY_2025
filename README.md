📊 Credit Risk Analysis & Default Behavior Study
🧠 Business Problem

This project analyzes credit risk and default behavior for a consumer lending company serving retail customers, many with limited or thin credit histories.

The company faces two major risks:

❌ Approving high-risk customers who later default

❌ Rejecting low-risk customers and losing business

The objective is to understand default drivers, evaluate previous loan behavior, and provide data-driven recommendations to reduce credit risk while staying aligned with an industry default benchmark of 10%.

🎯 Project Objectives

Understand customer demographics and loan characteristics

Identify key drivers of loan default

Analyze how previous loan refusals impact current default risk

Compare company default rate with industry benchmark

Provide actionable business recommendations

🗂️ Datasets Used
1️⃣ Previous Loans Dataset (credit_risk_previous_loans)

Records: ~1.67 million

Columns: 37 → 26 after cleaning

Key Features:

SK_ID_CURR – Customer ID

NAME_CONTRACT_STATUS – Approved / Refused / Canceled

AMT_APPLICATION, AMT_CREDIT, AMT_ANNUITY

DAYS_DECISION – Days before current application

2️⃣ Current Applicants Dataset (credit_risk_applicants)

Records: ~307,000

Columns: 122 → 73 after cleaning

Key Features:

TARGET – 1: Default, 0: Repaid

Demographics: Gender, Age, Education

Financials: Income, Credit, Annuity

Employment: DAYS_EMPLOYED

External Risk Scores: EXT_SOURCE_2, EXT_SOURCE_3

🧹 Data Cleaning & Preparation
✔ Missing Value Treatment

Dropped columns with >40% missing values

Numerical columns → Median imputation

Categorical columns → Mode imputation

Final datasets have 0% missing values

✔ Outlier Handling

Used IQR method (1.5×IQR)

Applied on income, credit, annuity, and application amount

✔ Feature Engineering

AGE_YEARS

YEARS_EMPLOYED

CREDIT_INCOME_RATIO

CREDIT_ANNUITY_RATIO

Flags:

has_prev_refusal

has_prev_approval

📊 Exploratory Data Analysis (EDA)
Key Observations

Defaulters tend to have:

Lower income

Higher loan amounts

Higher credit burden

Customers with:

Lower education

Shorter employment history
show higher default risk

External risk scores (EXT_SOURCE_2, EXT_SOURCE_3) are strongly predictive

🧪 Hypothesis Testing
Hypothesis	Test Used	Result
Income differs for defaulters	T-test	✅ Significant
Default varies by gender	Chi-square	✅ Significant
Education affects default	ANOVA	✅ Significant
Previous refusals predict default	Chi-square	✅ Strong association
Company default vs 10% benchmark	Z-test	❌ Not significantly different
🔑 Key Drivers of Default

Low income

High credit & annuity burden

Previous loan refusals

Low external risk scores

Lower education level

Short employment history

Certain loan products & goods categories

💡 Business Recommendations

Use previous refusal history as a strong risk flag

Cap credit-to-income ratio for low-income customers

Apply stricter rules for:

Low education

Unstable employment

Leverage external risk scores more aggressively

Refine policies by loan product & goods category

Continuously monitor default rate against industry benchmark

⚠️ Limitations

No predictive ML model built (analysis-focused)

Some real-estate features dropped due to high missingness

Results based on historical data only

🚀 Future Scope

Build a credit scoring model (Logistic / XGBoost)

Perform time-based stability analysis

Add profitability & ROI analysis

Deploy as a risk analytics dashboard

🛠️ Tech Stack

Python

Pandas, NumPy

Matplotlib, Seaborn

SciPy, Statsmodels

Jupyter Notebook
