# Hamming Distance
We can calculate hamming distance by finding in how many places bits are different. We can use xor for this problem and count amount of 1s in xor
```python
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        return bin(x^y).count('1')
```
