# Excel Project Data Analyst Salary Calculator

 This data analyst salary dashboard was created to help give better insight on the jobs in the market with salary information based on title, location, and type of position.
 [Check out my work here](Salary-Dashboard-Project)  
 
 ![salary_dashboard](https://github.com/user-attachments/assets/b91f6603-15d3-4507-a150-cf2c6db5d415)

## Introduction  

This data jobs salary dashboard helps job seekers like myself cycle through different job titles to help find the median salaries for those jobs and what job site had the most postings to help them find more opportunities.

## Excel Skills Used

The following Excel skills were utilized for the analysis in this project:

- Formulas and Functions
- Data Validation
- Charts

## Data Jobs Dataset

The data used for this project contains real-world data job postings from 2023. This dataset was provided from an Excel course by Luke Barousse. It had information such as:

- Job Titles
- Salaries
- Locations
- Skills

# Dashboard Build

## Formulas and Functions

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
This Formula is similar to the one above with some slight changes
- **Count:** With the COUNT function it allows us to count how many job postings there are within the filters selected for job title and job type
- **Purpose:** Below is a screenshot of the table that is returned from this formula

![count of jobs table](https://github.com/user-attachments/assets/6400c449-d609-4512-854d-fc3a4fb91ba7)


```
=FILTER(J2#,NOT(ISNUMBER(SEARCH("and",J2#)))*(J2#<>0))
```
This formula helps us find the unique job titles
- **Unique List Generation:** Using the FILTER function we can exclude the titles that include "and" and exclude values that come back with as 0
- **Purpose:** Below is a screenshot of the table that is returned from this formula

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
- **Purpose:** Below is a screenshot of the table that is returned from these formulas

![job platform table](https://github.com/user-attachments/assets/2b51b993-def3-42d0-88eb-f3d4384b4aeb)

## Data Validation

- **Enhanced Data Validation:** Using filtered lists as a data validation rule for the Job Title, Type, and Country
- **Dashboard restrictions:** With the lists premade it prevents entries to be submitted that do not fit the preset options ensuring a better overall usability
Below are two of the filtered lists shown with all the available options

![job type list](https://github.com/user-attachments/assets/900c6e34-ff63-4d27-8382-577eefe92ae8)  
![job title list](https://github.com/user-attachments/assets/b2bdf41b-ea02-47cb-94e1-b3071f2c4af0)  

## Charts

![first chart](https://github.com/user-attachments/assets/68e000cb-c80c-4c8d-a4bc-4dc7d94e33ad)

This chart in the dashboard is used to help highlight the median salary for data jobs based on title

- **Excel Features:** Utilizing a bar chart I was able to visualize the findings on median salaries based on the job title
- **Organization:** Having the chart be shown in decending order allows for better readability
- **Design:** The chart also updates the color based on the selected filter to help highlight what you may be looking for on the graph
- **Insights:** Looking at this graph there is an higher pay salary trend for the Senior/Engenieering roles compared to the analyst roles

![second chart](https://github.com/user-attachments/assets/5c03b266-2e3c-47bf-b868-e9ce28782e75)

This chart in the dashboard is used to highlight geographical differences in the data job market

- **Excel Features:** Ulitlizing the map chart feature I was able to plot median salaries based on country
- **Design:** The color of the highlighted countries changes based on the salary, darker shade meaning a higher salary for that position
- **Insights:** Looking at this graph it helps give a quick grasp of the salary differences throughout the different countries

![third chart](https://github.com/user-attachments/assets/4fad2ef6-3599-48fc-9378-a3d5ce0d2977)

This chart is similar to the first chart having the difference be it is focused on the job type rather than the title

- **Insights:** In this graph we can see that having a full time job helps provide the better salary for the position Data Analyst

# Conclusion

This dashboard is designed to help showcase the salary trends across the different data positions. Utilizing my knowledge in excel it helped me put together the dashboard using Functions and Formulas, Data Validation, and Charts. Since I am looking for a job in the data job market this dashboard and project have helped give me insights into what can affect the slaries of a job also it has given me insights as to what I can expect and where to look for these data opportunities.












