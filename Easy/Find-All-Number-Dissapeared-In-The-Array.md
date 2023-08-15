# Find All Numbers Dissapeared In The Array
# Solution 1
We can convert nums to a set to avoid checking repeating elements. We can go through each element from 1 to len(nums) and if it is not in there append it to missing array.
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
