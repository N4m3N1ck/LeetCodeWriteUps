# Coin Change
This is a DP problem, so we can calculate the min amount of coins to add to all amounts between 0 and amount. To make up amount of 0, we take zero coins. For the next elements we will try each of the coins, subtract it from current amount and find the corresponding amount in the previous elements of dp. The one with smallest amount of coins is the best choice.
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
