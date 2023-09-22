# N-Repeated Element In Size 2N Array
```python
class Solution:
    def repeatedNTimes(self, nums: List[int]) -> int:
        v = []
        for i in nums:
            if i in v:
                return i
            v.append(i)
```
