# Longest Increasing Subsequence
# Solution 1 - I have no idea how it works
```python
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        dp = [1] * len(nums)
        for i in range(1, len(dp)):
            j = len(nums) - i - 1
            for k in range(j,len(nums)):
                if nums[k] > nums[j] and dp[len(nums) - k - 1] >= dp[i]:
                    dp[i] = dp[len(dp) - k - 1] + 1
        return max(dp)
```
