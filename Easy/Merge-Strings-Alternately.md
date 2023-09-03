# Merge Strings Alternately
```python
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        min_len = min(len(word1), len(word2))
        x = ""
        for i in range(min_len):
            x += word1[i]
            x += word2[i]
        if len(word1) == min_len:
            x += word2[min_len:]
        else:
            x += word1[min_len:]
        return x
```
