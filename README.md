# Sudoku-Puzzle-Solving-Using-Constraint-Satisfication-Problem-Artificial-Intelligence-
The Sudoku puzzle is a classic constraint satisfaction problem (CSP). Implement the Arc-Consistency 3 (AC-3) Algorithm and the Backtracking Algorithm to solve the Sudoku puzzle in Python, and compare their time complexities. The Sudoku puzzle board should feature a graphical user interface (GUI) using Tkinter..
function AC-3(csp) returns false if an inconsistency is found and true otherwise
 inputs: csp, a binary CSP with components (X, D, C)
 local variables: queue, a queue of arcs, initially all the arcs in csp
 while queue is not empty do
   (X i , X j ) ← POP(queue)
   if REVISE(csp, X i , X j ) then
     if size of D i  = 0 then return false
     for each X k  in X i .NEIGHBORS − {X j } do
      add(X k , X i ) to queue
      
 return true
function REVISE(csp, X i , X j ) returns true iff we revise the domain of X i
 revised ← false
 for each x in D i  do
   if no value y in D j  allows (x, y) to satisfy the constraint between X i  and X j  then
    delete x from D i
    revised ← true
 return revised
function BACKTRACKING-SEARCH(csp) returns a solution, or failure
 return BACKTRACK({}, csp)
function BACKTRACK(assignment, csp) returns a solution, or failure
 if assignment is complete then return assignment
 var ← SELECT-UNASSIGNED-VARIABLE(csp)
 for each value in ORDER-DOMAIN-VALUES(var, assignment, csp) do
   if value is consistent with assignment then
     add {var = value} to assignment
     inferences ← INFERENCE(csp, var, value)
     if inferences ≠ failure then
      add inferences to assignment
      result ← BACKTRACK(assignment, csp)
      if result ≠ failure then
       return result
     remove {var = value} and inferences from assignment
 return failure


Implementation Guidelines:
1. Stuart Russell and Peter Norvig. Artificial Intelligence: A Modern Approach, 4 th edition. Pearson, 2022.
2. Code for the book &quot;Artificial Intelligence: A Modern Approach&quot;
https://github.com/aimacode/aima-python (accessed April 15, 2024).
3. Wei-Meng Lee, &quot;Programming Sudoku&quot; www.apress.com/9781590596623  (accessed April 15, 2024).
4. Graphical User Interfaces, http://newcoder.io/gui/ (accessed April 15, 2024).

![image](https://github.com/rohit546/Sudoku-Puzzle-Solving-Using-Constraint-Satisfication-Problem-Artificial-Intelligence-/assets/100420859/710a3081-c6ae-44dc-ac6e-04c05d7853b9)

![image](https://github.com/rohit546/Sudoku-Puzzle-Solving-Using-Constraint-Satisfication-Problem-Artificial-Intelligence-/assets/100420859/a134ff93-0a61-4c38-b527-dc4068da0e4c)

![image](https://github.com/rohit546/Sudoku-Puzzle-Solving-Using-Constraint-Satisfication-Problem-Artificial-Intelligence-/assets/100420859/80289046-f0a2-4726-96d3-864184b3b43f)

![image](https://github.com/rohit546/Sudoku-Puzzle-Solving-Using-Constraint-Satisfication-Problem-Artificial-Intelligence-/assets/100420859/38d0d351-07d6-4b7e-a128-9ee52b5770f9)


2. The Sudoku Board should offer the option to select either the Arc-3 algorithm or
backtracking to solve the puzzle.
3. The Sudoku Board should allow users to select a difficulty level—easy, medium, or
hard—and choose from one of four available puzzles, provide in dataset.
4. The time taken to solve the puzzle, also known as time complexity, should be displayed.
5. Quality of Code.
