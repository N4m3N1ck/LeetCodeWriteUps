# Path Crossing
Store all visited points in a set, on each step check if the current point is in visited
```python
class Solution:
    def isPathCrossing(self, path: str) -> bool:
        moves = {
            "N": (0,1),
            "S": (0, -1),
            "E": (1,0),
            "W": (-1, 0)
        }
        cur_x = 0
        cur_y = 0
        visited = {(0,0)}
        for i in path:
            x, y = moves[i]
            cur_x += x
            cur_y += y
            if (cur_x,cur_y) in visited:
                return True
            visited.add((cur_x,cur_y))
        return False
```
