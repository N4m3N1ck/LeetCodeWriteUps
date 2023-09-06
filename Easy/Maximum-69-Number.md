# Maximum 69 Number
# Solution 1 - string conversion
```python
class Solution:
    def maximum69Number(self, num):
        return int(str(num).replace('6', '9', 1))
```
