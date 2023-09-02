```python
class Solution:
    def splitWordsBySeparator(self, words: List[str], separator: str) -> List[str]:
        ar=[]
        for i in words:
            ar+=i.split(separator)
        return [x for x in ar if len(x)>0]
```
