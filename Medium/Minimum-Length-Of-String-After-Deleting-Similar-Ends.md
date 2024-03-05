# Mimnmym Length Of String After Deleting Similar Ends
```python
class Solution:
    def minimumLength(self, s: str) -> int:
        left = 0
        right = len(s) - 1
        while left < right and s[left] == s[right]:
            cur = s[left]
            while s[left] == cur and left < right:
                left += 1
            while s[right] == cur and left <= right:
                right -= 1
        return right - left + 1
```
