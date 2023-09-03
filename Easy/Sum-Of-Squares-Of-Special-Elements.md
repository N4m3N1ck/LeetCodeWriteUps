```python
class Solution:
    def sumOfSquares(self, nums: List[int]) -> int:
        n = len(nums)
        s=0
        for i in range(n):
            if n % (i+1) == 0:
                s += nums[i] ** 2
        return s
```
