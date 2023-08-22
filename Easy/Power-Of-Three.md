# Power Of Three
# Solution 1: linear
We can raise three to all the powers while it's less than n and check if it's equal to n
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
3**19 is the largest power of three. It's only divisible by numbers that are also a power of three only
```python
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        return n > 0 and 3**19 % n == 0
```
