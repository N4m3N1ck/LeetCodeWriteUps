# Minimum Number of Operations to Make Array Empty
```python
class Solution:
    def minOperations(self, nums: List[int]) -> int:
        d = Counter(nums)
        ans = 0
        for i in d.values():
            if i == 1:
                return -1
            if i % 3 == 0:
                ans += i // 3
            elif i % 3 == 2:
                ans += i // 3 + 1
            else:
                ans += (i - 4) // 3
                ans += 2
        return ans
```
