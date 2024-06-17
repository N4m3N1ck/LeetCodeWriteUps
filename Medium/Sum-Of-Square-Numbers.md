# Sum Of Square Numbers
```python
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        left = 0
        right = int(sqrt(c))
        while left <= right:
            s = left ** 2 + right ** 2
            if s < c:
                left += 1
            elif s > c:
                right -= 1
            if s == c:
                return True
        return False

```
