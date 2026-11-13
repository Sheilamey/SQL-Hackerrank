## Weather Observation 19

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-19/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Querying the Euclidean Distance between points $P_1(a, c)$ and $P_2(b, d)$ rounded to 4 decimal places.

Find Coordinates: Identify the minimum and maximum values for Northern Latitudes (LAT_N) and Western Longitudes (LONG_W) to represent the points $P_1(min(LAT\_N), min(LONG\_W))$ and $P_2(max(LAT\_N), max(LONG\_W))$.

Calculate Distance: Compute the Euclidean Distance formula: $\sqrt{(a - b)^2 + (c - d)^2}$, which translates to $\sqrt{(min(LAT\_N) - max(LAT\_N))^2 + (min(LONG\_W) - max(LONG\_W))^2}$.

Format: Round the final square root result to 4 decimal places using ROUND().


## Solution

```SQL
SELECT ROUND(
    SQRT(
        POW(MIN(LAT_N) - MAX(LAT_N), 2) + 
        POW(MIN(LONG_W) - MAX(LONG_W), 2)
    ), 4
)
FROM STATION;
```
