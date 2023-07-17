# Climbing Stairs
Number of ways we can get to each stair is the number of ways we can get the previous stair and the second previous stair. So basically it's a fibonacchi sequence. We can solve it using recursion and memoization:
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        memo = {}
        def rec(n):
            if n in memo:
                return memo[n]
            if n == 1:
                return 1
            if n == 2:
                return 2
            memo[n] = rec(n-1) + rec(n-2)
            return memo[n]
        return rec(n)
```
We will create to base cases for n = 1 and n = 2 and we will also check if n is in memo not to calculate the same staircase multiple times. Otherwise the number of ways to reach stair n is rec(n-1) + rec(n-2)
