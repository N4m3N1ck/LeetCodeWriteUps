# Running Sum of 1D Array
We can loop through each element of the array except the first one and add the previous element to the value:
```python
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        for i in range(1,len(nums)):
            nums[i] +=nums[i-1]
        return nums
```
