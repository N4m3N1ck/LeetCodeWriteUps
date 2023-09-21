# Longest Increasing Subsequence
Here, I loop through dp and loop through nums in reverse. The last element of nums has a max subsequence of 1, itself. The previous element will be the start of the subsequence either one (itself) or there is a smaller element in front of it. We will loop through all the elements after it that are smaller and get the largest dp value among those elements. We will add one to this value to include the current element. The max of dp is the longest increasing subsequence.
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
