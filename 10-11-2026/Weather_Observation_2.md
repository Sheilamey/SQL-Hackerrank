## Weather Observation 2

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-2/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the total sum of Northern Latitudes (LAT_N) and Western Longitudes (LONG_W) truncated to 2 decimal places.

Aggregate: Add up all the values for latitude and longitude using SUM().

Format: Cut off extra decimals to a scale of 2 decimal places using ROUND().

## Solution

```SQL
SELECT ROUND(SUM(LAT_N), 2),
       ROUND(SUM(LONG_W), 2)
FROM STATION;
```
