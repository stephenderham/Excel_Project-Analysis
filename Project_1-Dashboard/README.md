# Excel Salary Dashboard

![1_Salary_Dashboard.png](../Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This project allows users to interrogate salary data by role, location, and experience level to better understand trends and patterns in compensation across the industry.

### Dashboard File
Final dashboard download: [Project_1-Dashboard.xlsx](Project_1-Dashboard.xlsx)

### Excel Skills Used

The following Excel skills were utilized for analysis:

-  Charts
-  Formulas and Functions
-  Data Validation

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information. It includes detailed information on:

-  Job titles
-  Salaries
-  Locations
-  Skills

## Dashboard Build

### Charts

####  Data Science Job Salaries - Bar Chart

<img src="../Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

-  **Excel Function:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
-  **Data Organization:** Sorted job titles by descending salary for improved readability.
-  **Insights Gained:** This enables quick identification of salary trends.

#### Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](../Images/1_Salary_Dashboard_Country_Map.gif)

-  **Excel Function:** Utilized Excel's map chart feature to plot median salaries globally.
-  **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
-  **Data Representation:** Plotted median salary for each country with available data.
-  **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

####  Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

-  **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
-  **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
-  **Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table

![1_Salary_Dashboard_Screenshot1.png](../Images/1_Salary_Dashboard_Screenshot1.png)

Dashboard Implementation

<img src="../Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

-  **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

![1_Salary_Dashboard_Type.png](../Images/1_Salary_Dashboard_Screenshot2.png)

Dashboard Implementation:

<img src="../Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

<img src="../Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. This dashboard allows users to make informed decisions about the data science job market.
