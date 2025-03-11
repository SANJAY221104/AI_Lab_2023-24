# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 11/3/2025                                                                  
### REGISTER NUMBER : 212222060217
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:
```
import math

PLAYER = "X"
OPPONENT = "O"
EMPTY = "_"

def evaluate(board):
    for row in board:
        if row[0] == row[1] == row[2] and row[0] != EMPTY:
            return 10 if row[0] == PLAYER else -10
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] and board[0][col] != EMPTY:
            return 10 if board[0][col] == PLAYER else -10
    if board[0][0] == board[1][1] == board[2][2] and board[0][0] != EMPTY:
        return 10 if board[0][0] == PLAYER else -10
    if board[0][2] == board[1][1] == board[2][0] and board[0][2] != EMPTY:
        return 10 if board[0][2] == PLAYER else -10
    return 0

def is_moves_left(board):
    for row in board:
        if EMPTY in row:
            return True
    return False

def alphabeta(board, depth, alpha, beta, is_max):
    score = evaluate(board)
    if score == 10 or score == -10:
        return score - depth if score > 0 else score + depth
    if not is_moves_left(board):
        return 0
    if is_max:
        best = -math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == EMPTY:
                    board[i][j] = PLAYER
                    best = max(best, alphabeta(board, depth + 1, alpha, beta, False))
                    board[i][j] = EMPTY
                    alpha = max(alpha, best)
                    if beta <= alpha:
                        break
        return best
    else:
        best = math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == EMPTY:
                    board[i][j] = OPPONENT
                    best = min(best, alphabeta(board, depth + 1, alpha, beta, True))
                    board[i][j] = EMPTY
                    beta = min(beta, best)
                    if beta <= alpha:
                        break
        return best

def find_best_move(board):
    best_val = -math.inf
    best_move = (-1, -1)
    for i in range(3):
        for j in range(3):
            if board[i][j] == EMPTY:
                board[i][j] = PLAYER
                move_val = alphabeta(board, 0, -math.inf, math.inf, False)
                board[i][j] = EMPTY
                if move_val > best_val:
                    best_move = (i, j)
                    best_val = move_val
    return best_move

board = [
    ["X", "O", "X"],
    ["_", "X", "O"],
    ["_", "_", "_"]
]

print(f"Best move is at: {find_best_move(board)}")
```

### Output:
![Screenshot 2025-03-11 112741](https://github.com/user-attachments/assets/8986d826-5e2e-465a-b7da-c7f7a6b31990)



### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
