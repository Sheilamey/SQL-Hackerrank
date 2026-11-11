## Weather Observation 16

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-16/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the smallest Northern Latitude (LAT_N) that is greater than 38.7780, rounded to 4 decimal places.

Filter: Keep only the rows where Northern Latitudes (LAT_N) are greater than 38.7780.

Find the Minimum: Use the MIN() aggregate function to find the smallest value among those filtered latitudes.

Format: Round the final minimum value to 4 decimal places using ROUND().

## Solution

```SQL
SELECT ROUND(MIN(LAT_N), 4)
FROM STATION
WHERE LAT_N > 38.7780;
```
