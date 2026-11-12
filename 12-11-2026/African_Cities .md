## African Cities

Link: [Hackerrank](https://www.hackerrank.com/challenges/african-cities/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the names of all cities where the continent is 'Africa' using a join between the CITY and COUNTRY tables.

Join Tables: Connect the CITY table and COUNTRY table together using their matching key columns (CITY.CountryCode and COUNTRY.Code).

Filter: Apply a condition where the continent is explicitly 'Africa' (COUNTRY.Continent = 'Africa').

Select: Retrieve the city names (CITY.NAME

## Solution

```SQL
SELECT CITY.NAME
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.Continent = 'Africa';
```
