# Excel Sheet Column Number
```python
class Solution:
    def titleToNumber(self, columnTitle: str) -> int:
        n = 0
        for i in range(len(columnTitle)):
            order = ord(columnTitle[i]) - 64
            j = len(columnTitle) - i - 1
            n += 26**j*order
        return n
```
