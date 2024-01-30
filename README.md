# Maze Solver

This repo based on the case study in chapter 4 of "Java Software Structures 4th Edition".

Please study the source code, manually trace it, and experiment with the running program as follows to understand how the solver algorithm works.
```shell
$ javac *.java
$ java MazeTester 
Enter the name of the file containing the maze: testfile.txt

10000
11000
01000
01110
00011

The maze was successfully traversed!

20000
22000
02000
02220
00022
```

## Task 1
If you enter non-existent file name, the program will crash. Please modify the program so that it repromt 
the user for a file name if the previously entered one does not exist.

## Task 2
The maze solver algorithm uses a stack to keep track of the options (positions in the maze it needs to
explore). The result of exploring a simple maze can look as follows:
```
2>2>2 0
  v
0 2 0 0
  v
2<2>2 0
v   v
2 0 2>2
```
The arrows show the directions the algorithm took before a solution is found. Each position can have multiple 
directions (branches) to go, resulting in a tree-like exploration path. Some paths lead to dead-ends, i.e. 
`(0, 2)` and `(3,0)`. 
Each position can lead to multiple positions, but each position comes from exactly one position. One way to 
mark the path is for each position to keep a reference/pointer to its "parent" position. Then, we can simply
trace from the "goal" back to the "start" using the "parent" reference and mark the positions along the way
as a possible path.

Please create a "result.txt" with the output of your test cases.