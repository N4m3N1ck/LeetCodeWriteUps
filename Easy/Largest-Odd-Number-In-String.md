# Largest Odd Number In String
Odd number ends with an odd digit. This is the only requirement for an odd number. The largest odd number will always start at 0 and will always end at the last odd number. So if we loop through the digits in reverse, when we get to an odd number, we just return the string up to this number.
```python
class Solution:
    def largestOddNumber(self, num: str) -> str:
        for i in range(len(num)):
            if num[len(num) - i - 1] in "13579":
                return num[:len(num) - i]
        return ""
```
