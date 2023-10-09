# 3Sum Closest
If you have solved two sum, two sum ii and 3sum this problem is extremely easy. We will use the same approach as in 3 sum but for each sum we will check if it is the closest one so far.
```python
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        nums.sort()
        closest = float('inf')
        for i in range(len(nums)-2):
            l = i + 1
            r = len(nums) - 1
            while l < r:
                s = nums[l] + nums[r] + nums[i]
                if abs(target-s) < abs(target-closest):
                    closest = s
                if s > target:
                    r -= 1
                elif s < target:
                    l += 1
                else:
                    return target
        return closest
```
