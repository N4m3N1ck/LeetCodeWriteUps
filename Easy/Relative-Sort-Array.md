# Relative Sort Array
```python
class Solution:
    def relativeSortArray(self, arr1: List[int], arr2: List[int]) -> List[int]:
        ar3 = []
        ar4 = []
        ans = []
        for i in arr2:
            ar3 += [i] * arr1.count(i)
        for i in arr1:
            if i not in arr2:
                ar4.append(i)
        ar4.sort()
        return ar3 + ar4
```
