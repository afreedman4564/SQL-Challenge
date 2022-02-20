# SQL-Challenge

## Data modelling
- Quick Database Design website leveraged: https://app.quickdatabasediagrams.com/#/
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

![](/Images/CountEmployeesTable.png)

- salary sum from salary table

![](/Images/SalaryTotalSalaryTableTest.png)


## Perform below data analyses using postgres:
### 1. List the following details of each employee: employee number, last name, first name, sex, and salary.
- join employees and salary table on emp_no
- confirm accurate pull by creating view and doing general calcs to confirm accurate join
- use calculation of view after join to confirm total is accurate

![](/Images/SalaryTotalSalaryView.png)

### 2. List first name, last name, and hire date for employees who were hired in 1986.
- confirm accurate pull by calculating frequency distribution by year from employees table

![](/Images/CountYearEmployeesTable.png)

- apply filter with WHERE statement, limiting to only hires in 1986



### 3. List the manager of each department with the following information: department number, department name, the manager's employee number, last name, first name.
- confirm accurate by calculating count with GROUP BY statement application to original table: dept_manager

![](/Images/DeptMngrFrequencybyDeptMngrTable.png)

- join dept_manager on departments by dept_no
- use calculation of view after join to confirm accurate

![](/Images/DeptMngrFrequencybyDeptMngrView.png)

### 4. List the department of each employee with the following information: employee number, last name, first name, and department name.
- confirm accurate by calculating count with GROUP BY statement application to original table: dept_emp

![](/Images/DeptEmpFrequencybyDeptEmpTable.png)

- join employees table to dept_emp and departments by emp_no and dept_no respectively
- use calculation of view after join to confirm accurate

![](/Images/DeptEmpFrequencybyDeptEmpPostJoin.png)


### 5. List first name, last name, and sex for employees whose first name is "Hercules" and last names begin with "B."
- leverage employees table using WHERE statement to id employees with first name "Hercules" and LIKE with % function to grab those with last name starting with 'B'

### 6. List all employees in the Sales department, including their employee number, last name, first name, and department name.
- calculate distribution by department of employees from dept_emp table

![](/Images/CountDeptNumberDeptEmpTable.png)

- perform join of employees table on dept_emp and departments tables using emp_no and dept_no respectively
- perform count post join to confirm accuracy

![](/Images/SalesDeptEmpCountPostJoin.png)

### 7. List all employees in the Sales and Development departments, including their employee number, last name, first name, and department name.
- calculate distribution by department of employees from dept_emp table

![](/Images/CountDeptNumberDeptEmpTable.png)

- perform join of employees table on dept_emp and departments tables using emp_no and dept_no respectively
- perform count post join to confirm accuracy

![](/Images/SalesDevelopmentDeptEmpCountPostJoin.png)

### 8. In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.
- use group by and order by to provide list

## Bonus
### 1. Import the SQL database into Pandas.
- Create table, merging employees, salary and titles on emp_no and title_id/emp_title_id respectively
- Order by salary
- create trend to understand general curve of salary and whether natural breaks exist

![](/Images/SalaryTrend.png)

### 2. Create a histogram to visualize the most common salary ranges for employees.
![](/Images/SalaryDistributionbyCategory.png)
     
### 3. Create a bar chart of average salary by title.

![](/Images/SalaryDistributionbyTitle.png)
    
    

