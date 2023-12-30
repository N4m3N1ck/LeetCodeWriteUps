# Redistribute Characters To Make All Strings Equal
```python
class Solution:
    def makeEqual(self, words: List[str]) -> bool:
        count = {}
        for i in words:
            for j in i:
                if j in count:
                    count[j] += 1
                else:
                    count[j] = 1
        for i in count:
            if count[i] % len(words) != 0:
                return False
        return True
```
