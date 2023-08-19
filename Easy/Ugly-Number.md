# Ugly Number
We can easily solve the problem by dividing the number by 2 3 and 5 while we can and checking if the number is equal to one in the end.
```python
class Solution:
    def isUgly(self, n: int) -> bool:
        if n==0:
            return False
        while n%2==0:
            n//=2
        while n%3==0:
            n//=3
        while n%5==0:
            n//=5
        return n==1
```
