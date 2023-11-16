# Jump Game
If there is at least one number we cant get to, it means we cant get to any number after it. We can replace each nums[i] value with the max value between nums[i] and nums[i-1] - 1 ( because from this position we can also jump one step less of the previous position). If the previous number of any nums[i] is zero, we will count the amount of zeroes behind it and if the first number before zeroes cant jump over all the zeroes, then we cant get to all the numbers in the nums array and we return False. After iterating through each number in nums and we can get to every one of them, it means we can return True, aas we can get to t the last one.
```python
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        if len(nums) <= 1:
            return True
        if nums[0] == 0:
            return False
        for i in range(1, len(nums)):
            nums[i] = max(0, nums[i], nums[i-1] - 1)
            if nums[i - 1] == 0:
                zero_count = 0
                x = i - 1
                while x >= 0 and nums[x] == 0:
                    zero_count += 1
                    x -= 1
                if nums[x] <= zero_count:
                    return False
        return True
```
