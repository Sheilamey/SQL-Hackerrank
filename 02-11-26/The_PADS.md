## The PADS

Link: [Hackerrank](https://www.hackerrank.com/challenges/the-pads/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Part One: Select names and transform occupations to their first letter using SUBSTR(), combine them using CONCAT(), and sort alphabetically by name.

Part Two: Group rows by occupation, count occurrences, convert profession names to lowercase using LOWER(), format into the requested sentence structure, and sort by count followed by the profession name.

Combine: Use UNION to merge both result sets into a single sequential output.


## Solution

```SQL
SELECT CONCAT(Name, '(', SUBSTR(Occupation, 1, 1), ')')
FROM OCCUPATIONS
ORDER BY Name;

SELECT CONCAT('There are a total of ', COUNT(Occupation), ' ', LOWER(Occupation), 's.')
FROM OCCUPATIONS
GROUP BY Occupation
ORDER BY COUNT(Occupation), Occupation; 
```
