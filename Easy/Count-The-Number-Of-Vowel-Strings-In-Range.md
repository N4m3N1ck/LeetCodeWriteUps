# Count the Number of Vowel Strings in Range
```python
class Solution:
    def vowelStrings(self, words: List[str], left: int, right: int) -> int:
        ans = 0
        for i in range(left,right + 1):
            if words[i][0] in "aeiou" and words[i][-1] in "aeiou":
                ans += 1
        return ans
```
