# Check If N And Its Double Exists
```python
class Solution:
    def checkIfExist(self, arr: List[int]) -> bool:
        for i in arr:
            if i == 0:
                if arr.count(0) > 1:
                    return True
            elif i*2 in arr:
                return True
        return False
```
