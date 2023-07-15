# Length of Last Word
An obvious solution using python is to use the split() function and return the length of the last element:
```python
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        return len(s.split()[-1])
```
