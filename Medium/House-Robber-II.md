# House Robber II
The same approach as to House Robber, but return the max between the array without the first element, and the array without the last element
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        if len(nums) == 1:
            return nums[0]
        def helper(ar):
            n1 = 0
            n2 = 0
            for i in ar:
                t = max(i+n1,n2)
                n1 = n2
                n2 = t
            return n2
        return max(helper(nums[1:]), helper(nums[:-1]))
```
