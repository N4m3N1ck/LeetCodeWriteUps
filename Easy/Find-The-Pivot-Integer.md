# Find The Pivot Integer
We can say that:
k*(k + 1)/2 = n*(n + 1)/2 - k*(k + 1)/2 + k
We can solve it for k and we get: k = √((n^2+n)/2)
```python
class Solution:
    def pivotInteger(self, n: int) -> int:
        k = ((n ** 2 + n) // 2)**0.5
        if k % 1 != 0:
            return -1
        return int(k)
```
