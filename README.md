# SQL-Challenge

## Data modelling
- tool used:
- sketch out logical erd to capture the relational schema
![](/ERD/Pewlett%20Hackard%20ERD%20-%20Logical.png)


- physical erd, noting primary, foreign keys as well as data types
![](/ERD/Pewlett%20Hackard%20ERD%20-%20Physical.png)

## Data engineering
- leverage postgres to create table
- use IF EXISTS in DROP TABLE statement so easily refresh as coding
- use COPY statement w/ DELIMITER and CSV HEADER options to make table creation more efficient
*files have to formatted properly to allow COPY statement to apply w/o erroring out

### In order to copy csv into SQL created table follow below steps:
    - Go to file in Explorer window
    - Right click in file of interest and select Properties
    - Go to the Security tab
    - Select Edit
    - Within the Permissions dialogue box click Address
    - Type Everyone in the 'Enter the object names to select' box
    - Select OK
    - Select Full Control to remove restrictions
    - Finally, select Apply and OK

    Congrats! You are now able to copy the csv contents to the empty and recently created data base

## Data Analysis
### Data exploration
- use sql to perform general assessment of data to confirm accurate pulls
- employee counts from employee table



- salary sum from salary table

![](/Images/SalaryTotalSalaryTableTest.png)


## Perform below data analyses using postgres:
### 1. List the following details of each employee: employee number, last name, first name, sex, and salary.
- join employees and salary table on emp_no
- confirm accurate pull by creating view and doing general calcs to confirm accurate join
- use calculation of view after join to confirm accurate

### 2. List first name, last name, and hire date for employees who were hired in 1986.
- confirm accurate pull by calculating frequency distribution by year
- apply filter with WHERE statement, limiting to only hires in 1986
- use calculation of view after join to confirm accurate


### 3. List the manager of each department with the following information: department number, department name, the manager's employee number, last name, first name.
- confirm accurate by calculating count with GROUP BY statement application to original table: dept_manager
- join dept_manager on departments by dept_no
- use calculation of view after join to confirm accurate

### 4. List the department of each employee with the following information: employee number, last name, first name, and department name.
- confirm accurate by calculating count with GROUP BY statement application to original table: dept_emp
- join employees table to dept_emp and departments by emp_no and dept_no respectively
- use calculation of view after join to confirm accurate


### 5. List first name, last name, and sex for employees whose first name is "Hercules" and last names begin with "B."

### 6. List all employees in the Sales department, including their employee number, last name, first name, and department name.

### 7. List all employees in the Sales and Development departments, including their employee number, last name, first name, and department name.

### 8. In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.

## Bonus
### 1. Import the SQL database into Pandas.
     o Create table, merging employees, salary and titles on emp_no and title_id/emp_title_id respectively
     o Order by salary

### 2. Create a histogram to visualize the most common salary ranges for employees.
     
     
### 3. Create a bar chart of average salary by title.
    
    

