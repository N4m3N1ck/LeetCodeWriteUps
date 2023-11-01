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
# O(n^2) optimized (Timeout)
Instead of calculating max_left on each step, we can store it and update it for each next element.
```python
class Solution:
    def trap(self, height: List[int]) -> int:
        total = 0
        max_left = 0
        for i in range(len(height)):
            max_right = 0
            for j in range(i + 1,len(height)):
                if height[j] > max_right:
                    max_right = height[j]
            total += max(0, min(max_left,max_right) - height[i])
            if height[i] > max_left:
                max_left = height[i]
        return total
```
# O(n) Solution
We can create two extra arrays: max_left_ar and max_right_ar. In these arrays we will store the max to the left and max to the right heights for each index. We can then use these values in the same way as before.
```python
class Solution:
    def trap(self, height: List[int]) -> int:
        max_left = 0
        max_right = 0
        max_left_ar = [0]*len(height)
        max_right_ar = [0]*len(height)
        for i in range(len(height)):
            max_left_ar[i] = max_left
            if height[i] > max_left:
                max_left = height[i]
            max_right_ar[len(height) - 1 - i] = max_right
            if height[len(height) - 1 - i] > max_right:
                max_right = height[len(height) - 1 - i]
        total = 0
        for i in range(len(height)):
            total += max(0,min(max_left_ar[i],max_right_ar[i]) - height[i])
        return total
```
