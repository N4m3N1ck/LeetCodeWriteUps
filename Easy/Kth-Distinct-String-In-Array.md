# Kth Distinct String In Array
```python
class Solution:
    def kthDistinct(self, arr: List[str], k: int) -> str:
        count = Counter(arr)
        c = 0
        for i in arr:
            if count[i] == 1:
                c += 1
                if c == k:
                    return i
        return ""
```
