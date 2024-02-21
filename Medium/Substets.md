# Subsets
Each subset can be represented as an array of booleans, where each boolean represents if the element is included into the subset. We can iterate through all the possible combinations using backtracking.
```python
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        answer = []
        def backtrack(arr):
            if len(arr) == len(nums):
                ans = []
                for i in range(len(arr)):
                    if arr[i] == True:
                        ans.append(nums[i])
                answer.append(ans)
            else:
                backtrack(arr + [False])
                backtrack(arr + [True])
        backtrack([])
        return answer
```
