# Assign Cookies
Sort s and g, create to variables: last_child, last_cookie, both set to 0. If s[last_child] can take the cookie, we add 1 to answer, add one to both last_child and last_cookie to move to the next child and cookie. If the child can't take the cookie, we will take the next cookie, until the child takes it.
```python
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:
        s.sort()
        g.sort()
        ans = 0
        last_cookie = 0
        last_child = 0
        while last_child < len(g) and last_cookie < len(s):
            if g[last_child] <= s[last_cookie]:
                last_cookie += 1
                last_child += 1
                ans += 1
            else:
                last_cookie += 1
        return ans
```
