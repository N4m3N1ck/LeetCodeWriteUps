# Longest Continuous Increasing Subsequence
```python
class Solution:
    def findLengthOfLCIS(self, nums: List[int]) -> int:
        max_len = 1
        cur_len = 1
        for i in range(1, len(nums)):
            if nums[i] > nums[i - 1]:
                cur_len += 1
            else:
                if cur_len > max_len:
                    max_len = cur_len
                cur_len = 1
        if cur_len > max_len:
            max_len = cur_len
        return max_len
```
