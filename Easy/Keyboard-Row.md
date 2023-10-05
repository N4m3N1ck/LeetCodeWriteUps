# Keyboard Row
# Solution 1 - all()
```python
class Solution:
    def findWords(self, words: List[str]) -> List[str]:
        r1 = "qwertyuiop"
        r2 = "asdfghjkl"
        r3 = "zxcvbnm"
        ans = []
        for i in words:
            if all(char in r1 for char in i.lower()) or all(char in r2 for char in i.lower()) or all(char in r3 for char in i.lower()):
                ans.append(i)
        return ans
```
