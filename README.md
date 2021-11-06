# Pewlett Hackard Analysis

## Overview of Analysis

The purpose of this analysis is to convert a bunch of csv files from Pewlett Hackard into a relational database using Postgresql (SQL). There are six initial csv files that contain employee, manager, department, salary and title information that needed to be transformed into database. By creating this database of the employee information from Pewlett Hackard, the number of retiring employees can be determined so that departments know how many employees need to be replaced and create a program for older employees to mentor and train in-coming or newer employees to create a more successful work environment.

## Results

In order to create the database of Pewlett Hackard information, the relationships between the six csv tables had to be determined and a schema was created to help identify the primary and foreign keys. The six tables with the correct relationships were created in SQL and the csv files were imported with the corresponding table. Once all of the tables were imported, the data could be investigated further. The number of retiring employees was determined by creating a new table to hold employees with a birthdate between 1952 and 1955 and a hire date 1985 and 1988 as seen in the image below.
![Retirement Employee Information](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_info.png)

### The number of retiring employees by their title

![Retirement Employee Titles](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_titles.png)

- The number of retiring employees by their company title was determined by gathering individual employee's first and last name, their title and the date they were hired to the day they can retire using the previously determined birth years. 
- ![Retirement Employee Titles Table](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_titles_csv.png) 
  This is the first couple of rows from the create table that was exported as a csv file. The problem with this table is that some employees appear more than once since they changed titles over the course of their employeement.
- In order to get a better idea of retiring employee's titles, a new table was created using only unique titles for employees which was done with the DISTINCT ON () function.
 ![Unique Employee Titles](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Unique_titles.png) 
 This is what the new table looks like once only unique titles for each employee number are used. 
 ![Unique Employee Titles Table](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Unique_titles.csv.png)
- Finally, the number of position titles was counted to understand how many retiring employees by each position would need to be replaced, using the following query. 
 ![Retiring Employee Titles](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Retiring_titles.png) Now that number of position titles have been counted it is clear that there are a lot of senior positions that will be vacated by retiring employees that need to be replaced. This data is grouped by the title and ordered in descending order. 
 ![Retiring Employee Titles Table](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_titles_csv.png)

### The number of employees eligible as mentors

![Mentorship Eligibilty](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Mentorship_eligibilty.png)

- With the large number of employees that will be retiring in the near future from Pewlett Hackard, a new program has been suggested that will allow senior employees to act as mentors for in-coming or newer employees to help with training and learning the inside outs of each job. Employees with a birthdate in the year of 1965 and are still employeed at Pewlett Hackard. 
![Mentorship Eligibilty Table](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Mentorship_eligibilty_csv.png) The above image shows the first rows of employees eligible for the mentorship program after it was exported as a csv file. There are over 1,500 employees eligible for the mentorship program. However, there should probably be more requirements for the mentorship program besides birthdate. It might be a good idea to consider how long the employees have been at Pewlett Hackard since someone could have been born in 1965 but only worked at Pewlett Hackard for a short amount of time. This program would be really beneficial for everyone involved since it would allow new employees to gain experience from experienced employees and help acclimate new employees. This program could really improve employee retention and create a more cohesive workforce.

## Summary

All of this analysis has shown that there are a lot of employees that are eligible to retire which will vacate a ton of positions inside of the company that will have to be filled.

- One of the big questions raised about the impending 'silver tsunami' of retiring employees, is how many roles will need to be filled? There is a total of 300,024 employees at Pewlett Hackard and 41,380 of them are of retirement age. That's about 14% of the entire company that will be leaving and from the above analysis, it is clear that a lot of the retiring employees hold more senior positions which are important positions and either internal promotions will need to occur or external new hires will need to be found as replacements.
- The second big question regarding departure of the 'silver tsunami' is are there enough eligible mentors in the departments to mentor the next generation of Pewlett Hackard employees? While most of the retiring employees hold senior positions, the titles of the eligible mentors were gathered into the below table. 
![Mentorship Employee Titles](https://github.com/likenberry/Pewlett-Hackard-Analysis/blob/main/Resources/Mentorship_count_csv.png) 
The eligible mentors do hold higher up positions in the company but which would mean they have a lot of experience and can train the new employees accordingly. There are 1,550 eligible mentors and that's less than 0.03% of the retiring employees meaning that each mentor would have to train too many new employees at a time to be realistic. Therefore the mentorship program would need to be expanded to maybe include more employees not only based on their birthdate but maybe experience as well. The mentorship program is a great idea but would need some more adjustments before it would be implemented.

## Resources

- Data Source: departments.csv, dept_emp.csv, dept_managers.csv, employees.csv, salaries.csv, titles.csv
- Software: pgAdmin 4 Version 6.1, Visual Studio Code 1.61.2
