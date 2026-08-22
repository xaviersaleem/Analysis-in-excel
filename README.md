# Excel Data Jobs Market Analysis

A business-focused Excel analysis of data job postings, salaries, locations, and skill demand. The project demonstrates how Excel can turn raw job-market data into actionable insights for workforce and career decisions.

## Business Questions

- Does a broader skill set correlate with higher compensation?
- How do salaries vary between the United States and other markets?
- Which skills are most frequently requested by employers?
- Which skills combine strong demand with higher compensation?

## Tools & Techniques

- Microsoft Excel
- Power Query — ETL, cleaning, transformation
- Power Pivot — relational data model
- DAX — analytical measures
- PivotTables & PivotCharts
- Advanced formulas and data visualization

## Data Preparation

Power Query was used to extract and transform job-posting and skill data. The analysis uses separate job and skill tables connected through `job_id`, creating a reusable data model in Power Pivot.

![Power Query – Jobs](https://github.com/user-attachments/assets/9fc53613-08c7-488e-a570-3d194ffcd11c)

![Power Query – Skills](https://github.com/user-attachments/assets/efcba2de-d96c-4445-874b-46f6d504112e)

## Analysis & Findings

### 1. Skills and compensation

The analysis compares the number of skills requested in job postings with median salary across major data roles.

![Skills vs Salary](https://github.com/user-attachments/assets/ddb57e87-4172-4d11-bfc9-6ba1482ace83)

**Takeaway:** More specialized roles tend to combine broader technical requirements with higher compensation. This is an association in the dataset, not proof that learning more skills directly causes higher pay.

### 2. Salary by geography

A DAX measure calculates median salary, with a separate United States filter:

```DAX
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])

US Median Salary :=
CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)
```

![Salary by Region](https://github.com/user-attachments/assets/d0197ba1-2c54-46e9-8c70-d66789bfdb34)

**Takeaway:** Compensation varies substantially by role and geography, with senior technical roles generally commanding higher median salaries.

### 3. Most requested skills

Power Pivot connects the job and skill tables through `job_id`, enabling skill-level analysis across job postings.

![Data Model](https://github.com/user-attachments/assets/f500b4f6-62ad-46c2-8d13-402644188c92)

![Power Pivot](https://github.com/user-attachments/assets/d56a161f-ee1-46a8-8b92-d664db3c5b7d)

![Top Skills](https://github.com/user-attachments/assets/1bb510b5-334c-461c-9040-9982fc58ed57)

**Takeaway:** SQL and Python are prominent skills in the dataset, while cloud technologies such as AWS and Azure also show meaningful demand.

### 4. Pay associated with top skills

A combination PivotChart compares median salary with skill prevalence.

![Skill Pay](https://github.com/user-attachments/assets/a94bb738-e28d-475e-99f6-80f35672ecb)

**Takeaway:** Some technical skills are associated with higher median compensation, but skill-level salary comparisons should be interpreted alongside role, seniority, location, and industry.

## Workbook

The complete Excel workbook is available as [`Project_Analysis.xlsx`](Project_Analysis.xlsx).

## What This Project Demonstrates

This project is designed as a portfolio example of **business analysis in Excel**, including:

- ETL and data cleaning
- Relational data modeling
- DAX measures
- KPI and salary analysis
- Interactive PivotTables and PivotCharts
- Translating quantitative findings into business recommendations

## Portfolio Context

This project complements my Power BI, SQL, and Python analytics projects and demonstrates an end-to-end progression from data preparation to business insight.
