# Element Appearing More Than 25% In Sorted Array
# Linear Solution
```python
class Solution:
    def findSpecialInteger(self, arr: List[int]) -> int:
        n = len(arr) // 4
        for i in range(len(arr)):
            if arr[i] == arr[i + n]:
                return arr[i]
        return None
```
