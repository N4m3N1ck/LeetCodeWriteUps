# O(n^2) solution - slow (Timeout)
We can loop through each element of the array, fijnd the highest point to the left and the highest point to the right. We will then take the lowest one of them (this is the maximum possible height for the water before it spills out) and subtract the height of the current element(it is occupied by the blocks).
```python
class Solution:
    def trap(self, height: List[int]) -> int:
        total = 0
        for i in range(len(height)):
            max_left = 0
            max_right = 0
            for j in range(i):
                if height[j] > max_left:
                    max_left = height[j]
            for j in range(i + 1,len(height)):
                if height[j] > max_right:
                    max_right = height[j]
            total += max(0, min(max_left,max_right) - height[i])
        return total
```
