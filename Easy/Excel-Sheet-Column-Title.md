# Excel Sheet Column Title
```python
class Solution(object):
    def convertToTitle(self, columnNumber):
        ans = ""
        while columnNumber > 0:
            ans = chr(ord('A') + (columnNumber - 1) % 26) + ans
            columnNumber = (columnNumber - 1) // 26
        return ans
```
