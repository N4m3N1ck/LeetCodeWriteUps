# Largest 3 Same Digit Number In String
We can store the 3 digits in variables d1, d2 and d3 and increment them by one on each iteration. On each iteration, we will check if d1 is equal to d2 and is equal to d3. We will also store the largest digit in max_d1. At the end we return str(max_d1) * 3 if max_d1 > -1 (the initial value), otherwise we return empty string.
```python
class Solution:
    def largestGoodInteger(self, num: str) -> str:
        d1 = 0
        d2 = 1
        d3 = 2
        max_d1 = -1
        for i in range(len(num)-2):
            if num[d1] == num[d2] == num[d3] and int(num[d1]) > max_d1:
                max_d1 = int(num[d1])
            d1 += 1
            d2 += 1
            d3 += 1
        if max_d1 != -1:
            return str(max_d1) * 3
        return ""
```
