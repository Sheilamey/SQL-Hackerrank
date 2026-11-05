## Weather Observation 13

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-13/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying sum of Northern Latitudes greater than 38.7880 and less than 17.2345 truncate to 4 decimal places

Filter: Keep latitudes between 38.7880 and 137.2345.

Aggregate: Add them up (SUM).

Format: Cut extra decimals (TRUNCATE).

## Solution

```SQL
SELECT TRUNCATE (SUM(LAT_N), 4)
FROM STATION 
WHERE LAT_N >38.7880 AND LAT_N <137.2345;
```
