# Perfect Number
```python
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        x = 0
        if num == 1:
            return False
        for i in range(1,int(num**0.5)+1):
            if num%i==0:
                x += i
                x += num//i
        return num*2 == x
```
