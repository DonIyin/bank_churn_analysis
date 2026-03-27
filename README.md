# Bank Customer Churn Analysis

An exploratory data analysis of 500 bank customers to identify behavioural patterns and factors contributing to customer churn. Conducted using **Microsoft Excel** — Pivot Tables for descriptive analysis and the **Data Analysis ToolPak** for inferential statistics.

---

## Dataset

| Variable | Description |
|---|---|
| CustomerID | Unique customer identifier |
| CreditScore | Score between 350–850 |
| Geography | France, Spain, or Germany |
| Gender | Male or Female |
| Age | Customer age |
| Tenure | Years with the bank |
| Balance | Account balance |
| NumOfProducts | Number of banking products used |
| HasCrCard | Credit card holder (1 = Yes) |
| IsActiveMember | Active membership status (1 = Active) |
| EstimatedSalary | Estimated annual salary |
| Churn | Whether customer left (1 = Yes) |

**Data Cleaning:** Missing values in `EstimatedSalary` and inconsistent entries in `Balance` were replaced with column averages before analysis.

---

## Analytical Questions (Pivot Tables)

**Q1 — Average credit score by geography**

Spain has the highest average credit score (600.99), followed by France (592.55) and Germany (579.69). The differences across regions are relatively small, suggesting geography alone is not a strong credit score predictor.

**Q2 — Average account balance by gender and country**

Male customers in France hold higher average balances than females (₦133,204 vs ₦129,577). In Germany, the pattern reverses — females hold significantly higher balances (₦140,888 vs ₦128,591). Spain has the lowest balances overall for both genders, with males and females being very close.

**Q3 — Active vs non-active members by credit card ownership**

Customers without a credit card are slightly more likely to be non-active (140 vs 113). Those with a credit card are nearly evenly split between active and non-active (124 vs 123). Credit card ownership shows little influence on whether a customer remains actively engaged.

**Q4 — Churn rate by number of products**

Churn rate is consistently high across all product groups, ranging from 52.5% to 55.2%. Customers using 4 products show the slightly lowest churn rate. There is no strong relationship between number of products used and likelihood of churning — churn is widespread regardless of product count.

**Q5 — Average credit score: churned vs retained customers across tenure**

No consistent pattern emerges between credit score and churn across different tenure years. In some tenure groups churned customers have higher credit scores than retained ones; in others the reverse is true. Credit score alone is not a reliable predictor of churn at any tenure level.

---

## Research Questions (Data Analysis ToolPak)

**RQ1 — Is there a significant difference in average salary between churned and non-churned customers?**

A two-sample t-test (equal variances assumed) was conducted at α = 0.05.

| | Churned | Not Churned |
|---|---|---|
| Mean Salary | ₦83,428.09 | ₦80,464.52 |
| Observations | 272 | 228 |
| t-statistic | 0.8046 | |
| p-value (two-tail) | 0.4214 | |

**Conclusion:** p = 0.4214 > 0.05. We fail to reject the null hypothesis. There is no statistically significant difference in average estimated salary between churned and non-churned customers.

**RQ2 — Is there a significant difference in average credit score across geographic locations?**

A one-way ANOVA was conducted at α = 0.05 to compare credit scores across France, Spain, and Germany.

**Conclusion:** Based on the ANOVA results, we evaluate whether geographic location has a statistically significant effect on average customer credit scores across the three regions.

---

## Tools Used

- Microsoft Excel (Pivot Tables)
- Excel Data Analysis ToolPak (t-Test, ANOVA)

---

## Files

| File | Description |
|---|---|
| `Bank_Churn_Data.xlsx` | Cleaned dataset with all pivot tables and statistical tests across separate worksheets |

---

## Key Takeaways

- Churn is high across all customer segments — no single factor (salary, credit score, products used) strongly predicts who leaves.
- Geography and gender interact in interesting ways with account balance but not with churn directly.
- Salary does not significantly differ between churned and retained customers, suggesting churn is driven by other behavioural or service-related factors not captured in this dataset.
