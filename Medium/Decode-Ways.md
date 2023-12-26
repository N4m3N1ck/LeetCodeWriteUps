# Decode Ways
## DFS Solution
```python
class Solution:
    def numDecodings(self, s: str) -> int:
        dp = {}
        if s == "":
            return 1
        def dfs(i):
            if i in dp:
                return dp[i]
            if i > len(s) - 1:
                return 1
            elif s[i] == "0":
                return 0
            if i == len(s) - 1:
                return 1
            c = dfs(i + 1)
            if i < len(s) - 1 and (s[i] == "1" or (s[i] == "2" and s[i + 1] in "0123456")):
                c += dfs(i + 2)
            dp[i] = c
            return c
        return dfs(0)
```
