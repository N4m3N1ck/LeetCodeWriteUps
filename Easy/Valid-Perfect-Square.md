# Valid Perfect Square
Simple binary search
```python
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        l = 0
        r = num
        while l < r:
            mid = (l + r) // 2
            if mid ** 2 < num:
                l = mid + 1
            else:
                r = mid
        return l ** 2 == num
```
