## Top Earners

Link: [Hackerrank](https://www.hackerrank.com/challenges/earnings-of-employees/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the maximum total earnings (salary multiply by months ) and the count of employees who achieved that maximum value, ordered from highest to lowest.

Calculate Earnings: Multiply salary by months for each employee to find their total earnings.

Group and Count: Group the rows by total earnings and count how many employees share each earning amount (COUNT(*)).

Find the Maximum: Sort the grouped earnings in descending order (ORDER BY, DESC) and pick the top result (LIMIT 1) to get the highest total earnings and its corresponding employee count.

## Solution

```SQL
SELECT (salary * months) AS earnings, COUNT(*)
FROM Employee
GROUP BY earnings
ORDER BY earnings DESC
LIMIT 1;
```
