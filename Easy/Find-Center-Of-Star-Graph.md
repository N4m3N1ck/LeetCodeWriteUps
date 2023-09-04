```python
class Solution:
    def findCenter(self, edges: List[List[int]]) -> int:
        guess1 = edges[0][0]
        guess2 = edges[0][1]
        if guess1 in edges[1]:
            return guess1
        return guess2
```
