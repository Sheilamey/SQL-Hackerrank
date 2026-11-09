## Japan Population

Link: [Hackerrank](https://www.hackerrank.com/challenges/japan-population/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the total population for Japan. 

Filter: Country code for Japan

Aggregate: Subtract the two.


## Solution

```SQL
SELECT SUM(POPULATION)
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
