## Top Competitors

Link: [Hackerrank]https://www.hackerrank.com/challenges/full-score/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Identify hackers who achieved full scores on more than one challenge, filtering by maximum difficulty score, and sorting results.

Join Tables: Connect Submissions, Challenges, Difficulty, and Hackers using their corresponding IDs to link each submission's score with the maximum possible score for that challenge.

Filter Full Scores: Keep only the records where a hacker's submission score (Submissions.score) matches the maximum score for that difficulty level (Difficulty.score).

Group and Count: Group the results by hacker (hacker_id and name) and count how many unique challenges they aced (COUNT). Keep only those with a count greater than 1 (HAVING COUNT(*)).

Sort: Order the output descending by the total number of full-score challenges, then ascending by hacker_id.

## Solution

```SQL
SELECT h.hacker_id, h.name
FROM Submissions s
JOIN Challenges c ON s.challenge_id = c.challenge_id
JOIN Difficulty d ON c.difficulty_level = d.difficulty_level
JOIN Hackers h ON s.hacker_id = h.hacker_id
WHERE s.score = d.score
GROUP BY h.hacker_id, h.name
HAVING COUNT(s.challenge_id) > 1
ORDER BY COUNT(s.challenge_id) DESC, h.hacker_id ASC;
```
