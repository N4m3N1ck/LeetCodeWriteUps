# Min Cost Climbing Stairs
We can calculate min cost of each stair by finding the min cost between the previous two and adding current cost. The cost to reach the last stair is the solution to the problem. We will add last stair with cost 0 to the cost array to calculate min value between the last two.
```python
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        cost+=[0]
        dp = [0]*len(cost)
        dp[0],dp[1] = cost[0],cost[1]
        for i in range(2,len(cost)):
            dp[i] = min(dp[i-1],dp[i-2])+cost[i]
        return dp[-1]
```
