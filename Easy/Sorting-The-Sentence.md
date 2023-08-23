# Sorting The Sentence
# Solution 1 - Messy One-Liner
```python
class Solution:
    def sortSentence(self, s: str) -> str:
        return " ".join([x[:-1] for x in sorted(s.split(),key=lambda x: x[-1])])
```
