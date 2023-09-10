# Maximum Subarray
We can solve this problem using two pointers: left and right. We will start with both pointers at index of 0, and move the right pointer forward. We will keep track of the sum from left to the element before right. If the sum is less than zero, then there is no point to including it with the right pointer element, as it will reduce the total sum. So we move the left pointer to the right pointer and update max_sum on after each iteration.
```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        l = 0
        cur_sum = 0
        max_sum = nums[0]
        for r in range(len(nums)):
            if cur_sum < 0:
                l = r
                cur_sum = nums[r]
            else:
                cur_sum += nums[r]
            if cur_sum > max_sum:
                max_sum = cur_sum
        return max_sum
```
