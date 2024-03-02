# Squares Of A Sorted Array
# Solution 1
```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        for i in range(len(nums)):
            nums[i] **= 2
        return sorted(nums)
```
# Linear Solution
```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        left = 0
        right = len(nums) - 1
        answer = []
        while left <= right:
            if nums[left] ** 2 > nums[right] ** 2:
                answer.append(nums[left] ** 2)
                left += 1
            else:
                answer.append(nums[right] ** 2)
                right -= 1
        return answer[::-1]
```
