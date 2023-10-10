# Number Of Senior Citizens
```python
class Solution:
    def countSeniors(self, details: List[str]) -> int:
        n = 0
        for i in details:
            if int(i[11:13]) > 60:
                n += 1
        return n
```
