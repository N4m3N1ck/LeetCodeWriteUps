# Spiral Matrix
```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        ans = []
        highest_row = 0
        lowest_row = len(matrix) - 1
        leftest_col = 0
        rightest_col = len(matrix[0]) - 1
        while highest_row <= lowest_row and leftest_col <= rightest_col:
            for i in range(leftest_col,rightest_col + 1):
                ans.append(matrix[highest_row][i])
            highest_row += 1
            for i in range(highest_row,lowest_row + 1):
                ans.append(matrix[i][rightest_col])
            rightest_col -= 1
            if highest_row <= lowest_row:
                for i in range(-rightest_col,-leftest_col + 1):
                    j = -i
                    ans.append(matrix[lowest_row][j])
            lowest_row -= 1
            if leftest_col <= rightest_col:
                for i in range(-lowest_row,-highest_row + 1):
                    j = -i
                    ans.append(matrix[j][leftest_col])
            leftest_col += 1
        return ans
```
