# Maximum Product of Two Elements in an Array
```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        max_1 = 0
        max_2 = 0
        for i in nums:
            if i > max_1:
                max_2 = max_1
                max_1 = i
            elif i > max_2:
                max_2 = i
        return (max_1 - 1) * (max_2 - 1)
```
