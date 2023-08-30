```python
class Solution:
    def repeatedCharacter(self, s: str) -> str:
        visited = []
        for i in s:
            if i in visited:
                return i
            else:
                visited.append(i)
```
