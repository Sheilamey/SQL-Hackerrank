## Average Population

Link: [Hackerrank](https://www.hackerrank.com/challenges/average-population/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Average population for all cities rounded down to the nearest integer. We'll use FLOOR


## Solution

```SQL
SELECT FLOOR(AVG (POPULATION))
FROM CITY;
```
