# Question 1:
*Find all time entries.*

SELECT *
FROM time_entries

500 rows returned in 8ms from: SELECT *
FROM time_entries

# Question 2:
*Find the developer who joined most recently.*

SELECT  joined_on, name, id
FROM developers 
ORDER BY ID DESC
LIMIT 1

# Question 3:
*Find the number of projects for each client.*

SELECT  client_id, COUNT (projects.client_id)
FROM projects INNER JOIN clients
WHERE projects.client_id = clients.id
GROUP BY client_id

# Question 4:
*Find all time entries, and show each one's client name next to it.*

SELECT  project_id, name
FROM time_entries INNER JOIN clients
LIMIT 500

# Question 5:
*Find all developers in the "Ohio sheep" group.*

SELECT developer_id
FROM developers INNER JOIN group_assignments
WHERE group_id = 3
LIMIT 3

# Question 6:
*Find the total number of hours worked for each client.*

SELECT  client_id, clients.name, SUM(duration)
FROM clients LEFT JOIN projects ON projects.client_id = clients.id LEFT JOIN time_entries ON time_entries.project_id = projects.id
GROUP BY clients.id

# Question 7:
*Find the client for whom Mrs. Lupe Schowalter (the developer) has worked the greatest number of hours.*



# Question 8:
*List all client names with their project names (multiple rows for one client is fine). Make sure that clients still show up even if they have no projects.*

SELECT clients.name, projects.name
FROM clients LEFT JOIN projects
GROUP BY clients.name, projects.name


# Question 9:
*Find all developers who have written no comments*

