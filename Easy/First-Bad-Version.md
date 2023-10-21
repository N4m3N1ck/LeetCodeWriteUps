# First Attempt
```python
# The isBadVersion API is already defined for you.
# def isBadVersion(version: int) -> bool:

class Solution:
    def firstBadVersion(self, n: int) -> int:
        l = 1
        r = n
        while isBadVersion(r-1):
            m = (l + r) // 2
            if isBadVersion(m) == True:
                r = m
            else:
                l = m
        return r
```
