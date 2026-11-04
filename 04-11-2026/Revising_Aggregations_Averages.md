## Revising Aggregations - Averages

Link: [Hackerrank](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Average population of all cities in California


## Solution

```SQL
SELECT AVG (POPULATION)
FROM CITY
WHERE DISTRICT = 'California'; 
```
