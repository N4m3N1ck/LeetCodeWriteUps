# Add Strings
# Solution 1 - Slow
Here is a very simple but relatively slow solution. <br>
We can add zeroes to the start of the numbers to make them the sama length. Then we can add digits one by one in reverse order and add carry as well. We return the reverse of sum.
```python
class Solution:
    def addStrings(self, num1: str, num2: str) -> str:
        s = ""
        while len(num1)<len(num2):
            num1 = "0"+num1
        while len(num2)<len(num1):
            num2 = "0"+num2
        carry = 0
        print(num1,num2)
        for i in range(len(num1)):
            j = len(num1)-1-i
            x = int(num1[j])+int(num2[j])+carry
            s += str(x%10)
            carry = x//10
        if carry > 0:
            s+= str(carry)
        return s[::-1]
```
