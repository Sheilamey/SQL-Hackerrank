## Weather Observation 12
Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-12/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying distinct city names that do not start with vowels and do not ed with vowels



## Solution

```SQL
SELECT DISTINCT CITY 
FROM STATION 
WHERE CITY NOT REGEXP '^[aeiouAEIOU]' 
  AND CITY NOT REGEXP '[aeiouAEIOU]$';
```
