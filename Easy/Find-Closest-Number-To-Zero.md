```python
class Solution:
    def findClosestNumber(self, nums: List[int]) -> int:
        closest=float("inf")
        closest_i=0
        for i in nums:
            if abs(i)<closest:
                closest=abs(i)
                closest_i=i
            elif abs(i)==closest:
                if i > closest_i:
                    closest_i=i
        return closest_i
```
