# Excel Project Data Analyst Salary Calculator

 This data analyst salary dashboard was created to help give better insight on the jobs in the market with salary information based on title, location, and type of position  
 [Check out my work here](Salary-Dashboard-Project)  
 
 ![salary_dashboard](https://github.com/user-attachments/assets/b91f6603-15d3-4507-a150-cf2c6db5d415)

## Introduction  

This data jobs salary dashboard helps job seekers like myself cycle through different job titles to help find the average salaries for those jobs and what job site had the most postings to help them find more opportunities

## Excel Skills Used

The following Excel skills were utilized for the analysis in this project

- Formulas and Functions
- Data Validation
- Charts

## Data Jobs Dataset

The data used for this project contains real-world data job postings from 2023. This dataset was provided from an Excel course by Luke Barousse. It had information such as:

- Job Titles
- Salaries
- Locations
- Skills

## Dashboard Build

### Formulas and Functions

```
=MEDIAN(
   IF(
     (jobs[job_title_short]=A2)*
     (jobs[salary_year_avg]<>0)*
     (jobs[job_country]=country)*
     (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
     jobs[salary_year_avg]
))
```
This formula had a lot of functions within it such as:
- **Multi-criteria Filtering:** It checks for job titles, countries, schedule type, and excludes all blank values
- **Median and IF:** Using the MEDIAN and IF function we are able to analyze the entire array
- **Renamed cells:** A lot of the cells have been renamed to help with formula readability
- **Purpose:** Below is a screenshot of the table that is returned from this formula

![median salary table screenshot](https://github.com/user-attachments/assets/7b493d4f-9d4f-4bc7-a223-b4ce023f147d)

```
=COUNT(
   IF(
     (jobs[job_country]=country)*
     (jobs[job_title_short]=A8)*
     (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
     jobs[salary_year_avg]
))
```
This Formula is very similar to the one above with some slight changes
- **Count:** With the COUNT function it allows us to count how many job postings there are within the filters selected for job title and job type

![count of jobs table](https://github.com/user-attachments/assets/6400c449-d609-4512-854d-fc3a4fb91ba7)


```
=FILTER(J2#,NOT(ISNUMBER(SEARCH("and",J2#)))*(J2#<>0))
```
This formula helps us find the unique job titles
- **Unique List Generation:** Using the FILTER function we can exclude the titles that include "and" and exclude values that come back with as 0

![job type table](https://github.com/user-attachments/assets/8b1a9b66-05d8-40b0-9fc8-bd6dda034d16)


```
=UNIQUE(jobs[job_via])
```
```
=SORT(A2:B594,2,-1)
```
```
=SUBSTITUTE(D2,"via ","")
```

I then used these three functions to help find top job platform for the filters put in

- **Unique:** The UNIQUE function helps us find all the unique job sites with data jobs
- **Sorting:** The SORT function then allows me to sort the job sites by most available
- **Substitue:** The SUBSITUTE function then makes the top result more readable for the dashboard

![job platform table](https://github.com/user-attachments/assets/2b51b993-def3-42d0-88eb-f3d4384b4aeb)







