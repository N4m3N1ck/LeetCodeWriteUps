# Maximum Difference Between Increasing Elements
```python
class Solution:
    def maximumDifference(self, nums: List[int]) -> int:
        cur_min = nums[0]
        max_diff = 0
        for j in range(len(nums)):
            if nums[j] < cur_min:
                cur_min = nums[j]
            else:
                max_diff = max(max_diff, nums[j] - cur_min)
        return max_diff if max_diff > 0 else -1
```
