# Permutations
Simple backtracking solution
```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        ans = []
        def backtrack(a):
            if len(a) == len(nums):
                ans.append(a)
                return
            for i in nums:
                if i not in a:
                    backtrack(a+[i])
        backtrack([])
        return ans
```
