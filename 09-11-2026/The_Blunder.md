
## The Blunder

Link: [Hackerrank](https://www.hackerrank.com/challenges/the-blunder/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the error in salary average rounded to the nearest integer. 

Simulate the Error: Convert each numeric salary into a string, strip out all instances of the character '0', and convert it back into a number.

Compare Averages: Calculate the difference between the actual average salary and the miscalculated average salary.

Round Up: (Ceil) Round the final absolute difference up to the next upper integer using the ceiling function.

## Solution

```SQL
SELECT CEIL(AVG(Salary) - AVG(CAST(REPLACE(CAST(Salary AS CHAR), '0', '') AS UNSIGNED)))
FROM EMPLOYEES;
```


