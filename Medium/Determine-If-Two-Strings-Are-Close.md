# Determine If Two Strings Are Close
If the strings have different lengths or different set of characters, it's impossible to make them equal. We will count each letter in each string. If for each count in word1 there is the same count in word2, then they are close, because we can just swap the counts around to get the rightg string.
```python
class Solution:
    def closeStrings(self, word1: str, word2: str) -> bool:
        if len(word1) != len(word2) or set(word1) != set(word2):
            return False
        return not Counter(Counter(word1).values()) - Counter(Counter(word2).values())

```
