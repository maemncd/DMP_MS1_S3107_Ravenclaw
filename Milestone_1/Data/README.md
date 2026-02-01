# Milestone 1 - Data Files

## FinMark_Transaction_Data_Cleaned.csv
- **Records**: 5,000 cleaned transactions
- **Columns**: 10
- **Purpose**: Transaction-level analysis
- **Key Feature**: Income_Group (derived from transaction amount quartiles)
- **Contents**: 
  - Customer_ID
  - Transaction_Date
  - Transaction_Amount
  - Transaction_Type
  - Satisfaction_Score
  - Likelihood_to_Recommend
  - Feedback_Comments
  - Income_Group (Low/Medium/High)
  - Temporal flags (Is_Business_Hours, Is_Weekend)

## FinMark_Customer_Features_Engineered.csv
- **Records**: 993 unique customers
- **Columns**: 28 (Customer_ID + 27 engineered features)
- **Purpose**: PRIMARY FILE FOR CLUSTERING ANALYSIS (Milestone 2)
- **Features Created**: 
  - Spending metrics (6): Total, Avg, Max, Min, Std, Median
  - Engagement (1): Transaction Count
  - Satisfaction (4): Avg, Std, Min, Max
  - Recommendation (3): Avg, Min, Max
  - Sentiment (2): Avg, Std
  - Temporal behavior (6): Business hours %, Weekend %, Morning %, Evening %, Avg hour, Std hour
  - Transaction type distribution (4): Purchase, Bill Payment, Investment, Loan Payment
  - Income group (1): Primary income classification

## Data Preparation Summary
✅ Merged Transaction + Customer Feedback (BEFORE cleaning - mentor feedback)
✅ Removed 20,623 duplicates from 25,623 records
✅ Income groups derived from transaction amount quartiles:
   - Low (≤$1,260): 25%
   - Medium ($1,260-$3,682): 50%
   - High (>$3,682): 25%
✅ All missing values imputed (median strategy)
✅ Outliers handled via IQR method
✅ 27 customer-level features engineered for clustering
