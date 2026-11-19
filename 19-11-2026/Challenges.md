## Challenges

Link: [Hackerrank]https://https://www.hackerrank.com/challenges/challenges/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

List each student's hacker_id, name, and total created challenges, while filtering out duplicate counts that fall below the maximum challenge count.

Join and Count: Join Hackers and Challenges on hacker_id, group by student (hacker_id and name), and count how many challenges each created (COUNT(c.challenge_id)).

Filter Duplicate Counts: Keep a student's row if their challenge count equals the maximum challenge count overall or if their count is unique among all students (COUNT(*) = 1 for that count value).

Sort: Order by total challenges descending, then by hacker_id ascending.

## Solution

```SQL
WITH ChallengeCounts AS (
    SELECT 
        h.hacker_id, 
        h.name, 
        COUNT(c.challenge_id) AS challenges_created
    FROM Hackers h
    JOIN Challenges c ON h.hacker_id = c.hacker_id
    GROUP BY h.hacker_id, h.name
)
SELECT 
    hacker_id, 
    name, 
    challenges_created
FROM ChallengeCounts
WHERE challenges_created = (
    SELECT MAX(challenges_created) 
    FROM ChallengeCounts
)
OR challenges_created IN (
    SELECT challenges_created
    FROM ChallengeCounts
    GROUP BY challenges_created
    HAVING COUNT(*) = 1
)
ORDER BY challenges_created DESC, hacker_id ASC;
```