# Minimum Sum Of Four Digit Number After Splitting Digits
The optimal way will always be two two digit numbers with the smallest possible decimal digits
```python
class Solution:
    def minimumSum(self, num: int) -> int:
        digits = []
        while num > 0:
            digits.append(num % 10)
            num //= 10
        digits.sort()
        return digits[0] * 10 + digits[3] + digits[1] * 10 + digits[2]
```
