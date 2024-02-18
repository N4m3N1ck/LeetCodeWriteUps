# Combination Sum
```python
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        answer = []
        def backtrack(array, arr_sum, candidates):
            if arr_sum == target:
                answer.append(array)
            elif arr_sum > target or candidates == []:
                return None
            else:
                backtrack(array + [candidates[0]], arr_sum + candidates[0], candidates)
                backtrack(array, arr_sum, candidates[1:])
        backtrack([],0, candidates)
        return answer
```
