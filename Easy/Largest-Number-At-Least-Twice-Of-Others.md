```python
class Solution:
    def dominantIndex(self, nums: List[int]) -> int:
        max_index = 0
        max_value = 0
        for i in range(len(nums)):
            if max_value < nums[i]:
                max_value = nums[i]
                max_index = i
        for i in range(len(nums)):
            if nums[i] != max_value and nums[i]*2 > max_value:
                return -1
        return max_index
```
