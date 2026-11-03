## Occupation

Link: [Hackerrank](https://www.hackerrank.com/challenges/occupations/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

We assign an alphabetical row number to names separately within each occupation. This aligns rows by position instead of by name.

Pivot (CASE WHEN): We use conditional logic to split the single column of names into four distinct occupation columns side-by-side.

Aggregate (MAX + GROUP BY): We group everything by that row number. Since each row only contains one name per occupation and NULLs elsewhere, MAX() cleanly grabs the name while ignoring the NULLs.


## Solution

```SQL
SELECT 
    MAX(CASE WHEN Occupation = 'Doctor' THEN Name END) AS Doctor,
    MAX(CASE WHEN Occupation = 'Professor' THEN Name END) AS Professor,
    MAX(CASE WHEN Occupation = 'Singer' THEN Name END) AS Singer,
    MAX(CASE WHEN Occupation = 'Actor' THEN Name END) AS Actor
FROM (
    SELECT Name, Occupation,
           ROW_NUMBER() OVER (PARTITION BY Occupation ORDER BY Name) AS row_num
    FROM OCCUPATIONS
) AS ranked_occupations
GROUP BY row_num; 
```
