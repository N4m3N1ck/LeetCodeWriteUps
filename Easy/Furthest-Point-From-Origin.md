# Furthest Point From Origin
```python
class Solution:
    def furthestDistanceFromOrigin(self, moves: str) -> int:
        l_count = 0
        r_count = 0
        u_count = 0
        for i in moves:
            if i == "L":
                l_count += 1
            elif i == "R":
                r_count += 1
            elif i == "_":
                u_count += 1
        return max(l_count, r_count) + u_count - min(l_count, r_count)
```
