# Search a 2D Matrix
This is a simple binary search problem, in which we can treat the matrix as an array. left = 0, right = m * n. After that we can extract the coordinates on the matrix using whole division and modulus operations. The coordinates are only relevenat for comparison.
```python
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        left = 0
        m = len(matrix[0])
        n = len(matrix)
        right = n * m - 1
        while left < right:
            median  = (right + left) // 2
            y = median // m
            x = median % m
            if matrix[y][x] < target:
                left = median + 1
            else:
                right = median
        y = left // m
        x = left % m
        return matrix[y][x] == target
```
