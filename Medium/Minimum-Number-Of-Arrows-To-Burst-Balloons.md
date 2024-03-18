# Minimum Number Of Arrows To Burst Balloons
We can sort the balloons by the right edge from the lowest to highest. The optimal way of popping the balloons is to always shoot at the rightmost side of the leftmost balloon.
```python
class Solution:
    def findMinArrowShots(self, points: List[List[int]]) -> int:
        points.sort(key = lambda x: -x[1])
        ans = 0
        print(points)
        while points:
            x = points[-1][1]
            while points and points[-1][0] <= x <= points[-1][1]:
                points.pop()
            ans += 1
        return ans
``
