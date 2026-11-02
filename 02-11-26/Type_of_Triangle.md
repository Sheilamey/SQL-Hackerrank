## Type of Triangle

Link: [Hackerrank](https://www.hackerrank.com/challenges/what-type-of-triangle/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Use a CASE statement to evaluate the three side lengths (A, B, and C) from the TRIANGLES table.

Filter Conditions (WHEN):

Check if it's not a valid triangle first (A + B <= C etc.).

Check if all sides are equal (Equilateral).

Check if any two sides are equal (Isosceles).

Fallback (ELSE): Classify the remaining valid combinations as Scalene

## Solution

```SQL
SELECT 
    CASE 
        WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
        WHEN A = B AND B = C THEN 'Equilateral'
        WHEN A = B OR B = C OR A = C THEN 'Isosceles'
        ELSE 'Scalene'
    END
FROM TRIANGLES; 
```
