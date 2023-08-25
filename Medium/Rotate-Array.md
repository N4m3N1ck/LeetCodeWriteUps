# Rotate Array
# Solution 1 - Simple
We can take the last k elements, and put the behind the array:
```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        k%=len(nums)
        suffix = nums[-k:]
        prefix = nums[:len(nums)-k]
        for i in range(k):
            nums[i] = suffix[i]
        for i in range(k,len(nums)):
            nums[i] = prefix[i-k]
        return nums
```
