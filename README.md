# Telecom-Company-

1. What variables are contributing to customer churn? 
Utilized (EDA) techniques to understand the relationship between different customer attributes and churn. Variables such as Contract Renewal, Data Plan usage, Customer Service Calls, Monthly Charges, and Overage Fees could potentially contribute to customer churn. Present findings using visualizations such as bar charts, and correlations to illustrate the impact of each variable on churn.
2. Who are the customers more likely to churn?
Segment customers based on various characteristics such as Contract Renewal status, Data Plan usage, and Customer Service interaction frequency. Calculate churn rates within each segment to identify groups of customers more likely to churn. Visualized churn rates across different segments to highlight which customer groups are at higher churn risk.
3. What actions can be taken to stop them from leaving?
Propose specific actions to reduce churn, such as offering personalized discounts, improving customer service quality, or introducing loyalty programs. Monitored the impact of retention strategies over time and iterate based on feedback and performance metrics. Presented recommendations and actionable insights clearly and concisely, supported by relevant visualizations and data-driven analysis.
In conclusion, the Power BI report will provide telecom industry stakeholders with actionable insights to better understand customer churn dynamics and implement effective retention strategies to minimize churn and improve customer retention rates.

DAX used:

Churn Rate = DIVIDE(COUNTROWS(FILTER('telecom_churn', 'telecom_churn'[Churn] = 1)), COUNTROWS('telecom_churn'))

Avg MonthlyCharge Churned = 
    AVERAGEX(
        FILTER('telecom_churn', 'telecom_churn'[Churn] = 1),
        'telecom_churn'[MonthlyCharge]
    )

Churn Rate by ContractRenewal = 
CALCULATE(
  DIVIDE(
    COUNTROWS(FILTER('telecom_churn', 'telecom_churn'[Churn] = 1)),
    COUNTROWS('telecom_churn')
  ),
  'telecom_churn'[ContractRenewal]
)
