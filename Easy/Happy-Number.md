# Happy Number
We can find out if the number is happy or not by checking there are repeating results. For example let's take number 14:
14
17
50
25
29
85
**89**
145
42
20
4
16
37
58
**89**
145
42
20
4
16
37
58
**89**
We can see that there is a loop and we will always get back to 89 without reaching 0. We can create a set in which we store visited numbers and each iteration check if the number is not in visited. If it is we return False. When we reach one we return true:
```python
class Solution:
    def isHappy(self, n: int) -> bool:
        visited = set()
        while n != 1:
            m = 0
            while n>0:
                m+=(n%10)**2
                n//=10
            if m in visited:
                return False
            visited.add(m)
            n = m
        return True
```
