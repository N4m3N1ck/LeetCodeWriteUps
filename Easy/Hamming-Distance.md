# Hamming Distance
We can calculate hamming distance by finding in how many places bits are different. We can use xor for this problem and count amount of 1s in xor
```python
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        return bin(x^y).count('1')
```
We can improve the code by avoiding using count function and instead use biot operation &
```python
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        xor = x ^ y
        n = 0
        while xor:
            n += 1
            xor = xor & xor - 1
        return n
```
This works because each time we will remove last 1 from original xor which means there will be one less ones after & operator
