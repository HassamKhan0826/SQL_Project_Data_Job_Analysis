# Data Analyst Job Market Analysis

## Project Overview

This project analyzes Data Analyst job postings to identify the skills, salaries, and characteristics associated with high-paying Data Analyst roles.

The analysis uses **PostgreSQL and SQL** to investigate job-market trends and **Python-based Exploratory Data Analysis (EDA)** to complement the SQL findings with visual analysis.

The project focuses on answering practical questions such as:

- What are the highest-paying Data Analyst roles?
- Which companies offer these opportunities?
- What skills are most frequently requested?
- Which skills appear in high-paying Data Analyst positions?
- Which skills provide the best combination of demand and salary?
- How does technical skill breadth relate to compensation?

The objective is to transform raw job-posting data into **actionable insights about the Data Analyst job market**.

---

## Business Problem

The Data Analyst profession is becoming increasingly technical. Employers may expect candidates to work with SQL, Python, business intelligence platforms, databases, and other analytical tools.

For someone entering the field, an important question is:

> **Which skills are actually valuable in the job market, and which skills should be prioritized?**

This project analyzes job-posting data to identify the skills that appear most frequently, the skills associated with higher-paying positions, and the overall technical requirements of Data Analyst roles.

---

## Project Objectives

- Identify the highest-paying Data Analyst positions.
- Identify companies associated with high-paying roles.
- Analyze the most demanded Data Analyst skills.
- Determine which skills appear in high-paying Data Analyst positions.
- Compare skill demand with salary.
- Identify skills that provide a strong combination of demand and compensation.
- Perform exploratory data analysis using Python.
- Visualize important findings.
- Translate analytical results into practical business insights.

---

## Dataset

The project uses a relational dataset containing Data Analyst job-posting information.

| Table               | Description                                                            |
| ------------------- | ---------------------------------------------------------------------- |
| `job_postings_fact` | Job posting information including title, salary, location, and company |
| `company_dim`       | Company information                                                    |
| `skills_dim`        | Available skills and skill names                                       |
| `skills_job_dim`    | Relationship between job postings and required skills                  |

The relationship between jobs and skills is many-to-many:

```text
job_postings_fact
       │
       │ job_id
       ▼
skills_job_dim
       │
       │ skill_id
       ▼
skills_dim
A single job can have multiple skills, while a single skill can appear in multiple jobs.

Tools & Technologies
SQL & Database
PostgreSQL
SQL
Common Table Expressions (CTEs)
JOINs
LEFT JOIN
INNER JOIN
GROUP BY
Aggregate Functions
Subqueries
Filtering
ORDER BY
LIMIT
CASE Statements
UNION
Date Manipulation
Conditional Aggregation
Python & EDA
Python
Pandas
NumPy
Matplotlib
Jupyter Notebook
Development Tools
VS Code
Git
GitHub

# Project Structure
Data Analyst Job Market Analysis/
│
├── advanced_sql/
│   ├── 2_dates.sql
│   ├── 3_cases.sql
│   ├── subqueries&CTE's.sql
│   └── unions.sql
│
├── csv_files/
│   ├── company_dim.csv
│   ├── job_postings_fact.csv
│   ├── skills_dim.csv
│   └── skills_job_dim.csv
│
├── sql_load/
│   ├── 1_create_database.sql
│   ├── 2_create_tables.sql
│   └── 3_modify_tables.sql
│
├── sql_project/
│   ├── EDA/
│   │   └── data_analyst_job_market_eda_project.ipynb
│   │
│   └── Graphs/
│       ├── 01_skill_demand.png
│       ├── 02_salary_ranking.png
│       ├── 03_skill_coverage_heatmap.png
│       ├── 04_salary_vs_skill_breadth.png
│       └── 05_salary_distribution.png
│
├── 1_top_paying_jobs.sql
├── 2_top_paying_job_skills.sql
├── 3_top_demanded_skills.sql
├── 4_top_paying_skills.sql
├── 5_optimal_skills.sql
│
├── .gitignore
└── README.md

SQL Analysis
1. Top-Paying Data Analyst Jobs

File: 1_top_paying_jobs.sql

Identifies the highest-paying Data Analyst positions based on annual salary while filtering for relevant job characteristics.

The analysis considers:

Data Analyst positions
Remote opportunities
Available salary information
Salary ranking
2. Skills Required by Top-Paying Jobs

File: 2_top_paying_job_skills.sql

Connects the highest-paying Data Analyst jobs with their required skills.

The analysis uses the relationship:

job_postings_fact
        ↓
skills_job_dim
        ↓
skills_dim

This identifies the technical skills associated with high-paying Data Analyst positions.

3. Most In-Demand Data Analyst Skills

File: 3_top_demanded_skills.sql

Identifies the skills that appear most frequently across Data Analyst job postings.

The objective is to determine which technical skills employers request most often.

4. Highest-Paying Skills

File: 4_top_paying_skills.sql

Examines the relationship between individual skills and salary.

This provides a different perspective from skill frequency by identifying skills associated with higher-paying positions.

5. Optimal Skills

File: 5_optimal_skills.sql

Combines skill demand and salary to identify skills that provide a strong balance between market demand and compensation.

The objective is to identify skills that are both:

Frequently requested
Associated with competitive compensation
Exploratory Data Analysis

The SQL analysis is complemented by a focused Python EDA.

Notebook:

sql_project/EDA/data_analyst_job_market_eda_project.ipynb

The EDA examines:

Dataset structure
Salary distribution
Skill demand
Skill coverage across job postings
Technical skill breadth
Relationship between salary and number of listed skills
Key Visualizations
Most In-Demand Skills

Key Finding: SQL is the most consistently represented skill in the analyzed sample, followed by Python and business intelligence / visualization technologies.

This indicates that modern Data Analyst roles commonly require a combination of:

SQL + Python + BI / Visualization

rather than relying on a single technical skill.

Salary Ranking

Key Finding: There is considerable salary variation even among high-paying Data Analyst positions.

Compensation can be influenced by factors such as:

Role scope
Seniority
Technical specialization
Company
Industry
Responsibilities
Skill Coverage Across Job Postings

The heatmap shows how major skills are distributed across individual job postings.

It helps distinguish between:

Skills appearing consistently across many jobs.
Skills concentrated in specific positions.
Specialized technologies required by only a subset of roles.
Key Insights
1. SQL Is a Core Data Analyst Skill

SQL appears consistently across the analyzed high-paying Data Analyst roles.

This reinforces SQL's importance for:

Extracting business data
Joining relational datasets
Aggregating information
Building analytical queries
Answering business questions
2. Python Complements SQL

Python is also highly represented in the analyzed roles.

Python can complement SQL for:

Data cleaning
Exploratory analysis
Data manipulation
Automation
Statistical analysis
Visualization
3. BI and Visualization Skills Remain Important

Business intelligence and visualization technologies also appear frequently in the analyzed postings.

This reflects the importance of communicating analytical results to stakeholders rather than simply producing database queries.

4. More Skills Do Not Automatically Mean Higher Salary

The number of listed skills alone does not explain salary differences in this sample.

A role requiring fewer technologies can still offer higher compensation than a role requiring a larger technical stack.

This suggests that:

Skill specialization and role characteristics can be more important than simply knowing more tools.

5. Data Analyst Roles Require a Broad Technical Ecosystem

The analyzed jobs contain skills across several categories:

SQL
Python
R
Excel
Tableau
Power BI
Pandas
NumPy
Cloud platforms
Databases
Development and collaboration tools

This demonstrates that modern Data Analyst roles can extend beyond traditional spreadsheet-based reporting.

Business Recommendations

Based on the analysis, a practical Data Analyst skill-development strategy should prioritize strong analytical foundations before simply accumulating additional technologies.

A strong foundation can be represented as:

SQL
 ↓
Data Analysis
 ↓
Python
 ↓
BI / Visualization
 ↓
Specialization

The results particularly support developing strong SQL capabilities and then complementing them with Python and BI skills.

Specialized technologies can then be added based on the target role, industry, and job market.

Data Quality Considerations

The dataset is stored at job-skill grain, meaning that a single job can appear in multiple rows because each skill is represented separately.

For example:

Job 101 → SQL
Job 101 → Python
Job 101 → Tableau

Therefore, salary analysis must be performed at the job level rather than directly across job-skill rows.

The EDA handles this by reducing the data to one record per job when calculating job-level salary metrics.

Sample Limitation

The exported skill-analysis dataset contains 8 unique job IDs despite the analysis targeting the top 10 jobs.

Therefore, the EDA findings should be interpreted as findings from the available sample rather than as a statistically representative description of the entire Data Analyst job market.

Limitations
The sample focuses on selected high-paying Data Analyst roles.
The dataset does not represent the entire Data Analyst job market.
Salary associations do not establish causation.
Salary can be influenced by experience, seniority, industry, company, specialization, and other factors.
The exported skill dataset contains fewer unique job postings than the intended top-10 analysis.

Therefore, the findings should be interpreted as directional insights rather than universal conclusions about the Data Analyst profession.

Conclusion

This project demonstrates an end-to-end workflow for analyzing the Data Analyst job market using SQL and Python.

Raw Job Data
     ↓
PostgreSQL Database
     ↓
SQL Analysis
     ↓
Business Questions
     ↓
Python EDA
     ↓
Data Visualization
     ↓
Business Insights

The findings indicate that SQL remains a highly consistent requirement across the selected high-paying Data Analyst roles, while Python and BI/visualization technologies provide complementary capabilities.

The analysis also demonstrates that evaluating skills requires more than simply counting how often a technology appears. Combining skill demand, salary, and job-level context provides a more meaningful view of the Data Analyst job market.

Skills Demonstrated
Technical
PostgreSQL
SQL
CTEs
JOINs
LEFT JOIN
INNER JOIN
Aggregations
Subqueries
CASE Statements
UNION
Data Transformation
Python
Pandas
NumPy
Matplotlib
Exploratory Data Analysis
Analytical
Business Question Formulation
Data Validation
Data-Grain Awareness
Descriptive Analysis
Comparative Analysis
Salary Analysis
Skill-Demand Analysis
Data Visualization
Insight Generation
Business
Market Analysis
Identifying Skill Demand
Evaluating Compensation Patterns
Evidence-Based Recommendations
Communicating Analytical Findings
```
