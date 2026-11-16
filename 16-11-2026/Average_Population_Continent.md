## Average Population of Each Continent

Link: [Hackerrank]https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Join Tables: Connect the CITY and COUNTRY tables using their matching keys (CITY.CountryCode and COUNTRY.Code).

Group and Average: Group the results by each continent (GROUP BY COUNTRY.Continent) and compute the average city population for each using AVG(CITY.Population).

Select and Format: Select the continent name alongside the average population, rounded down to the nearest integer using FLOOR().


## Solution

```SQL
SELECT COUNTRY.Continent, FLOOR(AVG(CITY.Population))
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
GROUP BY COUNTRY.Continent;
```
