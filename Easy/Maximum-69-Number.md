# Maximum 69 Number
# Solution 1 - List
```python
class Solution:
    def maximum69Number (self, num: int) -> int:
        num = list(str(num))
        if "6" not in num:
            return int("".join(num))
        for i in range(len(num)):
            if num[i] == "6":
                num[i] = "9"
                break
        return int("".join(num))
```
