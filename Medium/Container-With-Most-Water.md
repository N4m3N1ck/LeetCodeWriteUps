# Container With Most Water
Let's create two pointer left and right and move them towards each other while storing the max value. Each move we will take the lowest one and move it closer to the middle, so that the outcome volume will be as large as possible. 
```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        left = 0
        right = len(height)-1
        max_v = 0
        while left<right:
            if min(height[left],height[right]) * (right-left) > max_v:
                max_v = min(height[left],height[right]) * (right-left)
            if height[left]<height[right]:
                left+=1
            else:
                right -= 1

        return max_v
```
