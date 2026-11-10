## Weather Observation 15

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-15/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) that is less than 137.2345, rounded to 4 decimal places.

Filter: Keep only the rows where Northern Latitudes (LAT_N) are less than 137.2345.

Find the Maximum: Sort the filtered latitudes in descending order (ORDER BY LAT_N DESC) and pick the top row (LIMIT 1) to isolate the largest one.

Select and Format: Extract the corresponding Western Longitude (LONG_W) and round it to 4 decimal places using ROUND().

## Solution

```SQL
SELECT ROUND(LONG_W, 4)
FROM STATION
WHERE LAT_N < 137.2345
ORDER BY LAT_N DESC
LIMIT 1;
```
