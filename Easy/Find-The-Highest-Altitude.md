# Find The Highest Altitude
```python
class Solution:
    def largestAltitude(self, gain: List[int]) -> int:
        cur=0
        m=0
        for i in gain:
            cur+=i
            if cur>m:
                m=cur
        return m
```
