## Weather Observation 14

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-14/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the greatest value in Northern Latitudes with less than 137.2345 give the answer in 4 decimal places from station. 

Filter: Keep only latitudes below the threshold (< 137.2345).

Aggregate: Pick the highest value (MAX).

Format: Cut off extra decimals (TRUNCATE).


## Solution

```SQL
SELECT TRUNCATE (MAX(LAT_N), 4)
FROM STATION
WHERE LAT_N < 137.2345;
```
