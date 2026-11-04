## Binary Tree Nodes

Link: [Hackerrank](https://www.hackerrank.com/challenges/binary-search-tree-1/problem?isFullScreen=true)


Difficulty : Medium
DB Engine : MySQL

*********

## Intuition

Classifies each node by checking its position in the tree: no parent means Root, no children means Leaf, and everything else is Inner.

## Solution

```SQL
SELECT N, 
       CASE 
           WHEN P IS NULL THEN 'Root'
           WHEN N NOT IN (SELECT DISTINCT P FROM BST WHERE P IS NOT NULL) THEN 'Leaf'
           ELSE 'Inner'
       END
FROM BST
ORDER BY N; 
```
