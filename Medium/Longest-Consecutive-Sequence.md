# Longest Consecutive Sequence
We will go through each element n, which is the start of the sequence (n-1 doesnt exist) and check if n + 1 exists for each next elements of the sequence.
```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        max_seq = 0
        nums = set(nums)
        for i in nums:
            if i - 1 not in nums:
                n = i
                while n + 1 in nums:
                    n += 1
                if n - i + 1 > max_seq:
                    max_seq = n - i + 1
        return max_seq
```
