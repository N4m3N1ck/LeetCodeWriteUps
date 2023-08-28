```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        mx=0
        cur=0
        for i in nums:
            if i==1:
                cur+=1
            else:
                if cur > mx:
                    mx = cur
                cur=0
        return max(cur,mx)
```
