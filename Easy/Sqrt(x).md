# Sqrt(x)
An obvious solution to the problem is a linear approach:
```python
class Solution:
    def mySqrt(self, x: int) -> int:
        n=0
        while n**2<x:
            n+=1
        if n**2==x: return n
        return n-1
```
# Binary search
There are multiple ways to implement binary search:
```python
class Solution:
    def mySqrt(self, x: int) -> int:
        left = 0
        right = x
        mid = 0
        while not(mid ** 2 <= x<(mid+1)**2):
            mid = (left+right)//2
            if mid ** 2 < x:
                left = mid + 1
            else:
                right = mid - 1
        return mid
```
and
```python
class Solution:
    def mySqrt(self, x: int) -> int:
        left = 0
        right = x
        mid = 0
        while left<right:
            mid = (left+right)//2 + 1
            if mid**2<=x<(mid+1)**2:
                return mid
            elif mid ** 2 > x:
                right = mid - 1
            else:
                left = mid
        return mid
```
