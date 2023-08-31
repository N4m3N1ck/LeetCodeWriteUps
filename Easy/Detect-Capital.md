```python
class Solution:
    def detectCapitalUse(self, word: str) -> bool:
        return word.lower()==word or word.capitalize()==word or word.upper()==word
```
