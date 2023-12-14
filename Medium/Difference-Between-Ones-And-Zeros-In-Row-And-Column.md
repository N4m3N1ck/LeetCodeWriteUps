# Difference Between Ones And Zeros In Row And Column
We can count zeroes and ones in each row and coulmn by iterating through the matrix, after that we can loop through each element agian, and replace it with the sum of ones in its row and its column minus the sum of zeroes in its row and its column.
```python
class Solution:
    def onesMinusZeros(self, grid: List[List[int]]) -> List[List[int]]:
        ones_rows = [0] * len(grid)
        ones_cols = [0] * len(grid[0])
        zeroes_rows = [0] * len(grid)
        zeroes_cols = [0] * len(grid[0])
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j] == 1:
                    ones_rows[i] += 1
                    ones_cols[j] += 1
                else:
                    zeroes_rows[i] += 1
                    zeroes_cols[j] += 1
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                grid[i][j] = ones_rows[i] + ones_cols[j] - zeroes_rows[i] - zeroes_cols[j]
        return grid
```
