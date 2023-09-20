# Determine If String Halves Are Alike
```python
class Solution:
    def halvesAreAlike(self, s: str) -> bool:
        count_1 = 0
        count_total = 0
        for i in range(len(s)):
            if s[i].lower() in "aeuoi":
                if i < len(s) // 2:
                    count_1 += 1
                count_total += 1
        return count_1 * 2 == count_total
```
