# Transpose Matrix
## Manual Solution
Create new matrix with swapped height and width, insert elements from old matrix with swapped coordinates
```python
class Solution:
    def transpose(self, matrix: List[List[int]]) -> List[List[int]]:
        x = len(matrix)
        y = len(matrix[0])
        ans = []
        for i in range(y):
            ans.append([None]*x)
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                ans[j][i] = matrix[i][j]
        return ans

```
