```python
class Solution:
    def heightChecker(self, heights: List[int]) -> int:
        s= sorted(heights)
        n=0
        for i in range(len(s)):
            if s[i] != heights[i]:
                n+=1
        return n
```
