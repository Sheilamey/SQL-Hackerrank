## Revising Aggregations - SUM Function

Link: [Hackerrank](https://www.hackerrank.com/challenges/revising-aggregations-sum/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Add up the total population for California


## Solution

```SQL
SELECT SUM(POPULATION)
FROM CITY
WHERE DISTRICT = 'California';
```
