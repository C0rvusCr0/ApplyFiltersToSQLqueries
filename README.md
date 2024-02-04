# Apply filters to SQL queries

<h2>Project description</h2>

I am responsible for enhancing the system's security in my organization. My tasks include ensuring system safety, investigating security concerns, and updating employee computers when necessary. The steps below demonstrate how I utilized SQL filters to perform security-related tasks.


<h3>Retrieve after hours failed login attempts.</h3>


After business hours (post 18:00), a potential security incident transpired, requiring investigation of failed login attempts. The subsequent code showcases my creation of a SQL query to filter and identify failed login attempts that took place after business hours.


![image4](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/e5343e44-8e8f-4921-ae02-09cc02bbb7d1)


The screenshot presents a query and its output. The query filters for failed login attempts that happened after 18:00. Initially, all data from the log_in_attempts table is selected. Then, a WHERE clause with an AND operator is employed to display only login attempts occurring after 18:00 that were unsuccessful. The first condition, login_time > '18:00', filters for login attempts after 18:00. The second condition, success = FALSE, filters for failed login attempts.


<h3>Retrieve login attempts on specific dates</h3>


An alarming incident took place on May 9th, 2022. We need to investigate any login activity that occurred on that day or the day before.

I have written the following code to create a SQL query that filters for login attempts specifically on those dates.


![image1](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/173ee3cc-9b34-4b4d-abf4-bf2fe3e2976a)


The screenshot includes a query and its output. The query retrieves login attempts that took place on either 2022-05-09 or 2022-05-08. Initially, all data from the log_in_attempts table is selected. Then, a WHERE clause with an OR operator is used to filter the results, showing only login attempts on either of the specified dates. The first condition filters for logins on 2022-05-09 using login_date = '2022-05-09'. The second condition filters for logins on 2022-05-08 using login_date = '2022-05-08'.


<h3>Retrieve login attempts outside of Mexico</h3>


Upon examining the organization's login attempt data, I have identified a potential issue with login activities that took place outside of Mexico. It is crucial to thoroughly investigate these login attempts.

To address this concern, I have developed a SQL query that filters for login attempts specifically outside of Mexico. The following code showcases my approach.


![image3](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/84e4f10f-d6cd-43ab-876b-2425aa6c8208)


The screenshot displays a query and its output. The query retrieves login attempts from countries excluding Mexico. Initially, all data from the log_in_attempts table is selected. Then, a WHERE clause with the NOT operator is used to filter out Mexico. The pattern 'MEX%' is used with the LIKE operator to match variations of Mexico's representation, including MEX and MEXICO. The '%' represents any unspecified characters when utilized with LIKE.


<h3>Retrieve employees in Marketing</h3>


My team has a task to update the computers of specific employees in the Marketing department. In order to proceed with the updates, I need to gather information about which employee machines require the updates.


![image5](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/f2996bfd-7973-4103-ae54-346c493f1d5f)



The screenshot consists of a query and its output. The query retrieves employees in the Marketing department located in the East building. Firstly, all data from the employees table is selected. Then, a WHERE clause with an AND operator is used to filter for employees in both the Marketing department and the East building. The pattern 'East%' is employed with the LIKE operator to match the office column data, representing the East building with its specific office number. The first condition filters for employees in the Marketing department, while the second condition filters for employees in the East building.


<h3>Retrieve employees in Finance or Sales</h3>


Additionally, the machines of employees in the Finance and Sales departments also require updates. Since these updates involve a different security patch, I need to specifically gather information on employees solely from these two departments.

![image2](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/fd8728aa-8977-44ff-8e50-fd1758bbba9e)

![image6](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/7f646166-26a6-419e-a894-d2f35e7c47fe)


The screenshot contains two sections: the initial query and a segment of the resulting output. This query retrieves employees who belong to either the Finance or Sales departments. To begin, I selected all the data from the employees table. Then, I employed a WHERE clause with the OR operator to filter for employees in the Finance and Sales departments. I opted for the OR operator instead of AND because I wanted to include all employees who are in either department. The first condition, department = 'Finance', filters for employees from the Finance department. The second condition, department = 'Sales', filters for employees from the Sales department.


<h3>Retrieve all employees not in IT</h3>


To finalize our security updates, my team needs to apply one more update to employees outside of the Information Technology department. Before proceeding with the update, I must collect information on these particular employees.


![image7](https://github.com/C0rvusCr0/ApplyFiltersToSQLqueries/assets/122651345/383a0912-420d-4021-b2a0-ecdf229f3172)


The screenshot consists of two parts: the initial inquiry and a segment of the resulting output. The query retrieves employees who do not belong to the Information Technology department. Initially, I extracted all data from the employees table. Subsequently, I employed a WHERE clause with the negation (NOT) operator to filter out employees affiliated with said department.


<h3>Summary</h3>


To obtain specific information about login attempts and employee machines, I applied filters to SQL queries. I utilized two different tables, namely log_in_attempts and employees. For each task, I employed operators such as AND, OR, and NOT to filter the data based on the desired criteria. Additionally, I utilized the LIKE operator and the '%' wildcard to filter for specific patterns in the data.
