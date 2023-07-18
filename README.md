1. Getting started


## Queries and filters
### SELECT

```
SELECT * FROM jobs;
```


### WHERE
```
SELECT * from jobs
WHERE job_id = 1;
```

```SELECT * from jobs
WHERE min_salary > 4000
AND min_salary < 5000;
```

### ORDER BY
```
SELECT * from jobs
WHERE min_salary > 1000
AND min_salary < 8000
ORDER BY min_salary;
```

```
SELECT * from jobs
WHERE min_salary > 1000
AND min_salary < 8000
ORDER BY min_salary DESC;
```

### LIMIT
```
SELECT * from jobs
WHERE min_salary > 1000
AND min_salary < 8000
ORDER BY min_salary DESC
LIMIT 5;
```

## Aggregations

### AVG
```
SELECT AVG(min_salary) AS avg_min_salary,
AVG(max_salary) AS avg_max_salary
FROM jobs;
```


### COUNT
```
SELECT COUNT(*) AS total_jobs
FROM jobs;
```

### MAX
```
SELECT MAX(min_salary) AS max_min_salary,
MAX(max_salary) AS max_max_salary
FROM jobs;
```

### MIN
```
SELECT MIN(min_salary) AS min_min_salary,
MIN(max_salary) AS min_max_salary
FROM jobs;
```


## Grouping
### GROUP BY
```
SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id;
```

### HAVING
```
SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 5;
```

## Joins
### INNER JOIN
An inner join will return only the rows that match in both tables.
```
SELECT * FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

### LEFT JOIN
A left join will return all the rows from the left table, and the matched rows from the right table.

In the query below, all the employees will be returned, even if they don't have a department because employees is the left table.
```
SELECT * FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

### RIGHT JOIN
A right join will return all the rows from the right table, and the matched rows from the left table.

In the query below, all the departments will be returned, even if they don't have an employee because departments is the right table.
```
SELECT * FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```
