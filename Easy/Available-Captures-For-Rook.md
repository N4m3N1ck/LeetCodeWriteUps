# Available Captures For Rook
```python
class Solution:
    def numRookCaptures(self, board: List[List[str]]) -> int:
        captures = 0
        # Locate the rook
        x, y = 0, 0
        for i in range(8):
            for j in range(8):
                if board[i][j] == "R":
                    x = j
                    y = i
        print(x,y)
        # Check for captures to the right
        for i in range(x + 1, 8):
            if board[y][i] == ".":
                continue
            elif board[y][i] == "B":
                break
            else:
                captures += 1
                break
        # Check for captures to the left
        for i in range(0, x):
            j = x - 1 - i
            if board[y][j] == ".":
                continue
            elif board[y][j] == "B":
                break
            else:
                captures += 1
                break
        # Check for captures below
        for i in range(y + 1, 8):
            if board[i][x] == ".":
                continue
            elif board[i][x] == "B":
                break
            else:
                captures += 1
                break
        # Check for captures above
        for i in range(0, y):
            j = y - 1 - i
            if board[j][x] == ".":
                continue
            elif board[j][x] == "B":
                break
            else:
                captures += 1
                break
        return captures
```
