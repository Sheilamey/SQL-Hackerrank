## Population Density Difference

Link: [Hackerrank](https://www.hackerrank.com/challenges/population-density-difference/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the difference between the maximum and minimum population. 

Aggregate: Subtract the two.


## Solution

```SQL
SELECT MAX(POPULATION) - MIN(POPULATION)
FROM CITY;
```
