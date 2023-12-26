# Decode Ways
## DFS Solution
Number 12 can be decoded as AB or as L. The number of ways to decode a string is the number of ways to decode the string from the next letter, plus the number of ways to decode the string from the second next letter IF the first plus second letter make a number less than 26. If the first letter is zero, no combinations are possible. There is only one way to decode a string of the length one or less.
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
