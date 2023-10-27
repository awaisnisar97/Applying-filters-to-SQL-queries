<h1>Applying filters to SQL queries</h1>



<h2>Description</h2>
Project consists of examining employee login data and filtering via location, time and date to identify any suspicious login attempts.
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 

<h2>Program walk-through:</h2>

<p align="center">

Retrieve after hours failed login attempts:

I recently discovered a potential security incident that occurred after business hours. To investigate this, I queried the log_in_attempts table and reviewed after hours login activity. <br/>

<img src="https://imgur.com/si1wk2J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The first part of the screenshot is my query and the second is the output. 
This identified number of after hour log in attempts and how many have failed. First, I started by selecting all data from the log_in_attempts table using the FROM clause. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts.

Retrieve login attempts on specific dates:

A suspicious event occurred on 2022-05-09, any activity that happened on the day or day before needs to be investigated. 
The following code demonstrates the SQL queries I used to investigate this. <br/>

<img src="https://imgur.com/InnrOT1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The query returned all log in attempts on 2022-05-08 or 2022-05-09. I selected all data from the log_in_attempts and then used the WHERE and OR  operator to filter results accordingly.

Retrieve login attempts outside of Mexico:

After investigating the organisation’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico.

<img src="https://imgur.com/4DJjw8W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The first line is my input and the table below is the output. I selected all data from the log_in_attempts table and used the WHERE and NOT operators to include any login attempts from countries outside of Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE


Retrieve employees in Marketing:

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.


<img src="https://imgur.com/kPcqDsW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The first line is the input and the second demonstrated in a table is the output of my SQL query. 
I selected all data from the employees table and then filtered using the WHERE and AND operator to filter data from the marketing department and offices in the east building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building. 

Retrieve employees in Finance or Sales:

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<img src="https://imgur.com/VTnMiMF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department

Retrieve all employees not in IT:

My team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. 
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<img src="https://imgur.com/6ESiVOt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The first part of the screenshot is my query and the second part is the output. I first selected all data from the employees table and then used the WHERE and NOT operator to filter out employees that are not from the IT department. 

Summary:

I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
