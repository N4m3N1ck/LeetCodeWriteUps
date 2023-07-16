# Length of Last Word
An obvious solution using python is to use the split() function and return the length of the last element:
```python
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        return len(s.split()[-1])
```
A better solution is to loop from the end of the string until we meet the space character:
```python
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        return len(s.split()[-1])
        i = len(s)-1
        while i >= 0 and s[i]!=" ":
            i -= 1
        return len(s)-1 - i
```
