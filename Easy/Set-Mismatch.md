# Set Mismatch
```python
class Solution:
    def findErrorNums(self, nums: List[int]) -> List[int]:
        expected_sum = (len(nums) * (len(nums) + 1)) // 2
        current_sum = sum(nums)
        set_sum = sum(set(nums))
        # Find the duplicate element
        duplicate = current_sum - set_sum
        # Find the missing element
        # expected_sum - current_sum = missing - duplicate
        missing = expected_sum - current_sum + duplicate
        return [duplicate, missing]
```
