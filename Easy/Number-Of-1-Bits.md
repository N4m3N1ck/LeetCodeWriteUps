# Number Of 1 Bits
```python
class Solution:
    def hammingWeight(self, n: int) -> int:
        i = 0
        while n:
            n &= n-1
            i+=1
        return i
``
Every time we perform n&=n-1 we remove the last '1' from n. For example: bin(69) = 1000101, bin(68) = 1000100. 1000101&1000100 = 1000100. We succesfully removed last '1' from the number. We can repeat this step until the number is zero.
