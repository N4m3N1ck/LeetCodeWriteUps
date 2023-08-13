# Valid Sudoku
To be valid, the sudoku needs to satisfy three conditions: <br>
1. No numbers repeat in each row
2. No numbers repeat in each column
3. Sudoku is divided in nine 3x3 squares. No numbers must repeat in those squares
```python
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        for nums in board:
            for i in "123456789":
                if nums.count(i)>1:
                    return False
        for i in range(9):
            ar = []
            for j in board:
                ar.append(j[i])
            for x in "123456789":
                if ar.count(x)>1:
                    return False
        left_up_corners = ["00","30","60","03","33","63","06","36","66"]
        for i in left_up_corners:
            ar = []
            for j in range(3):
                for k in range(3):
                    ar.append(board[int(i[0])+j][int(i[1])+k])
            for x in "123456789":
                if ar.count(x)>1:
                    return False
        return True
```
