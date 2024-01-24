# Target Sum
We will create a DFS function which has two arguments: index and sum. The index argument represents the current element we are going to add/subtract from the current sum argument. When the index reaches the limit, if the sum is equal to target return 1. Otherwise return 0.
```python
class Solution:
    def findTargetSumWays(self, nums: List[int], target: int) -> int:
        dp = {}
        def dfs(index,_sum):
            if (index, _sum) in dp:
                return dp[(index, _sum)]
            if index == len(nums):
                if _sum == target:
                    return 1
                else:
                    return 0
            x = dfs(index + 1, _sum + nums[index]) + dfs(index + 1, _sum - nums[index])
            dp[(index, _sum)] = x
            return x
        return dfs(0, 0)
```
