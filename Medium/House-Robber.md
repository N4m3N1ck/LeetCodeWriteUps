# House Robber
We can calculate the max profit for each house by selecting from: a) this house and house before the previous profit. b) previous house profit. We can do it for each house and we will get the solution at the last house.
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        n1 = 0
        n2 = 0
        for i in nums:
            t = max(i+n1,n2)
            n1 = n2
            n2 = t
        return n2
```
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        if len(nums)==1:
            return nums[0]
        dp = [nums[0],max(nums[0],nums[1])]
        for i in range(2,len(nums)):
            dp.append(max(dp[-1],dp[-2]+nums[i]))
        return dp[-1]
```
