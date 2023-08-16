# Isomorphic Strings
# Solution 1
We can go through each string and check if there is only one letter from another representing the current letter. We can do it by creating two dictionaries and looping through two of the strings
```python
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        d = {}
        for i in range(len(s)):
            if s[i] not in d:
                d[s[i]] = t[i]
            else:
                if d[s[i]] != t[i]:
                    return False
        d2 = {}
        for i in range(len(t)):
            if t[i] not in d2:
                d2[t[i]] = s[i]
            else:
                if d2[t[i]] != s[i]:
                    return False
        return True
```
Here is a way to solve the problem with only one for loop:
```python
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        d = {}
        d2 = {}
        for i in range(len(s)):
            if s[i] not in d:
                d[s[i]] = t[i]
            else:
                if d[s[i]] != t[i]:
                    return False
            if t[i] not in d2:
                d2[t[i]] = s[i]
            else:
                if d2[t[i]] != s[i]:
                    return False
        return True
```
