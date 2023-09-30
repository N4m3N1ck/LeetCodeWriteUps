# Maximum Odd Binary Number
```python
class Solution:
    def maximumOddBinaryNumber(self, s: str) -> str:
        zero_count = 0
        one_count = 0
        for i in s:
            if i == "0":
                zero_count += 1
            else:
                one_count += 1
        return "1" * (one_count - 1) + "0" * zero_count + "1"
```
