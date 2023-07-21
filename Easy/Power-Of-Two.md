# Power Of Two
We can solve this problem using binary. Numbers that are power of two start with one number 1 and have n zeroes in the end. For example: **bin(32) = 100000**, **bin(69) = 1000101**. We can check if it is true for the number.
```python
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        return n > 0 and bin(n).count('1')==1
```
Also, if the number is the power of two, for example 32 (100000) the previous number will be shorter by one digit and will consist of only number ones: bin(31) = 011111. We can perform & operation which will return zero if no bits match
```python
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        return n > 0 and not n & n-1
```
