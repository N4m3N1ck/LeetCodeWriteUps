# Squares Of A Sorted Array
# Solution 1
```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        for i in range(len(nums)):
            nums[i] **= 2
        return sorted(nums)
```
