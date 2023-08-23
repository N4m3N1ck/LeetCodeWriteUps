# Count The Number Of Consistent Strings
```python
class Solution:
    def countConsistentStrings(self, allowed: str, words: List[str]) -> int:
        def isConsistent(s1,s2):
            for i in s1:
                if i not in s2:
                    return False
            return True
        n = 0
        for i in words:
            if isConsistent(i,allowed):
                n+=1
        return n
```
