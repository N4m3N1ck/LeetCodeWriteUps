```python
class Solution:
    def countPairs(self, nums: List[int], target: int) -> int:
        n = 0
        for i in range(len(nums)):
            for j in range(i+1, len(nums)):
                if nums[i]+nums[j]<target:
                    n+=1
        return n
```
