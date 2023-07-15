# Search Insert Position
An obvious solution would be to create a while loop like this:
```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        cur = 0
        n = len(nums)
        while cur < n and nums[cur] <= target:
            cur += 1
        if target in nums:
            return cur-1
        return cur
```
We will continue the loop while the current number is less than target, and when it becomes more than target, we stop the loop.
# Binary Search
This problem can be solved using binary search. You can check out this article about binary search: https://www.geeksforgeeks.org/binary-search/
```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums)
        while left < right:
            mid = (left+right) // 2
            if nums[mid] < target:
                left = mid + 1
            else:
                right = mid
        return left
```
