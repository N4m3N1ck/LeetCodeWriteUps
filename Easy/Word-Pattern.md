# Word Pattern
The problem is almost the same as problem "Isomorphic Strings". We can use the same approach of two dictionaries and checking if each letter has a unique word from the other strings
```python
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        s = s.split()
        if len(s) != len(pattern):
            return False
        d = {}
        d2 = {}
        for i in range(len(pattern)):
            if pattern[i] not in d:
                d[pattern[i]] = s[i]
            else:
                if d[pattern[i]]!=s[i]:
                    return False
            if s[i] not in d2:
                d2[s[i]] = pattern[i]
            else:
                if d2[s[i]]!=pattern[i]:
                    return False
        return True
```
