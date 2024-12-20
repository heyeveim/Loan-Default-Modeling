<h1>Loan Default Rate Prediction and Analysis 📊</h1>



<h2>Description</h2>
This project explores the likelihood of loan defaults using a dataset of 307,511 loan applications from India. By employing <b>dimensional modeling</b>, we analyzed key factors such as <b>income levels, loan types, gender differences</b>, and <b>age brackets</b> to identify patterns and build predictive insights for loan repayment behavior. This work highlights the importance of customer segmentation in reducing default risks and improving lending strategies.  <br><br>
Key features of the project include:


- Dimensional modeling using SQL for clean and efficient data organization
- Business questions addressing loan default rates by demographic and income group
- Identification of high-risk profiles through data wrangling and exploratory analysis


<h2>Languages and Tools Used</h2>

- <b>SQL</b>: For data wrangling and dimensional modeling.
- <b>Python</b>: Data visualization and final analysis.
- <b>PostgreSQL</b>: Database for dimensional modeling.
- <b>Excel</b>: Preliminary data exploration.
- <b>Tableau/Power BI</b>: (Optional for dashboards).


<h2>Dataset </h2>

- <b>Source: International Institute of Information Technology Bangalore (Loan Applications Dataset)</b>

  [Visit NBA Data Source](https://www.kaggle.com/datasets/nathanlauga/nba-games)

- <b>Size</b>: 148.7 MB (122 variables and 307,511 observations)
- <b>Target Variable</b>: Loan repayment behavior (1 = Default, 0 = No Default)
  
- <b>Main Features</b>:
  - amt_income_total: Client income
  - amt_credit: Loan amount.
  - amt_annuity: Annual loan payment.
  - cnt_children: Number of children.
  - days_birth: Age of the client.
  - name_contract_type: Loan type (Cash or Revolving).


<h2>Key Steps</h2>

<h3>1. Data Wrangling:</h3>

- Cleaned missing values and replaced them with NULL or DATA NOT AVAILABLE
- Grouped numerical data into categories:
  - Income Levels:
    - ≤ ₹100k: Lower
    - ₹100k–₹150k: Lower-Middle
    - ₹150k–₹200k: Upper-Middle
    - ₹200k: Upper
  - Age Groups:
    - 21–30, 31–40, 41–50, 51–60, ≥61
- Other categories: Loan amounts, annuities, and inquiries to credit bureaus
  
<h3>2. Dimensional Modeling:</h3>

Organized data into a star schema with:

- <b>Fact Table</b>: Loan repayment outcomes
- <b>Dimension Tables</b>: Customer demographics, loan details, and credit inquiries
  
<h3>3. Analysis:</h3>

- <b>Business Questions</b>:
  1. What is the average default rate across different income groups and loan types?
  2. How do income and gender affect default rates?
  3. Which combinations of income, age, and occupation are the highest risk?

- <b>Observations</b>:
  - <b>Income and Loan Type</b>: Cash loans have higher default rates (8.9%) than revolving loans (6.8%)
  - <b>Gender Differences</b>: Males have higher incomes but also higher default rates
  - <b>Age and Occupation</b>: Defaults are highest in the 21–30 age group, especially for low-skill laborers and cleaning staff



<h2>Visualizations:</h2>

<p align="center">
  <b>Default Rates by Income and Loan Type:</b><br/>
  <img src="https://i.imgur.com/QHGXA35.png" alt="Default Rates" width="50%"/>
  <br />
</p>
<p align="center">
  <b>Gender-Based Differences:</b><br/>
  <img src="https://i.imgur.com/Yaat4MN.png" alt="Gender-Based Differences" width="50%"/>
  <br />
</p>
<p align="center">
  <b>Risk Profiles by Age and Occupation:</b><br/>
  <img src="https://i.imgur.com/ntWKjao.png" alt="Risk Profile 1" width="45%" style="margin-right: 5px;"/>
  <img src="https://i.imgur.com/4TubQv1.png" alt="Risk Profile 2" width="45%"/>
</p>


<h2>Challenges and Insights</h2>

-  <b>Challenges</b>:
    - Class imbalance: Only 8% default rate
    - High dimensionality: Reduced variables from 122 to 19 for clarity
      
- <b>Key Insights</b>:
  - Income, age, and loan type significantly impact defaults.
  - Technical occupations have the lowest default rates.


<h2>Future Recommendation</h2>

1. <b>Enhanced Features</b>:
    - Include behavioral data, such as transaction history or spending patterns.
2. <b>Improved Models</b>:
     - Implement machine learning for more robust predictions.
3. <b>Expanded Analysis</b>:
     - Explore regional differences or time trends in defaults.

<h2>Conclusion</h2>

This project demonstrates the power of dimensional modeling and data analysis in understanding loan default risks. The findings provide actionable insights for lenders to minimize risks and offer tailored loan products to customers. 

<!-- 
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>


