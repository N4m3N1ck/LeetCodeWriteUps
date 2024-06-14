# Minimum Increment To Make Array Unique
```python
class Solution:
    def minIncrementForUnique(self, nums: List[int]) -> int:
        # Sort the array
        nums.sort()
        ans = 0
        for i in range(1, len(nums)):
            # If the current element is the same as the prev or less: (i.e. 1,2,1)
            # We want to make it one more than prev. (1,2,2+1)
            # This way we remove the duplicate of the prev. or before prev.
            if nums[i] <= nums[i - 1]:
                ans += nums[i - 1] + 1 - nums[i]
                nums[i] = nums[i - 1] + 1
                
        return ans
```
