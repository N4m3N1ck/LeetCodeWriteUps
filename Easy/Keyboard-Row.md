# Keyboard Row
# Solution 1 - all()
```python
class Solution:
    def findWords(self, words: List[str]) -> List[str]:
        r1 = "qwertyuiop"
        r2 = "asdfghjkl"
        r3 = "zxcvbnm"
        ans = []
        for i in words:
            if all(char in r1 for char in i.lower()) or all(char in r2 for char in i.lower()) or all(char in r3 for char in i.lower()):
                ans.append(i)
        return ans
```
# Solution 2 - set theory
We can check if one set is a subset of another one by using <=
```python
class Solution:
    def findWords(self, words: List[str]) -> List[str]:
        r1, r2, r3 = set("qwertyuiop"), set("asdfghjkl"), set("zxcvbnm")
        ans = []
        for i in words:
            s = set(i.lower())
            if s <= r1 or s <= r2 or s <= r3:
                ans.append(i)
        return ans
```
