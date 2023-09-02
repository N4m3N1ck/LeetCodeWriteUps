# Matrix Diagonal Sum
We can go through each element on the diagonal by using same x and y or opposite x and y. If the matrix has an odd length we can subtract the middle element
```python
class Solution:
    def diagonalSum(self, mat: List[List[int]]) -> int:
        s = 0
        if len(mat)%2!=0:
            s -= mat[len(mat)//2][len(mat)//2]
        for i in range(len(mat)):
            s += mat[i][i]
            s += mat[i][len(mat)-1-i]
        return s
```
