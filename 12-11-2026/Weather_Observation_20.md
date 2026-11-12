## Weather Observation 20

Link: [Hackerrank](https://www.hackerrank.com/challenges/weather-observation-station-20/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Querying the median of the Northern Latitudes (LAT_N) from the Station table, rounded to 4 decimal places.

Order and Rank: Sort all Northern Latitudes in ascending order and assign row numbers to identify the middle values.

Find the Middle:

If the total row count is odd, pick the single middle value.

If the total row count is even, average the two middle values.

Format: Round the resulting median to 4 decimal places using ROUND().


## Solution


```SQL
SELECT ROUND(LAT_N, 4) 
FROM (
    SELECT LAT_N, ROW_NUMBER() OVER (ORDER BY LAT_N) as row_num,
           COUNT(*) OVER () as total_count
    FROM STATION
) as ranked
WHERE row_num = CEIL(total_count / 2.0) 
   OR row_num = FLOOR(total_count / 2.0) + 1;
```
