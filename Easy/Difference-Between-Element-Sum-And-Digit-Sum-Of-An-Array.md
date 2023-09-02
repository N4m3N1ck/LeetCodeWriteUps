# Difference Between Element Sum and Digit Sum of an Array
```python
class Solution:
    def differenceOfSum(self, nums: List[int]) -> int:
        element_sum = sum(nums)
        digit_sum = 0
        for i in nums:
            while i != 0:
                digit_sum += i%10
                i//=10
        return abs(element_sum-digit_sum)
```
DailyCTF:
flag{You think it's so easy lol}
