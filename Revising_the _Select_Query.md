## Revising the Select Query

Link: [Hackerrank](https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : DB2

*********

## Intuition

Querying all columns for all American cities with population larger than 100000



## Solution

```SQL
SELECT * FROM CITY WHERE COUNTRYCODE = 'USA' AND POPULATION > 100000;
```
