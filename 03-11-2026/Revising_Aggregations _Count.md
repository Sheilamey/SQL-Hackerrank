## Revising Aggregations - Count Function

Link: [Hackerrank](https://www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Number of cities with a popoluation larger than 100,000


## Solution

```SQL
SELECT COUNT(*)
FROM CITY
WHERE POPULATION > 100000; 
```
