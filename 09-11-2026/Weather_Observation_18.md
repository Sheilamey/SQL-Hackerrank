## Weather Observation 18

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-18/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Querying the Manhattan Distance between points $P_1(a, b)$ and $P_2(c, d)$ rounded to 4 decimal places

Find Coordinates: Identify the minimum and maximum values for Northern Latitudes and Western Longitudes to establish points $P_1$ and $P_2$.

Calculate Distance: Compute the Manhattan Distance.

Format: (ROUND)Round the final result to 4 decimal places.

## Solution

```SQL
SELECT ROUND(ABS(MIN(LAT_N) - MAX(LAT_N)) + ABS(MIN(LONG_W) - MAX(LONG_W)), 4)
FROM STATION;
```
