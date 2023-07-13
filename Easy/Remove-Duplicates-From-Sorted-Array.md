# Remove Duplicates from sorted array
The problem wants us to modify the array so that the first n elements of the array are unique, where n is the amount of unique elements. We also need to return n.
# Solution
We will loop through each element in the array and check if it is unique. We can do it by comparing it to the previous element. We will then replace older elements in the array with the unique ones as we go. The first n elements will be the sorted array of unique items.
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        cur = 1
        for i in range(1,len(nums)):
            if nums[i] != nums[i-1]:
                nums[cur] = nums[i]
                cur+=1
        return cur
```
