# Generate Parentheses
Classic backtracking problem. The sequence of parentheses is valid only if at a any index of the sequence i >= j, where i is the amount of opening parentheses and j is the amount of closing parentheses. If the amount of closing parentheses is n, that means the sequence is finished. We will backtrack by adding "(" if we have enough opening parentheses, and backtrack by adding ")" if i > j.
```python
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        ans = []
        def backtrack(s, i, j):
            if j == n:
                ans.append(s)
            if i < n:
                backtrack(s + "(", i + 1, j)
            if j < i:
                backtrack(s + ")", i, j + 1)
        backtrack("", 0, 0)
        return ans
```
