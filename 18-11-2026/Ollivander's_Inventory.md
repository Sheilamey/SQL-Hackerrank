## Ollivander's Inventory

Link: [Hackerrank]https://www.hackerrank.com/challenges/harry-potter-and-wands/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Finding non-evil wands (is_evil = 0) that require the minimum number of gold galleons for each unique combination of power and age.

Join Tables: Connect the Wands and Wands_Property tables using their matching code column.

Filter Non-Evil: Keep only wands where is_evil = 0.

Find Minimum Cost: Use a subquery to find the minimum coins_needed for every combination of wand power and age property.

Sort: Order the final output in descending order of power, and then by descending order of age for wands with identical power.

## Solution

```SQL
SELECT w.id, wp.age, w.coins_needed, w.power
FROM Wands w
JOIN Wands_Property wp ON w.code = wp.code
WHERE wp.is_evil = 0 
  AND w.coins_needed = (
      SELECT MIN(w1.coins_needed)
      FROM Wands w1
      JOIN Wands_Property wp1 ON w1.code = wp1.code
      WHERE wp1.age = wp.age 
        AND w1.power = w.power 
        AND wp1.is_evil = 0
  )
ORDER BY w.power DESC, wp.age DESC;
```
