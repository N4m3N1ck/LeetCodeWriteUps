# Maximum Product Difference Between Two Pairs
```python
class Solution:
    def maxProductDifference(self, nums: List[int]) -> int:
        min_1 = 100000
        min_2 = 100000
        max_1 = 0
        max_2 = 0
        for i in nums:
            if i < min_1:
                min_2 = min_1
                min_1 = i
            elif i < min_2:
                min_2 = i
            if i > max_1:
                max_2 = max_1
                max_1 = i
            elif i > max_2:
                max_2 = i
        return max_1 * max_2 - min_1 * min_2
```
