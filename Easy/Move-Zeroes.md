# Move Zeroes
We can solve the problem by storing the number of zeroes we collected by iterating through the array. If we meet a non-zero element i, we will swap it with i-zero_count element, which is zero. At the end we will have all zeroes at the end of the array 
```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        cur_zero_count = 0
        for i in range(len(nums)):
            if nums[i] == 0:
                cur_zero_count += 1
            else:
                if cur_zero_count > 0:
                    nums[i-cur_zero_count] = nums[i]
                    nums[i] = 0
```
