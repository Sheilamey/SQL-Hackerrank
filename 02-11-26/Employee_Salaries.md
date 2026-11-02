## Employee Salaries

Link: [Hackerrank](https://www.hackerrank.com/challenges/salary-of-employees/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Retrieve the name column from the Employee table.

Filter (WHERE): Keep employees earning over $2,000 (salary > 2000) and employed for fewer than 10 months (months < 10).

Sort (ORDER BY): Order the results by employee_id in ascending order.

## Solution

```SQL
SELECT name 
FROM Employee
WHERE salary > 2000 AND months < 10
ORDER BY employee_id;
```
