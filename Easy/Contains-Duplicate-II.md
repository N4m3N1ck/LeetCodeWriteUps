# Contains Duplicate II
# Solution 1: O(n*k)
```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        for i in range(len(nums)):
            if nums[i] in nums[i + 1: i + k + 1]:
                return True
        return False
```
