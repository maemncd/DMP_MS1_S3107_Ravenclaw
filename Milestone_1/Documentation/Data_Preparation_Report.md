# Milestone 1 - Data Preparation & Feature Engineering Report

## Executive Summary
Complete data preparation for FinMark customer segmentation with **all mentor feedback incorporated**.

## Mentor Feedback - All Addressed ✅
- ✅ Merged transaction and customer data **FIRST** (before cleaning)
- ✅ Used **transaction amount** as reference for income groups
- ✅ Derived income groups using **quartiles** (Q1, Q3)
- ✅ Created **consolidated CSV** of cleaned data

## Data Cleaning Results
| Metric | Value |
|--------|-------|
| Original merged records | 25,623 |
| Cleaned records | 5,000 |
| Duplicates removed | 20,623 |
| Missing values | 0 (imputed with median) |
| Outliers handled | Yes (IQR method) |

## Income Group Derivation
**Method**: Quartile-based on Transaction_Amount

| Group | Boundary | Count | Percentage |
|-------|----------|-------|-----------|
| Low | ≤ $1,260 (Q1) | 1,251 | 25% |
| Medium | $1,260 - $3,682 (Q1-Q3) | 2,501 | 50% |
| High | > $3,682 (Q3) | 1,248 | 25% |

## Features Engineered (27 total)

### Spending Features (6)
- Total_Spending: Sum of all transactions
- Avg_Transaction_Amount: Mean transaction value
- Max_Transaction: Highest single transaction
- Min_Transaction: Lowest single transaction
- Std_Transaction_Amount: Variability in spending
- Median_Transaction: Median transaction value

### Engagement Features (1)
- Transaction_Count: Number of transactions per customer

### Satisfaction Features (4)
- Avg_Satisfaction: Mean satisfaction score
- Std_Satisfaction: Consistency of satisfaction
- Min_Satisfaction: Lowest satisfaction
- Max_Satisfaction: Highest satisfaction

### Recommendation Features (3)
- Avg_Likelihood_to_Recommend: Mean recommendation score
- Min_Likelihood: Lowest likelihood
- Max_Likelihood: Highest likelihood

### Sentiment Features (2)
- Avg_Feedback_Sentiment: Mean feedback sentiment (1-5 scale)
- Std_Feedback_Sentiment: Sentiment consistency

### Temporal Behavior Features (6)
- Pct_Business_Hours: % transactions during 9AM-5PM
- Pct_Weekend_Transactions: % transactions on weekends
- Pct_Morning_Transactions: % transactions 6AM-12PM
- Pct_Evening_Transactions: % transactions 6PM-12AM
- Avg_Hour_of_Day: Average transaction hour
- Std_Hour_of_Day: Variability in transaction timing

### Transaction Type Distribution (4)
- Count_Purchase: Number of purchase transactions
- Count_Bill Payment: Number of bill payment transactions
- Count_Investment: Number of investment transactions
- Count_Loan Payment: Number of loan payment transactions

### Income Group (1)
- Primary_Income_Group: Low/Medium/High classification

## Key Insights

1. **Spending Diversity**: High variation in customer spending indicates good potential for segmentation
2. **Income-Spending Correlation**: Clear differentiation between income groups validates quartile approach
3. **Satisfaction Variation**: Low correlation with spending suggests distinct experience segments
4. **Temporal Patterns**: Customers show different activity schedules (business hours vs. evenings)
5. **Engagement Range**: Transaction count varies from 1-13, indicating diverse engagement levels

## Files Generated
- FinMark_Transaction_Data_Cleaned.csv (5,000 records)
- FinMark_Customer_Features_Engineered.csv (993 customers)
- FinMark_Milestone1_Fresh.ipynb (Complete analysis notebook)

## Next Steps
→ **Milestone 2**: Clustering analysis
  - K-means with elbow method
  - Hierarchical clustering
  - Cluster characterization and profiling
