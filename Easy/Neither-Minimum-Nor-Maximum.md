```python
class Solution:
    def findNonMinOrMax(self, nums: List[int]) -> int:
        if len(nums) <= 2:
            return -1
        mn = min(nums)
        mx = max(nums)
        for i in nums:
            if i != mn and i != mx:
                return i
```
