# Solution 1
```python
class Solution:
    def checkString(self, s: str) -> bool:
        if "b" not in s:
            return True
        first_b = 0
        for i in range(len(s)):
            if s[i] == "b":
                first_b = i
                break
        return "a" not in s[first_b:]
```
# Solution 2
```python
class Solution:
    def checkString(self, s: str) -> bool:
        return "ba" not in s
```