# Reverse String
This problem can be easily solved by creating two pointer left and right. Each iteration we can swap items in these pointers and add 1 to left and subtract 1 from right.
```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        left = 0
        right = len(s)-1
        while left<right:
            s[left],s[right] = s[right],s[left]
            left+=1
            right-=1
```
