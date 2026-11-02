## Type of Triangle

Link: [Hackerrank](https://www.hackerrank.com/challenges/what-type-of-triangle/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

We need to inspect the three side lengths (A, B, and C) of each record in the TRIANGLES table, determine what kind of geometric shape (if any) they form, and return the corresponding classification.

Evaluate Conditions Sequentially (CASE statement):

Rule 1: Validity Check (Not A Triangle) — Before testing what kind of triangle it is, we must first verify if the side lengths can actually form a triangle at all. According to the triangle inequality theorem, the sum of any two sides must be strictly greater than the third side ($A + B > C$, $A + C > B$, and $B + C > A$). Therefore, if the inverse is true ($A + B \le C$ or $A + C \le B$ or $B + C \le A$), it fails validation and must return Not A Triangle.

Rule 2: Equilateral Check (Equilateral) — If it passes the validity check, we check if all three sides are equal to one another ($A = B$ and $B = C$). If they are, it is classified as an equilateral triangle.

Rule 3: Isosceles Check (Isosceles) — Next, we check if at least two sides are equal ($A = B$ or $B = C$ or $A = C$). If this condition is met, it is an isosceles triangle. (Note: Placing this after the Equilateral check is crucial because an equilateral triangle also satisfies the isosceles condition; checking equilateral first ensures it gets the correct label).

Rule 4: Scalene Fallback (Scalene) — If none of the previous conditions are met (meaning it is a valid triangle, but no sides are equal), the remaining default case handles it as a scalene triangle.

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
