# Ex.No: 3  Implementation of Minimax Search
### DATE: 11/03/2025                                                                    
### REGISTER NUMBER : 212222060217
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

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

def minimax(board, depth, is_max):
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
                    best = max(best, minimax(board, depth + 1, False))
                    board[i][j] = EMPTY
        return best
    else:
        best = math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == EMPTY:
                    board[i][j] = OPPONENT
                    best = min(best, minimax(board, depth + 1, True))
                    board[i][j] = EMPTY
        return best

def find_best_move(board):
    best_val = -math.inf
    best_move = (-1, -1)
    for i in range(3):
        for j in range(3):
            if board[i][j] == EMPTY:
                board[i][j] = PLAYER
                move_val = minimax(board, 0, False)
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
![Screenshot 2025-03-11 111307](https://github.com/user-attachments/assets/0728d8c8-4d58-419c-a9ba-eb46a50bf410)



### Result:
Thus the optimum value of max player was found using minimax search.
