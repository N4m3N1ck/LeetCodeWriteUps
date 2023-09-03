# Find Numbers With Even Number Of Digits
```python
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        n = 0
        for i in nums:
            d = 0
            while i != 0:
                d += 1
                i //= 10
            if d%2==0:
                n += 1
        return n
```
