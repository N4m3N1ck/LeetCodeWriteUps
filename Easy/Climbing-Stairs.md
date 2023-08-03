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
# DP solution
We can also solve this problem using DP:
We can create an array of length on n+1(because array starts at index 0). We can set the first to values of the array to one because there is only one way o climb zero stairs and only one way to climb one stair. For other elements in the array we can set them to the sum of the previous two items. Finally, we will return the last element in the array.
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        dp = [0]*(n+1)
        for i in range(len(dp)):
            if i==0 or i==1:
                dp[i] = 1
            else:
                dp[i] = dp[i-1]+dp[i-2]
        return dp[-1]
```
