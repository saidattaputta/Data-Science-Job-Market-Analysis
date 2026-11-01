# Data Science Job Market Analysis (SQL)

A SQL analytics project focused on the Data Analyst job market. Using a relational job-postings dataset, the queries examine remote high-paying roles, the skills requested by those roles, overall skill demand, salary associations, and skills that combine demand with compensation.

## Questions

1. What are the highest-paying remote Data Analyst roles with disclosed salaries?
2. Which skills appear in those top-paying job postings?
3. Which skills are most frequently requested across Data Analyst postings?
4. Which skills are associated with higher average annual salaries?
5. Which skills combine meaningful demand with higher salary levels?

## SQL Analysis

The `project_sql/` directory contains five focused queries:

| File | Analysis |
|---|---|
| `1_top_paying_jobs.sql` | Top 10 remote Data Analyst roles by average annual salary |
| `2_top_paying_job_skills.sql` | Skills associated with the highest-paying roles |
| `3_most_in_demand_skills.sql` | Most frequently requested skills |
| `4_top_paying_skills.sql` | Average salary by skill |
| `5_most_optimal_skills.sql` | Joint view of skill demand and salary |

The `sql_load/` directory contains database/table setup and table modification scripts.

## Reported Findings

The existing analysis highlights SQL and Python as prominent Data Analyst skills and identifies visualization, database, and cloud technologies as additional areas of demand. Salary rankings are dataset- and query-specific and should not be interpreted as universal salary guarantees.

## Repository Contents

```text
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
```

## Run the Queries

1. Set up a compatible SQL database.
2. Load the job-postings and dimension tables expected by the queries (`job_postings_fact`, `company_dim`, `skills_job_dim`, and `skills_dim`).
3. Execute the SQL scripts in `project_sql/` in order.
4. Review the result sets alongside the visual summaries.

The SQL uses common relational constructs including joins, CTEs, grouping, sorting, and aggregation. Some scripts assume the schema and data have already been loaded.

## Technology

SQL · Relational data modeling · Job-market analytics

## Limitations

- Results depend on the underlying job-postings dataset, date range, salary coverage, and definition of remote work.
- Only postings with non-null salary values are included in salary calculations.
- Skill frequency measures association in job advertisements, not a causal effect on salary or employability.
- Refresh the source data before making current career-market decisions.


---

**Sai Datta Putta**

[LinkedIn](https://www.linkedin.com/in/sai-datta-putta/)
