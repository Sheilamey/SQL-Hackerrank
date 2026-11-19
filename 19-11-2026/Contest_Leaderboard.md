## Contest Leaderboard

Link: [Hackerrank]https://https://www.hackerrank.com/challenges/contest-leaderboard/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Calculate each hacker's total score—defined as the sum of their maximum score per challenge—while excluding zero-score totals and sorting appropriately.

Find Best Score per Challenge: A hacker might submit multiple times for the same challenge. First, group submissions by both hacker_id and challenge_id and take MAX(score) so each challenge is only counted once at its highest achieved score.

Sum Across Challenges: Join those challenge-level maximums with Hackers and sum them up per hacker (SUM(max_score)) to get each hacker's total contest score.

Filter Out Zeros: Exclude hackers whose total score is 0 (HAVING total_score > 0).

Sort: Order by total_score descending (DESC), then by hacker_id ascending (ASC) for ties.

## Solution

```SQL
WITH MaxChallengeScores AS (
    SELECT 
        hacker_id, 
        challenge_id, 
        MAX(score) AS max_score
    FROM Submissions
    GROUP BY hacker_id, challenge_id
)
SELECT 
    h.hacker_id, 
    h.name, 
    SUM(mcs.max_score) AS total_score
FROM Hackers h
JOIN MaxChallengeScores mcs ON h.hacker_id = mcs.hacker_id
GROUP BY h.hacker_id, h.name
HAVING total_score > 0
ORDER BY total_score DESC, h.hacker_id ASC;
```