# Count The Digits That Divide A Number
We can store a copy of num, and go through each digits in x and check if num is divisible by it. 
```python
class Solution:
    def countDigits(self, num: int) -> int:
        x = num
        n = 0
        while x!=0:
            if num%(x%10)==0:
                n+=1
            x//=10
        return n
```
