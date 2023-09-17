# Contains Duplicate II
# Solution 1: O(n*k)
```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        for i in range(len(nums)):
            if nums[i] in nums[i + 1: i + k + 1]:
                return True
        return False
```
# Solution 2: Dictionary
We can create a dictionary which stores all the previously visited numbers and their indices. If at some point we get to an element which is already in the dictionary and the index of this element stored in the dictionary is closer or as close as k, we return True
```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        dic = {}
        for i in range(len(nums)):
            if nums[i] in dic and i - dic[nums[i]] <= k:
                return True
            dic[nums[i]] = i
        return False

```
