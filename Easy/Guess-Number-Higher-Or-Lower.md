# Guess Number Higher Or Lower
Simple Binary Search Problem. <br>
Two pointers: left and right. On each step we will find the middle item. If it's larger, we will set the right value to middle - 1, if it's lower we will set the left value to middle + 1, otherwise return middle.
```python
# The guess API is already defined for you.
# @param num, your guess
# @return -1 if num is higher than the picked number
#          1 if num is lower than the picked number
#          otherwise return 0
# def guess(num: int) -> int:

class Solution:
    def guessNumber(self, n: int) -> int:
        l = 0
        r = n
        while True:
            m = (l + r) // 2
            g = guess(m)
            if g == 0:
                return m
            elif g == -1:
                r = m - 1
            else:
                l = m + 1

```
