```python
class Solution:
    def numOfStrings(self, patterns: List[str], word: str) -> int:
        n = 0
        for i in patterns:
            if i in word:
                n += 1
        return n
```
