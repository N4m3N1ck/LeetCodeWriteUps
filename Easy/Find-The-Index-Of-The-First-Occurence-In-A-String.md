# Find the Index of the First Occurrence in a String
The obvious solution for the problem would be using python index() function:
```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if needle not in haystack:
            return -1
        return haystack.index(needle)
```
