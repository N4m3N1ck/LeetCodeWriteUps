```python
class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        x=[""]*len(s)
        for i in range(len(s)):
            x[indices[i]]=s[i]
        return "".join(x)
```
