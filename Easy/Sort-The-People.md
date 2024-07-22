# Sort The People
```python
class Solution:
    def sortPeople(self, names: List[str], heights: List[int]) -> List[str]:
        d = dict(zip(heights, names))
        heights.sort(reverse=True)
        ans = []
        for i in heights:
            ans.append(d[i])
        return ans
```
