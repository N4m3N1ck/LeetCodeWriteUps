# Set Matrix Zeroes
```python
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        zero_rows = []
        zero_cols = []
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                if matrix[i][j] == 0:
                    if i not in zero_rows:
                        zero_rows.append(i)
                    if j not in zero_cols:
                        zero_cols.append(j)
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                if i in zero_rows or j in zero_cols:
                    matrix[i][j] = 0
        return matrix
```
