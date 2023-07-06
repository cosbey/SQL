# Filter a SQL Query

## Lab Objective:

As a security analyst, knowing how to make better queries to retrieve specific pieces of data can help you find the security-related information you need more efficiently.

In this lab activity, we’ll apply basic filters to SQL queries to retrieve information from a MariaDB database.

MariaDB is a popular open source relational database that is compatible with MySQL.

This activity provides you with a great opportunity to apply what you’ve learned and add filters to SQL queries.

_**Note:** The terms **row** and **record** are used interchangeably in this lab activity._

## Lab Purpose

Our purpose in this lab is to get specific information about employees, their machines, and the departments they’re in. Your team needs this data to perform various tasks, such as running updates, posting a privacy notice in certain departments, and sending an alert to an employee with an issue on a machine.

As an analyst, we are responsible for finding the required information by querying a database. We’ll add filters to your queries to locate the information more quickly.

Here’s how we’ll do this task: **First**, we’ll list all organization machines and their operating systems. **Second**, we’ll list all machines with the operating system OS 2. **Third**, we’ll list all the employees in the Finance and Sales departments. **Fourth**, you’ll obtain information about machines.


>_**Note:** In this lab you’ll be working with the organization database and the tables it contains._




## Task 1. List all organization machines

In this task, you need to get a list of all organization machines and their operating systems. The data is contained in the `machines` table. You’ll need to use the `SELECT` keyword to return specific columns.

- Run a SQL query to retrieve only the `device_id` and `operating_system` columns from the `machines` table.

![Pasted image 20230705212847](https://github.com/cosbey/SQL/assets/32424700/092f8ad6-60be-4ae8-8fb1-507ba42b27a5)

**How many rows were returned from the machines table?** (*You can view the number of rows at the bottom of the output*.)

- `200`
- 100
- 250
- 300


## Task 2. Retrieve a list of the machines with OS 2

In this task, you need to obtain a list of all machines with the `'OS 2'` operating system because these machines need an update. To get this information, you’ll run your first SQL query with a filter.

- Select all the records from the `machines` table with a value of `'OS 2'` in the `operating_system` column. Replace the value `X` with the correct string:

![Pasted image 20230705213416](https://github.com/cosbey/SQL/assets/32424700/7962e89a-d947-49ee-af3f-1d411ecb8673)

>_**Note:** The `WHERE` clause allows you to filter the results returned by a query by returning only the records that satisfy the condition._

**How many machines in the database use the OS 2 operating system?**

- 44
- 200
- 88
- `80`

## Task 3. List employees in specific departments

In this task, you need to retrieve a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about handling confidential financial information will be posted to these offices.

1. Filter the rows returned from `department` column in the `employees` table to include only employees from the `'Finance'` department. Replace `X` with the appropriate column name and `Y` with the appropriate value to complete the filter:

![Pasted image 20230705213948](https://github.com/cosbey/SQL/assets/32424700/5333b049-f28d-4a18-8c6e-fbdcb7036deb)

**What is the employee_id of the first row returned?**

- 1001
- `1003`
- 1049
- 1119

2. Modify the previous query so that it returns employees who are in the `'Sales'` department.

![Pasted image 20230705214041](https://github.com/cosbey/SQL/assets/32424700/b27af36b-ed03-455c-b30d-c67b324894fa)

**How many employees work in the Sales department?**

- 10
- `33`
- 17
- 42

## Task 4. Identify employee machines

Your team recently discovered that there are issues with machines in the South building. In this task, you need to obtain certain employee and computer information.

A machine in `'South-109'` has an issue. You need to determine which employee uses that computer so you can send them an alert.

1. Write a query to identify which employee uses the office in `'South-109'`. (The data must be returned from the `office` column in the `employees` table.)

![Pasted image 20230705214736](https://github.com/cosbey/SQL/assets/32424700/2d2547c0-158f-4071-bc2a-0d26d8928692)

**Which of the following employees uses the computer with the issue?**

- jhill
- `jlansky`
- nmitchell
- tsnow


Next, your team has determined that there is an issue with all the machines in the South building. Offices in the organization are named with the building name, a hyphen, and the office number in that building (for example, `'South-109'`).

2. Modify the query you used in the previous step so that it returns information on all the employees in the `'South'` building. Use the `LIKE` operator with `%` in this query.

>_**Note:** The `LIKE` keyword in SQL performs simple string matches. The matching pattern may include the wildcard `%` to represent a string of any length. This wildcard may be placed both before and after the targeted substring._

![Pasted image 20230705215040](https://github.com/cosbey/SQL/assets/32424700/a5ce3cea-d086-4dca-8f37-38f9c69cb3c9)

**Which department does the first employee listed in the South building belong to?**

- `Finance`
- Marketing
- Sales
- Information Technology



## Lessons Learned:


In this lab, we have used basic SQL filtering queries to:

- apply the `WHERE` clause to filter what a SQL query returns and
- use the `LIKE` operator to filter for patterns.









