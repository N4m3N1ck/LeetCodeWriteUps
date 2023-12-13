# Special Positions In A Binary Matrix
```python
class Solution:
    def numSpecial(self, mat: List[List[int]]) -> int:
        # Record the count of ones in each row and each column
        rows_count = [0] * len(mat)
        cols_count = [0] * len(mat[0])
        for i in range(len(mat)):
            for j in range(len(mat[0])):
                if mat[i][j] == 1:
                    rows_count[i] += 1
                    cols_count[j] += 1
        # For each 1 in the matrix, check if it is unique in its column and its row.
        answer = 0
        for i in range(len(mat)):
            for j in range(len(mat[0])):
                if mat[i][j] == 1 and rows_count[i] == 1 and cols_count[j] == 1:
                    answer += 1
        return answer
```
