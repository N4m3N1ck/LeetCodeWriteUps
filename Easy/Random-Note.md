# Ransom Note
We can solve the problem by creating two dictionaries and checking if nothing is left in the first dictionary, after we subtract the second dictionary
```python
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        return not collections.Counter(ransomNote) - collections.Counter(magazine)
```
