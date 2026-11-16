## The Report

Link: [Hackerrank]https://www.hackerrank.com/challenges/the-report/problem?isFullScreen=true)


Difficulty : Easy
DB Engine : MySQL

*********

## Intuition

Querying the The Report challenge by matching student marks to grade ranges, conditionally masking names as "NULL" for grades lower than 8, and sorting dynamically based on the grade level.

Join Ranges: Instead of joining Students and Grades on an exact equality, connect them using a range comparison where the student's Marks fall inclusively between Min_Mark and Max_Mark.

Conditional Masking: Use a CASE statement to check if the Grade is less than 8; if so, display "NULL" instead of the student's Name.

Conditional Sorting:For higher grades ($\ge 8$), order descending by grade, then alphabetically by name (NAME).For lower grades, order descending by grade, then ascending by marks (MARKS).


## Solution

```SQL
SELECT 
    CASE 
        WHEN Grades.Grade >= 8 THEN Students.Name 
        ELSE NULL 
    END, 
    Grades.Grade, 
    Students.Marks
FROM Students
JOIN Grades ON Students.Marks BETWEEN Grades.Min_Mark AND Grades.Max_Mark
ORDER BY 
    Grades.Grade DESC, 
    CASE WHEN Grades.Grade >= 8 THEN Students.Name END ASC, 
    Students.Marks ASC;
```
