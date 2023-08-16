# Find All Numbers Disappeared In The Array
# Solution 1
We can convert nums to a set to avoid checking repeating elements. We can go through each element from 1 to len(nums) and if it is not in there append it to the missing array.
```python
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        l = len(nums)
        nums = set(nums)
        ar = []
        for i in range(1,l+1):
            if i not in nums:
                ar.append(i)
        return ar
```
# Solution
Each element in the array will point at an index inside the array. We can mark off each index we see in the array. The indexes that were not marked are the numbers that weren't included. We can use the minus sign as the marker and check for all the positive indexes in the end.
```python
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        nums = [0]+nums
        for i in nums:
            nums[abs(i)] = -abs(nums[abs(i)])
        return [x for x in range(len(nums)) if nums[x] > 0]
```
