# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. Define a function `isPossible(row, col, val)` that checks whether placing `val` at `(row, col)` violates Sudoku rules in its row, column, or 3×3 subgrid.
2. Create a function `isEmpty()` that scans the board to find and return the coordinates of the first empty cell (with value 0), or `None` if the board is full.
3. Define a recursive function `solve()` that uses `isEmpty()` to find the next empty cell; if none is found, print the board and return `True`.
4. If an empty cell is found, try placing digits 1 to 9 using `isPossible()`; if valid, place it, call `solve()` recursively, and if it fails, reset the cell (backtrack).
5. Call `solve()` in the main execution to start solving the Sudoku puzzle and print the solution when found.

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: REXLIN R
Register Number:  212222220034
*/
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard():
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True
#####################  Add your code here #########################
def isEmpty():
    for r in range(9):
        for c in range(9):
            if board[r][c] == 0:
                return r, c
    return None


def solve():
    #####################  Add your code here #########################
    empty = isEmpty()
    if empty is None:
        printBoard()
        return True

    row, col = empty
    for guess in range(1, 10):
        if isPossible(row, col, guess):
            board[row][col] = guess
            if solve():
                return True
            board[row][col] = 0
    return False
solve()
```

## Output:

![image](https://github.com/user-attachments/assets/9b545643-9307-4933-a605-fc4a68c35aa3)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
