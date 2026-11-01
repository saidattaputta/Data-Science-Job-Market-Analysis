# Data Science Job Market Analysis — SQL

A SQL-based job-market analysis focused on Data Analyst roles. The project queries job-posting and skill tables to explore remote high-paying roles, skills requested by high-paying jobs, skill demand, salary associations, and the balance between demand and compensation.

## Business Questions

1. What are the highest-paying remote Data Analyst roles with disclosed salaries?
2. Which skills occur in high-paying job postings?
3. Which skills appear most frequently in Data Analyst job advertisements?
4. Which skills have the highest average salary in the available postings?
5. Which skills combine higher demand with higher average salary?

## Results and Chart-Based Findings

The repository includes four saved visual outputs. The charts are the persisted evidence; the underlying query-result tables are not committed as separate CSV files. Values below are therefore described at the level supported by the chart axes and plotted ordering, rather than reported as exact query results.

### Most in-demand skills

The saved chart ranks the following five skills highest by posting count:

1. SQL — approximately 92,000 postings on the chart scale
2. Excel — approximately 67,000
3. Python — approximately 57,000
4. Tableau — approximately 46,000
5. Power BI — approximately 39,000

**Finding:** the chart shows SQL and Excel as the most frequently requested skills in this Data Analyst posting sample, with Python and BI tools also prominent.

![Most in-demand skills](most_in_demand.png)

### Highest-paying Data Analyst roles

The saved top-paying jobs chart places the Data Analyst title at the top, with a plotted average salary near $650,000. The next role shown, Director of Analytics, is around $335,000, followed by Associate Director - Data Insights at roughly $255,000.

**Interpretation caution:** these chart values are unusually high for typical Data Analyst compensation. They are averages from the underlying filtered job-posting sample and may be affected by extreme values, small posting counts, salary-period conversion, or role-title aggregation. They should be treated as query outputs requiring validation—not as realistic salary expectations.

![Top-paying Data Analyst jobs](top_paying.png)

### Highest-paying skills

The top-paying skills chart ranks SVN at approximately $400,000 in average salary, followed by Solidity at around $180,000, then Couchbase, DataRobot, and Go at roughly $155,000–$165,000.

**Interpretation caution:** the high values for specialist skills may be driven by a small number of job advertisements. The result chart does not display the sample size per skill, so these rankings should not be used as stable compensation benchmarks without checking posting counts and outliers.

![Top-paying skills](top_paying_skills.png)

### Demand versus salary: most optimal skills

The saved scatter plot compares skill demand (job posting count) with average salary. The visual includes technologies such as Snowflake, Spark, Databricks, Airflow, Kafka, PyTorch, TensorFlow, PySpark, Pandas, and GCP.

The chart shows a trade-off between demand and salary: Snowflake and Spark sit toward the higher-demand end of the plotted sample, while some lower-frequency skills such as Kafka, PyTorch, and TensorFlow appear at higher salary levels.

![Demand versus salary for selected skills](most_optimal.png)

## SQL Analysis

The five scripts under project_sql/ address:

| Query | Analysis |
|---|---|
| 1_top_paying_jobs.sql | Highest-paying remote Data Analyst roles with non-null salary |
| 2_top_paying_job_skills.sql | Skills attached to the highest-paying roles |
| 3_most_in_demand_skills.sql | Most frequently requested Data Analyst skills |
| 4_top_paying_skills.sql | Average salary by skill |
| 5_most_optimal_skills.sql | Joint view of skill demand and salary |

The sql_load/ directory contains database/table setup and table modification scripts.

## Repository Structure

\`\`\`text
.
├── project_sql/
│   ├── 1_top_paying_jobs.sql
│   ├── 2_top_paying_job_skills.sql
│   ├── 3_most_in_demand_skills.sql
│   ├── 4_top_paying_skills.sql
│   └── 5_most_optimal_skills.sql
├── sql_load/
│   ├── 1_create_database.sql
│   ├── 2_create_tables.sql
│   ├── 3_modify_tables.sql
│   └── practice.sql
├── most_in_demand.png
├── most_optimal.png
├── top_paying.png
├── top_paying_skills.png
└── README.md
\`\`\`

## Running the Queries

1. Set up a compatible SQL database.
2. Load the job-postings and dimension tables expected by the queries: job_postings_fact, company_dim, skills_job_dim, and skills_dim.
3. Execute the scripts in project_sql/ after the source tables are available.
4. Review the result sets and compare them with the saved chart exports.

The source data and query result tables are not stored in this repository. The visualizations are committed, but a fully reproducible run requires the original database tables or a compatible dataset.

## Technology

SQL, relational joins, CTEs, aggregations, salary analysis, and data visualization.

## Limitations and Interpretation Notes

- Findings depend on the source dataset, collection period, location/remote filters, and the salary fields available.
- Only postings with usable salary data can contribute to salary averages.
- Salary charts contain unusually high averages; check sample sizes, units, pay-period conversion, and outliers before interpreting them as expected compensation.
- Skill frequency measures what employers mention in job advertisements, not the causal effect of a skill on salary or employability.
- The saved visual files do not expose exact underlying query rows or sample sizes for every plotted category.
- Refresh the source data before using the results as current job-market guidance.
- The practice.sql file is empty in the current repository.

## Recommendations for Further Analysis

Add exported result tables with posting counts and salary distributions, report medians and interquartile ranges alongside means, include sample sizes in the top-paying skill chart, and define the salary currency and annualization logic explicitly.

---

**Sai Datta Putta**

[LinkedIn](https://www.linkedin.com/in/sai-datta-putta/)
