# Thousand Separator
```python
class Solution:
    def thousandSeparator(self, n: int) -> str:
        s = ""
        if n < 10:
            return str(n)
        c = 0
        while n:
            x = n % 10
            n //= 10
            c += 1
            s += str(x)
            if c % 3 == 0:
                s += "."
        s = s[::-1]
        if s[0] == ".":
            return s[1:]
        return s
```
