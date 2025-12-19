<h1>🏦 Loan Default Rate Prediction & Segmentation</h1>
<h3>Turning messy credit data into decisions you can actually trust<h3>

<h2>Why I built this</h2>

When people talk about loan default models, they often jump straight to accuracy or algorithms.
What I kept running into instead was a quieter problem: **the data itself was messy, inconsistent, and easy to misread.**

I wanted to answer a more practical question first.

> If a credit team had to make decisions tomorrow, which parts of this data could they actually rely on?

This project started there.



<h2>The problem I was trying to solve</h2>

I worked with 307,000+ loan applications where only about 8 percent actually defaulted.
That imbalance alone makes it tempting to overfit, oversimplify, or chase surface level patterns.


- Source: IIIT Bangalore Loan Applications Dataset
- Size: 307,511 rows × 122 columns (148.7MB)
- Target: loan_default (1 = Default, 0 = No Default)

- Key Features:
  - amt_income_total (Client income)
  - amt_credit (Loan amount)
  - days_birth (Age in days)
  - name_contract_type (Cash vs Revolving loan)
  - cnt_children, amt_annuity, occupation_type
 


But the bigger challenge showed up earlier:

  - Income, age, occupation, and loan types existed, but not in a form that was easy to reason about
  - 120+ features looked impressive, but many told the same story in slightly different ways
  - Aggregates hid risk pockets that only appeared when variables interacted

Before predicting anything, I needed to make the system readable.


<h2> How I approached it (and why) </h2>

I treated this less like a modeling task and more like an application support problem for data.

**First, structure came before insight.**
I built a SQL-based star schema so that demographics, loan details, and credit inquiries each had a clear role. This made it easier to ask focused questions without re-cleaning the data every time.

**Second, I questioned defaults instead of accepting them.**
When default rates differed by gender or loan type, I stopped and asked:

- Is this a real signal?
- Or is it an artifact of income distribution, age mix, or occupation clustering?

That led me to segment deliberately instead of globally.

**Third, I reduced complexity on purpose.**
Out of 122 features, I narrowed the analysis to 19 that consistently mattered across segments.
Not because the others were useless, but because they didn’t help explain risk in a stable, repeatable way.


<h2> What surfaced once the noise was gone</h2>

A few findings stood out once the data was structured and validated:
  - Cash loans showed materially higher default rates than revolving loans
  - Higher income reduced default risk sharply after a clear threshold
  - Younger borrowers (21–30), especially in lower skill occupations, concentrated risk more than age alone suggested
  - Men earned more on average but defaulted at higher rates, which only made sense after controlling for loan type and income bands

None of these were surprising on their own.
What mattered was **how consistently they held once the data stopped fighting back.**


<h2>Where I struggled (and what I learned</h2>

Class imbalance forced tradeoffs.
High dimensionality tempted shortcuts.

I caught myself more than once chasing patterns that disappeared after one more validation step. That was the reminder that **clarity beats cleverness** in risk work.

What helped was slowing down and asking:

 > “If someone had to maintain this tomorrow, would this still make sense?”

That question guided most of my decisions.



<h2>Why this matters beyond this project</h2>

This wasn’t about building the flashiest model.
It was about showing how clean structure, careful segmentation, and disciplined skepticism turn raw data into something operational teams can actually use.

The same mindset applies whether the system is a credit platform, a risk pipeline, or an internal business application.


<h2>Key takeaways</h2>

- Structured data makes better decisions than clever models on unstable inputs
- Segmentation reveals risk that averages hide
- Reducing features can increase trust, not reduce insight
- Clear reasoning travels better than perfect accuracy


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
  
       
## Why This Project Matters to Employers

  
<h2>Final thoughtFh2>

I don’t see data as something to impress with.
I see it as something teams have to live with, maintain, and rely on when things go wrong.

This project reflects how I think when I’m responsible for that trust.



<!-- 
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>


