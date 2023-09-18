# Coin Change
```python
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [0] + [float('inf')]*amount
        for i in range(1,amount+1):
            min_coins = float('inf')
            for j in coins:
                if (j <= i) and (-1 < dp[i-j] < min_coins):
                    min_coins = dp[i-j] + 1
            dp[i] = min_coins
            if dp[i] == float('inf'):
                dp[i] = -1
        print(dp)
        return dp[-1]
```
