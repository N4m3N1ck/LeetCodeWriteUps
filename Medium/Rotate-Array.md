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
# Solution 2 - Reverse
We can reverse the array and then reverse the first k elements, and the remainder of the elements
```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        n = len(nums)
        k %= n
        nums.reverse()
        for i in range(k // 2):
            nums[i], nums[k - 1 - i] = nums[k - 1 - i], nums[i]
        for i in range(k, (n + k) // 2):
            nums[i], nums[n - 1 - i + k] = nums[n - 1 - i + k], nums[i]
```
