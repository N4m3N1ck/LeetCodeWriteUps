# Jump Game
Somehow it works.
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
