# Power Of Three
# Solution 1: linear
```python
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        x = 1
        while x<=n:
            if x==n:
                return True
            x*=3
        return False
```
# Solution 2: O(1)
```python
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        return n > 0 and 3**19 % n == 0
```
