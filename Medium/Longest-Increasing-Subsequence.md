# Longest Increasing Subsequence
# Solution 1 - I have no idea how it works
```python
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        dp = [1] * len(nums)
        for i in range(1, len(dp)):
            j = len(nums) - i - 1
            n = 0
            for k in range(j,len(nums)):
                if nums[k] > nums[j] and dp[len(dp) - k - 1] > n:
                    n = dp[len(dp) - k - 1]
            dp[i] = n + 1
        return max(dp)
```
