# Maximum Number Of Words Found In Sentences
```python
class Solution:
    def mostWordsFound(self, sentences: List[str]) -> int:
        n = 0
        for i in sentences:
            n = max(n,len(i.split()))
        return n
```
