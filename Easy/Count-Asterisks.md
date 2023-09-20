# Count Asterisks
```python
class Solution:
    def countAsterisks(self, s: str) -> int:
        pair_in = True
        count = 0
        for i in s:
            if i == "|":
                pair_in = not pair_in
            elif i == "*" and pair_in:
                count += 1
        return count
```
