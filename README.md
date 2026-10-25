# Online Retail Transaction Analysis

The **Online Retail Transaction Analysis** project analyses retail transaction data to understand sales performance, product performance, customer behaviour and geographic trends.

The project follows an ETL, exploratory data analysis and machine learning process using Python. Statistical testing is used to investigate relationships within the data, while Linear Regression is used to predict future customer spending. A Tableau dashboard was also created to present the main business findings interactively.

![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

---
## Tableau Dashboard 
https://public.tableau.com/views/Unit3-OnlineRetailSalesDashboard/OnlineRetailSalesPerformanceDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Dataset Content

The project uses an Online Retail transaction dataset containing transactions between December 2010 and December 2011.

The original dataset contained **541,909 rows and 8 columns**, including:

- Invoice number
- Product stock code
- Product description
- Quantity
- Invoice date
- Unit price
- Customer ID
- Country

After cleaning and transformation, the final dataset contained **534,129 rows and 14 columns**.

Additional variables such as transaction type, transaction category, transaction value, year, month and year-month were created to support the analysis.

---

## Business Requirements

The project aims to answer four main business requirements:

1. Analyse overall sales and revenue performance over time.
2. Identify the strongest-performing products.
3. Understand customer behaviour and geographic market performance.
4. Predict future customer spending using historical purchasing behaviour.

The results can support decisions around sales planning, marketing, customer targeting and product strategy.

---

## Hypothesis and how to validate?

Three hypotheses were tested during the exploratory analysis.

### Hypothesis 1 - UK vs Non-UK Order Value

**H₀:** There is no significant difference in average order value between UK and non-UK sales.

A Welch's t-test produced a p-value below 0.05, so the null hypothesis was rejected. This indicates a statistically significant difference between UK and non-UK order values.

### Hypothesis 2 - Market and Cancellation Behaviour

**H₀:** Cancellation/return status is independent of whether an invoice is from the UK or outside the UK.

A Chi-Square test produced a p-value of **0.000009**, so the null hypothesis was rejected. This suggests that cancellation behaviour is associated with market location.

### Hypothesis 3 - Purchase Frequency and Customer Spending

**H₀:** There is no significant relationship between purchase frequency and total customer spending.

Spearman's correlation produced a coefficient of **0.8067**, showing a strong positive relationship between purchase frequency and total spending.

---

## Project Plan

The project was completed in the following stages:

- Load the original dataset.
- Investigate the original dataset.
- Perform ETL.
- Create useful transaction, date and revenue columns.
- Perform EDA.
- Calculate business KPIs and create visualisations.
- Apply probability and hypothesis testing.
- Build a Linear Regression model.
- Evaluate the Linear Regression model.
- Create a Tableau sales dashboard.

The raw dataset was kept unchanged while the cleaned dataset was exported separately for EDA, machine learning and Tableau.

The methods were selected because they provided a structured way to move from data cleaning to statistical analysis, visualisation and prediction.


---
## Project Lifecycle Plan

**Implementation:** I reused my Unit 2 project, reviewed the existing notebooks and updated the Tableau dashboard to communicate the findings more clearly. I also added data and ai ethics.

**Evaluation:** I reviewed the analysis results, machine learning performance and dashboard visualisations to check that they met the business requirements.

**Maintenance:** I would maintain this project by checking the quality of the data, update the analysis and refresh the dashboard if new data is available.

**Updates:** I would improve the dashboard and documentation based on user feedback or changes to business requirements.

**Review and Revision:** I reviewed the analysis and machine learning results and Tableau dashboard. I revised the dashboard by adding brief explanations to make the findings easier to understand. I also updated the README to include data and ai ethics and how the findings are communicated to different audiences.


## The rationale to map the business requirements to the Data Visualisations

The visualisations were selected based on the business questions being investigated.

- **Monthly Net Revenue Line Chart** - shows changes in revenue over time and highlights stronger and weaker trading periods.
- **Monthly Order Volume Bar Chart** - compares the number of completed orders across different months.
- **Top 10 Products by Net Revenue** - identifies the products contributing the most revenue.
- **Net Revenue by Country** - compares geographic market performance.
- **Customer Analysis** - investigates differences in customer spending and purchasing frequency.
- **Actual vs Predicted Spending Scatterplot** - evaluates the performance of the machine learning model.

The Tableau dashboard combines the main sales visualisations with interactive country and date filters.

---

## Analysis Techniques Used

The project used several analytical techniques:

- ETL
- Data Cleaning
- Descriptive statistics
- Probability
- Exploratory Data Analysis
- Data visualisation
- Welch's independent t-test
- Chi-Square test of independence
- Spearman correlation
- Linear Regression
- Train/test splitting
- Feature scaling with StandardScaler
- Regression evaluation using MAE, RMSE and R²

Extreme values were investigated rather than automatically removed because some represented genuine retail transactions.

One unusual Customer ID, **15287**, showed activity across several countries that was not representative of a typical individual customer. It was therefore excluded from the individual customer and machine learning analysis.

Generative AI tools were used to support brainstorming, explaining code, improving markdowns and help troubleshoot code. All code and results were tested and reviewed within the project environment.

---
## Data Ethics, Privacy and Governance

### Ethical Considerations

I considered data quality, privacy and potential bias throughout the project. During ETL, I investigated missing product descriptions, duplicate transactions, negative quantities and unusual prices. I implemented this because incorrect data could lead to misleading sales figures and poor business decisions.

I included returns in my analysis because they reduce net revenue. Excluding them would make the business appear to have earned more revenue than it actually did.

### Data Privacy

The dataset contains CustomerID, which I used to group customer purchases and analyse spending behaviour. Although the dataset does not include customer names, this does not mean the data is fully anonymous. Customers could potentially be identified if transaction details were combined with other information.

The dataset contains CustomerID, which is pseudonymous rather than fully anonymous. Although customer names are not included, the ID allows individual purchases to be linked together, which could create privacy risks.

To make the CustomerID anonymous, I would remove it and group transactions into summarised results, and check that individuals cannot reasonably be identified from the remaining data.

My Tableau dashboard presents the overall results, such as revenue by country and product, rather than displaying individual customer IDs.

### Bias and Fairness

Most of the sales in the dataset came from the UK. This could lead to misleading conclusions because customer behaviour in the UK is different from other countries. For example, products that are popular in the UK might not be as popular internationally.

### Data Governance

I kept the original dataset separate from the cleaned dataset and documented my cleaning decisions in the ETL notebook. This made it easier to understand how the data was processed.

I also organised the analysis into separate ETL, EDA and Machine Learning notebooks and saved the prediction results in a versioned output folder.

## Legal and Social Implications 

### Legal Implications

The UK GDPR and Data Protection Act 2018 apply when handling personal data. Although the dataset is publicly available, this does not mean it is fully anonymous or free to reuse without restrictions.

To reduce privacy risks, I would check the dataset's permissions, avoid sharing unnecessary customer information, use anonymised or summarised data where possible, and restrict access to customer records.


### Social Implications

Data analysis can affect how businesses treat their customers. For example, businesses might use spending predictions to decide which customers receive discounts or promotions.

If the data contains errors or bias, some customers could be unfairly excluded from these offers.

My machine learning model achieved an R² score of 0.450, meaning its predictions have limitations. Relying on these predictions alone could lead to unfair customer targeting.

To reduce this risk, I would consider customers purchase history and check whether the model's predictions could lead to unfair treatment of certain customer groups.

---

## Key Findings

The analysis identified several important findings:

- Total net revenue was approximately **£9.75 million**.
- The dataset contained **19,960 completed orders** and **4,338 customers** with completed sales.
- Average completed order value was approximately **£533.17**.
- The **United Kingdom** was the largest market, generating approximately **£8.19 million** in net revenue.
- **REGENCY CAKESTAND 3 TIER** was the highest-revenue product at approximately **£164,459**.
- Revenue increased strongly between September and November 2011.
- Purchase frequency had a **strong positive relationship** with total customer spending.
- Cancellation behaviour differed between UK and non-UK markets.
- December 2011 only contains transactions up to **9 December**, so it should not be directly compared with complete months.

---

## Machine Learning

A Linear Regression model was created to predict how much an existing customer would spend during the following 30 days.

The model used three historical customer features:

- **Recency** - days since the customer's most recent purchase.
- **Frequency** - number of previous orders.
- **Monetary** - total historical spending.

The model was trained using 80% of the customer data and evaluated using the remaining 20%.

### Model Results

- **MAE:** £239.01
- **RMSE:** £596.99
- **R²:** 0.450

The R² score shows that approximately 45% of the variation in future customer spending was explained by Recency, Frequency and Monetary behaviour.

The model demonstrated moderate predictive ability and showed that historical purchasing behaviour can provide useful information about future customer value.

### Machine Learning Limitations

Customer spending is highly variable and many customers made no purchases during the future 30-day period.

The model also only uses three customer features, meaning other factors affecting future spending are not considered.

Linear Regression was selected because it is simple and interpretable for a continuous target variable. Future development could compare its performance with models such as Random Forest Regression.

---
## Dashboard Design

I created the Tableau dashboard to give a simple overview of the main findings from the Online Retail Transaction Analysis project.

The dashboard includes five main sections:

1. Sales KPIs
2. Monthly Net Revenue
3. Monthly Order Volume
4. Top 10 Products by Net Revenue
5. Net Revenue by Country

The aim of the dashboard is to make the key results easy to understand at a glance. It allows users to quickly see overall sales performance, how revenue changes over time, which products perform best and which countries generate the most revenue.

## Communicating Insights to Different Audiences

I designed the Tableau dashboard to communicate the main findings clearly to both technical and non-technical audiences.

### Non-Technical Audience

For retail managers and other business users, I used easy to understand charts, KPI figures and short written explanations on tableau.

The dashboard includes:

- Net Revenue

- Total Orders

- Unique Customers

- Average Order Value

- Monthly Sales and Order Trends

- Top 10 Products

- Revenue by Country

For example, the country revenue chart shows that the United Kingdom generates most of the business's revenue. This allows managers to understand the importance of the UK market without needing technical knowledge.


### Technical Audience

For data analysts and technical users, the ETL, EDA and Machine Learning notebooks provide more detailed information about the methods and results.

These include:

- Data cleaning and transformation steps.

- Statistical hypothesis tests and p-values.

- Machine learning features and model training.

- Model evaluation using MAE, RMSE and R².

For example, the Linear Regression model achieved an R² score of 0.450, meaning it explained approximately 45% of the variation in future customer spending in the test data.

The model also achieved a Mean Absolute Error of £239.01, meaning its predictions differed from actual spending by approximately £239 per customer on average.

### Communication Approach

I used the Tableau dashboard to present the main business findings visually, while the notebooks and README provide the technical explanations.

This allows non-technical users to understand the key results quickly and technical users to examine the methods, calculations and limitations behind those results.

## Project Limitations

The dataset represents one retailer and covers approximately one year, so findings may not generalise to other businesses or longer periods.

December 2011 is incomplete because the dataset ends on 9 December.

Some extreme transactions and unusual customer behaviour also required investigation before analysis.

The Tableau dashboard focuses mainly on sales, product and geographic performance and could be expanded with additional customer and machine learning visualisations.

---

## Development Roadmap

Throughout this project, I improved my skills in data cleaning, exploratory data analysis, statistical testing, machine learning, data visualisation and documenting my work.

I did come across one issue at the start of the project. The VS Code terminal and Python environment were running x86_64, while my Mac was running ARM64. This caused problems with Python packages and dependencies.

I corrected the Python and terminal configuration to use ARM64, rebuilt the virtual environment and reinstalled the required packages.

If I continued developing the project, I would:

Compare Linear Regression with other regression models to see whether prediction performance could be improved.

Explore additional customer features that may help predict future spending more accurately.

Test the model on additional or more recent retail data to see how well it performs on new data.

Add further Tableau visualisations if they provide useful insights for the business.

Continue developing my skills in Python, statistics, machine learning and Tableau.

---

## Main Data Analysis Libraries

- **Pandas** 
- **NumPy** 
- **Matplotlib** 
- **Seaborn** 
- **Plotly**
- **SciPy** 
- **Scikit-learn** 
- **Jupyter Notebook**
- **Tableau** 

---

## Credits

- Dataset - https://www.kaggle.com/datasets/abhishekrp1517/online-retail-transactions-dataset
- Pandas - https://www.w3schools.com/python/pandas/default.asp
- NumPy - https://www.w3schools.com/python/numpy/default.asp
- Matplotlib - https://www.w3schools.com/python/matplotlib_intro.asp
- Seaborn - https://www.w3schools.com/python/numpy/numpy_random_seaborn.asp
- Plotly - https://www.geeksforgeeks.org/data-visualization/using-plotly-for-interactive-data-visualization-in-python/
- SciPy - https://www.w3schools.com/python/scipy/index.php
- Scikit-learn - https://www.geeksforgeeks.org/machine-learning/learning-model-building-scikit-learn-python-machine-learning-library/
- Tableau - https://help.tableau.com/current/guides/get-started-tutorial/en-us/get-started-tutorial-home.htm
- ChatGPT
- Code Institute lms and the Code Institute README template.
- Information Commissioner's Office (ICO) - https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-sharing/anonymisation/pseudonymisation/
- ICO - https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-sharing/anonymisation/how-do-we-ensure-anonymisation-is-effective/
- ICO - https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-protection-principles/a-guide-to-the-data-protection-principles/
- UK Government - https://www.legislation.gov.uk/ukpga/2018/12/contents
- ICO - https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/how-do-we-ensure-fairness-in-ai/
- UK Government - https://www.gov.uk/government/publications/data-ethics-framework/data-and-ai-ethics-framework
---

## Acknowledgements

I would like to thank the **Code Institute mentors and tutors** for their guidance and support throughout the project.
