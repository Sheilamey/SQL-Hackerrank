## Population Census

Link: [Hackerrank]https://www.hackerrank.com/challenges/asian-population/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the total sum of populations for all cities where the continent is 'Asia' using a join between the CITY and COUNTRY tables.

Join Tables: Connect the CITY table and COUNTRY table together using their matching key columns (CITY.CountryCode and COUNTRY.Code).

Filter: Apply a condition where the continent is explicitly 'Asia' (COUNTRY.Continent = 'Asia').

Aggregate: Add up the populations of all matching cities using the SUM() function (SUM(CITY.Population)).


## Solution

```SQL
SELECT SUM(CITY.Population)
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.Continent = 'Asia';
```
