# Construct The Rectangle
Width will not be more then the integer square root of the area. We will subtract one from width until area is divisible by it.
```python
class Solution:
    def constructRectangle(self, area: int) -> List[int]:
        import math
        width = math.isqrt(area)
        while area % width != 0:
            width -= 1
        return [area // width, width]
```
