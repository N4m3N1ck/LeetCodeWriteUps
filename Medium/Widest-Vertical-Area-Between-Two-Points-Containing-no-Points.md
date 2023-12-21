# Widest Vertical Area Between Two Points Containing No Points
We can completely ignore the y value, make a new array of x values, sort them and return two adjacent values that are the furthest from each other
```python
class Solution:
    def maxWidthOfVerticalArea(self, points: List[List[int]]) -> int:
        x = []
        for i in points:
            x.append(i[0])
        x.sort()
        max_diff = 0
        for i in range(len(x) - 1):
            if x[i+1] - x[i] > max_diff:
                max_diff = x[i+1] - x[i]
        return max_diff
```
