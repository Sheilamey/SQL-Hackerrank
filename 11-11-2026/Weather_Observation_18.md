## Weather Observation 17

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-17/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the Western Longitude (LONG_W) for the smallest Northern Latitude (LAT_N) that is greater than 38.7780, rounded to 4 decimal places.

Filter: Keep only the rows where Northern Latitudes (LAT_N) are greater than 38.7780.

Find the Smallest: Sort the filtered latitudes in ascending order and pick the top row (LIMIT 1) to isolate the smallest one.

Select and Format: Extract the corresponding Western Longitude (LONG_W) and round it to 4 decimal places using ROUND().

## Solution

```SQL
SELECT ROUND((LONG_W), 4)
FROM STATION
WHERE LAT_N >38.7780
ORDER BY LAT_N 
LIMIT 1; 
```
