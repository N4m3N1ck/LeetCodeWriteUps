# Unique Paths
# Recursion + Memoization
```python
class Solution:
    def uniquePaths(self, m: int, n: int, memo = {}) -> int:
        if m == 1 or n == 1:
            return 1
        if f"{m},{n}" in memo:
            return memo[f"{m},{n}"]
        if f"{n},{m}" in memo:
            return memo[f"{n},{m}"]
        
        x = self.uniquePaths(m - 1, n) + self.uniquePaths(m, n - 1)
        memo[f"{n},{m}"] = x
        return x
```
