# Perform a SQL Query

## Lab Objective:

In this lab activity, we’ll use `SELECT` and `FROM` in SQL to return the information you need from a database. We’ll also use the `ORDER BY` keyword to sequence the information returned by a query based on a specified column.

It's important to know how to query information from a database because this is a common task you might encounter as a security analyst. You should know how to get the information you need to improve security and keep data safe.



## Lab Purpose:

In this lab, we'll write a few SQL queries to determine which employee devices must be updated. You also need to investigate user login activity to explore if any unusual activity has occurred. The information we'll need is located in the `machines` and `login_attempts` tables in the `organization` database.

Here’s how we’ll do this task: **First**, you’ll obtain information on the employee devices that must be updated. **Next**, we’ll examine the login attempts for unusual activity. **Finally**, we’ll use the `ORDER BY` keyword to sort the data returned by your SQL queries.


>_**Note:** In this lab you’ll be working with the organization database within a MariaDB shell and the tables it contains._

## Lab Tool: 
This activity was conducted within a virtual environment. However, these same SQL queries can be initiated in a real world application of a SOC analyst.
- SQL Server
- Oracle VirtualBox

## Task 1. Retrieve employee device data

In this task, you need to obtain information on employee devices because your team needs to update them. The information you need is in the `machines` table in the `organization` database.

**First**, you need to retrieve all the information about the employee devices.

1. Run the following query to select all device information from the `machines` table:


**SELECT** *
**FROM** machines;

_**Note:** Using the asterisk (`*`) returns all data from the specified table. Also, table names in MySQL are case-sensitive._

The output returns all the contents of the `machines` table:

![Pasted image 20230704185429](https://github.com/cosbey/SQL/assets/32424700/e94eaab3-dcc4-45c6-aa6f-08ece586bfd7)

**Next**, you want to focus on the email client running on various devices.

2. Run the following query to select only the `device_id` and `email_client` columns from the `machines` table. Replace `X` and `Y` with these column names:

**SELECT** X, Y **FROM** machines;

![Pasted image 20230704185701](https://github.com/cosbey/SQL/assets/32424700/5a6d39d3-1d34-4bf9-941c-ee396b142098)


**What email client is returned in the third row?**

- Email Client 3
- `Email Client 2`
- Email Client 4
- Email Client 1

**Now**, you need information on the operating systems used on various devices and their last patch date.

3. Complete the query to return only the `device_id`, `operating_system`, and `OS_patch_date` columns from the `machines` table. Replace `X`, `Y`, and `Z` with these column names:

**SELECT** X, Y, Z **FROM** machines;

**What is the patch date of the first entry?**

- 2021-12-01 
- `2021-09-01`
- 2021-06-01
- 2021-03-01

![Pasted image 20230704190350](https://github.com/cosbey/SQL/assets/32424700/7850743e-5e53-4838-be5c-ea39ebceaea1)

## Task 2. Investigate login activity

In this task, you need to analyze the information from the `log_in_attempts` table to determine if any unusual activity has occurred.

**First**, you need to investigate the locations where login attempts were made to ensure that they’re in expected areas (the United States, Canada, or Mexico).

1. Write a SQL query to select the `event_id` and `country` columns from the `log_in_attempts` table.

![Pasted image 20230704191250](https://github.com/cosbey/SQL/assets/32424700/926e5c8b-7272-40dd-9cc5-0aa05635eb6e)

Were any login attempts made from Australia?

- `No`
- Yes


**Next**, you need to check if login attempts were made outside of the organization's working hours.

2. Write a SQL query that selects the `username`, `login_date`, and `login_time` columns from the `log_in_attempts` table.

![Pasted image 20230704191433](https://github.com/cosbey/SQL/assets/32424700/c666c3f7-d030-4679-8147-0b7ac75ebd3c)



What username is returned in the fifth row?

- *jrafael*
- apatel
- dkot
- mrah



**Now**, you need to get a complete picture of all login attempts.

3. Write a SQL query that selects all columns from the `log_in_attempts` table, using a single symbol after the `SELECT` keyword.

![Pasted image 20230704191710](https://github.com/cosbey/SQL/assets/32424700/4806d8d9-4da4-49c1-93a7-c3b5106b31a1)

## Task 3. Order login attempts data

In this task, you need to use the `ORDER BY` keyword. You'll sequence the data that your query returns according to the login date and time.

**First**, you need to sort the information by date.

1. Run the following query, which orders `log_in_attempts` data by `login_date`:

**SELECT** *
**FROM** log_in_attempts
**ORDER BY** login_date;



**What are the username and login date of the first record returned?**

![Pasted image 20230704191901](https://github.com/cosbey/SQL/assets/32424700/1ca64d33-f382-42b6-b497-bb8d9fc36878)

- mabadi on 2022-05-10
- *ivelasco on 2022-05-08*
- daquino on 2022-05-08
- sbaelish on 2022-05-10

**Now**, you need to further organize the previous results by ordering them by `login_time`.


Click **Check my progress** to verify that you have completed this task correctly.


**Now**, you need to further organize the previous results by ordering them by `login_time`.

2. Modify the query from the previous step by adding the login time to the `ORDER BY` clause. You must replace `X` with the appropriate column name:
![Pasted image 20230704192516](https://github.com/cosbey/SQL/assets/32424700/aa117536-9e74-4d82-9100-cd702c79132e)


**What are the username and login time of the first record returned by the above query?**

- gesparza at 00:40:00
- *bsand at 00:19:11*
- pwashing at 00:36:12
- wjaffrey at 00:15:55



## Lessons Learned:


In this lab, we have used basic SQL queries to:

- select specific columns from a table,
- select all columns from a table by using an asterisk (`*`), and
- sort query results using the `ORDER BY` keyword.

These basic queries form the foundation for running more advanced queries and applying filters later.

**Additional Resources:** 
- https://www.microsoft.com/en-us/sql-server
- https://www.virtualbox.org/
