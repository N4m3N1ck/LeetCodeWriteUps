# Reverse Integer
We can convert the integer into a string, remove all zeroes from the end of it, reverse the integer and return it only if it's in the correct range
```python
class Solution:
    def reverse(self, x: int) -> int:
        x = str(x)
        while x[-1]==0 and x[-2]:
            x = x[:-1]
        if int(x) >= 0:
            x = int(x[::-1])
        else:
            x = -1 *int(x[1:][::-1])
        if x > 2**31-1 or x< -1 * 2**31:
            return 0
        else:
            return x
```
