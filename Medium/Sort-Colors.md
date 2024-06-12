# Sort Colors
Count each color, replace the first 'zeroes' elements with a 0, replace the next 'ones' elements with a 1, and replace the last 'twos' elements with a 2
```python
class Solution:
    def sortColors(self, nums: List[int]) -> None:
        zeroes = nums.count(0)
        ones = nums.count(1)
        twos = nums.count(2)
        for i in range(len(nums)):
            if i < zeroes:
                nums[i] = 0
            elif i < zeroes + ones:
                nums[i] = 1
            else:
                nums[i] = 2
```
