## Higher Than 75 Marks

Link: [Hackerrank](https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying names of students who scored higher than 75 marks, order the output by the last three characters of each name. If student have the same last three characters secondary sort ascending ID



## Solution

```SQL
SELECT Name
 FROM STUDENTS 
 WHERE Marks > 75
 ORDER BY RIGHT (Name, 3), ID;
```
