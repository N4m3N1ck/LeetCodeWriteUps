# Sorting The Sentence
# Solution 1 - Messy One-Liner
```python
class Solution:
    def sortSentence(self, s: str) -> str:
        return " ".join([x[:-1] for x in sorted(s.split(),key=lambda x: x[-1])])
```
# Solution 2
```python
class Solution:
    def sortSentence(self, s: str) -> str:
        arr = [i[-1] + i[:-1] for i in s.split()]
        arr.sort()
        ans = ""
        for i in arr:
            ans += i[1:] + ' '
        return ans[:-1]
```
