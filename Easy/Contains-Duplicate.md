# Contains Duplicate
There are multiple ways to solve the problem
# Using python set
We can convert our list to a set which will remove the duplicates and check if the length are equal. If they are equal return false, otherwise return true
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        n = len(nums)
        return n != len(set(nums))
```
# Using a dictionary
We can store the number in the dictionary if we meet it in the array. If we meet one more time, there are duplicates. If we dont meet any number twice, there are no duplicates.
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        dictionary = {}
        for i in range(len(nums)):
            if nums[i] not in dictionary:
                dictionary[nums[i]] = 1
            else:
                return True
        return False
```
