<h1>🏦 Loan Default Rate Prediction and Segmentation Analysis</h1>



<h2>Executive Summary</h2>
This project investigates loan default risk by analyzing over 307,000 loan applications from India. Using SQL-based dimensional modeling and Python-driven exploratory analysis, I identified patterns across income levels, loan types, age groups, and occupations. The goal was to uncover high-risk borrower segments and support data-driven credit strategies.

This work emphasizes how thoughtful data organization and demographic segmentation can help reduce default risks and guide smarter lending decisions.


<h2>Project Objectives</h2>
- Predict the likelihood of default using demographic and financial variables
- Segment customers by income, age, and occupation to identify high-risk groups
- Build a dimensional data model (star schema) to support scalable analysis
- Address class imbalance and reduce dimensionality for interpretable insights


<h2> Dataset Overview</h2>

- Source: IIIT Bangalore Loan Applications Dataset
- Size: 307,511 rows × 122 columns (148.7MB)
- Target: loan_default (1 = Default, 0 = No Default)

- Key Features:
  - amt_income_total (Client income)
  - amt_credit (Loan amount)
  - days_birth (Age in days)
  - name_contract_type (Cash vs Revolving loan)
  - cnt_children, amt_annuity, occupation_type
 

<h2>Tools & Technologies</h2>

| Tool | Purpose |
|------|---------|
| **SQL (PostgreSQL)** | Dimensional modeling, data wrangling |
| **Python (Pandas, Matplotlib)** | EDA and risk segmentation |
| **Excel** | Preliminary data cleaning |
| **Tableau/Power BI (Optional)** | Dashboard for business users |



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

- <b>Key Observations</b>:
  
| Variable | Finding |
|----------|---------|
| **Loan Type** | Cash loans → 8.9% default vs Revolving → 6.8% |
| **Gender** | Men earn more but default more than women |
| **Age + Occupation** | Highest risk: 21–30y, especially cleaners and low-skill workers |
| **Income** | Default risk decreases significantly after ₹200k annual income |


- <b> Challenges & Solutions</b>:

| Challenge | Approach |
|----------|----------|
| Class Imbalance (Only 8% defaults) | Stratified segmentation + categorical binning |
| High Dimensionality (122 features) | Reduced to 19 core features using business relevance & correlation checks |


<h2>Visualizations:</h2>

- 🔹 Bar chart: Default Rate by Income Group & Loan Type  
- 🔹 Heatmap: Default % by Age & Occupation  
- 🔹 Gender vs Income vs Default Rate comparison  

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


<h2>Future Recommendation</h2>

1. <b>Enhanced Features</b>:
    - Include behavioral data, such as transaction history or spending patterns.
2. <b>Improved Models</b>:
     - Implement machine learning for more robust predictions.
3. <b>Expanded Analysis</b>:
     - Explore regional differences or time trends in defaults.

<h2>Conclusion</h2>

This project demonstrates the power of dimensional modeling and data analysis in understanding loan default risks. The findings provide actionable insights for lenders to minimize risks and offer tailored loan products to customers. 

## Why This Project Matters to Employers

- 💡 Demonstrates ability to organize and model complex, high-dimensional data  
- 📊 Shows business-oriented thinking by translating insights into segmentation strategies  
- ⚙️ Applies data storytelling to real-world financial risk problems  
- 🔍 Highlights cross-functional value (useful to credit, risk, and product teams)
- 
<!-- 
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>


