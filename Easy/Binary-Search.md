# Binary Search
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums)-1
        while left<right:
            mid = (left+right)//2
            if nums[mid]>=target:
                right = mid
            else:
                left = mid + 1
        if nums[left] == target:
            return left
        return -1
```
We can create two pointers: left and right. We will calculate the pointer in the middle and compare it to the target. If it is more or equal to target, we will move right pointer to the mid pointer which will remove all the items above mid from our search. Otherwise we will move left to mid+1 and remove all the items that are less than mid. When left and right pointers meet we will return nums[left] but first we need to check if target is actuall in the list.
