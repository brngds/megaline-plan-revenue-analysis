# 📱 Megaline Plan Revenue Analysis

Statistical analysis of prepaid telecom plans using **Python**, **Pandas**, **NumPy**, **Matplotlib**, and **SciPy**, with a focus on customer behavior, monthly revenue, and hypothesis testing.

## 📌 Context

Megaline is a telecommunications company that offers two prepaid plans: **Surf** and **Ultimate**.

The commercial department wants to better understand how customers use these plans and whether their revenue performance differs. This information can support decisions related to marketing strategy and advertising budget allocation.

In this project, data from approximately 500 Megaline customers was analyzed to understand monthly usage patterns for calls, text messages, and mobile internet, calculate customer-level monthly revenue, and statistically compare revenue across plans and geographic regions.

The project was developed as part of my Data Science studies and reorganized for portfolio presentation, preserving the analytical process and statistical methodology.

## 🎯 Problem

The main objective was to analyze customer behavior and determine whether the two prepaid plans generate different levels of revenue.

The analysis addresses questions such as:

- How many call minutes do customers use each month?
- How many text messages do customers send?
- How much mobile data do customers consume?
- How do usage patterns differ between Surf and Ultimate subscribers?
- How much monthly revenue does each customer generate?
- Is average revenue statistically different between the Surf and Ultimate plans?
- Is average revenue for customers in the NY-NJ area statistically different from customers in other regions?

## 💳 Plans

### Surf

- Monthly fee: **$20**
- 500 included minutes
- 50 included text messages
- 15 GB of included data
- Additional minute: **$0.03**
- Additional message: **$0.03**
- Additional GB: **$10**

### Ultimate

- Monthly fee: **$70**
- 3,000 included minutes
- 1,000 included text messages
- 30 GB of included data
- Additional minute: **$0.01**
- Additional message: **$0.01**
- Additional GB: **$7**

Calls are rounded up individually to the next full minute. Monthly internet consumption is aggregated and then rounded up to the next gigabyte.

## 📊 Dataset

The project uses five related datasets.

### `megaline_users.csv`

Customer information including:

- user ID
- name
- age
- registration date
- churn date
- city
- subscribed plan

### `megaline_calls.csv`

Individual call records containing:

- call ID
- call date
- duration
- user ID

### `megaline_messages.csv`

Text message activity containing:

- message ID
- message date
- user ID

### `megaline_internet.csv`

Internet usage sessions containing:

- session ID
- megabytes used
- session date
- user ID

### `megaline_plans.csv`

Plan characteristics including:

- monthly fee
- included minutes
- included messages
- included data
- overage prices for minutes, messages, and data

## 🔎 Approach

The project followed a structured statistical analysis workflow:

1. Data loading and initial inspection
2. Data type validation and conversion
3. Data quality assessment
4. Call duration rounding according to billing rules
5. Monthly aggregation of call minutes
6. Monthly aggregation of text messages
7. Monthly aggregation of internet usage
8. Conversion of monthly internet consumption from MB to billed GB
9. Integration of customer activity and plan information
10. Calculation of monthly revenue per customer
11. Comparison of customer behavior between plans
12. Descriptive statistical analysis
13. Distribution analysis using histograms
14. Statistical hypothesis testing
15. Interpretation of results and business implications

## 🧹 Data Preparation

The datasets were inspected and prepared before the statistical analysis.

The preprocessing stage included:

- conversion of date columns to appropriate datetime formats;
- validation of numerical and categorical variables;
- investigation of missing values;
- aggregation of customer activity by month;
- rounding individual call durations according to Megaline billing rules;
- aggregation and monthly rounding of internet consumption;
- combination of calls, messages, internet usage, customer, and plan data.

These transformations made it possible to reconstruct the monthly activity and billing profile of each customer.

## 💰 Revenue Calculation

Monthly revenue was calculated at the customer level.

For each customer-month combination, the analysis:

1. identified the customer's plan;
2. calculated monthly call minutes, messages, and data consumption;
3. compared usage against the allowances included in the plan;
4. calculated charges for usage exceeding each allowance;
5. added the plan's fixed monthly fee.

This created a monthly revenue measure that could be compared across customers and plans.

## 📈 Customer Behavior Analysis

Customer behavior was analyzed separately for **Surf** and **Ultimate** subscribers.

The analysis examined monthly:

- call minutes;
- number of text messages;
- internet consumption;
- customer revenue.

For each metric, descriptive statistics including the **mean, variance, and standard deviation** were calculated.

Histograms were also used to compare the distributions between plans and identify differences in customer usage patterns.

## 🧪 Statistical Hypothesis Testing

Two statistical hypotheses were evaluated.

### 1. Surf vs. Ultimate Revenue

The first test investigated whether average monthly revenue differs between customers subscribed to the two plans.

**Null hypothesis (H₀):**

Average monthly revenue is equal for Surf and Ultimate customers.

**Alternative hypothesis (H₁):**

Average monthly revenue is different between Surf and Ultimate customers.

### 2. NY-NJ vs. Other Regions

The second test investigated whether average monthly revenue for customers in the **NY-NJ area** differs from customers in other regions.

**Null hypothesis (H₀):**

Average monthly revenue is equal between NY-NJ customers and customers from other regions.

**Alternative hypothesis (H₁):**

Average monthly revenue is different between NY-NJ customers and customers from other regions.

Independent-sample statistical tests were used to evaluate these hypotheses using a predefined significance level.

## 💡 Analytical Insights

The analysis provides several perspectives on Megaline's customer base:

- Surf and Ultimate customers show different patterns of monthly usage;
- customer consumption can exceed the allowances included in the subscribed plan, creating additional revenue;
- internet consumption represents an important component of monthly customer usage;
- the plans have substantially different pricing structures and included allowances;
- monthly revenue distributions can be compared statistically rather than relying only on descriptive averages;
- geographic segmentation provides an additional perspective on differences in customer revenue.

Statistical conclusions are based on the available sample and should be interpreted within the scope of the analyzed data.

## 🚀 Business Applications

The analysis can support business decisions such as:

- comparing the revenue performance of prepaid plans;
- supporting advertising budget allocation;
- understanding customer usage patterns;
- identifying services that frequently generate overage charges;
- evaluating plan allowance structures;
- supporting customer segmentation strategies;
- identifying opportunities for plan migration or personalized offers;
- improving telecom pricing and marketing decisions.

## ⚠️ Limitations

The analysis is based on a sample of Megaline customers and activity observed during 2018.

The results therefore describe the behavior of the available sample and should not automatically be generalized to the entire customer population or to different time periods.

The statistical tests evaluate differences in average revenue but do not establish causal relationships between plan selection, geography, and customer revenue.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- SciPy
- Jupyter Notebook
- Statistical Hypothesis Testing
- Exploratory Data Analysis

## 📁 Repository Structure

```text
megaline-plan-revenue-analysis/
│
├── README.md
│
├── data/
│   ├── megaline_calls.csv
│   ├── megaline_internet.csv
│   ├── megaline_messages.csv
│   ├── megaline_plans.csv
│   └── megaline_users.csv
│
└── notebook/
    └── megaline_plan_revenue_analysis.ipynb
