# Add Strings
We can reverse both numbers and add zeroes to the end of the shortest number. We can then loop through the number and add sum of digits + carry to sum_s. We return reversed sum_s
```python
class Solution:
    def addStrings(self, num1: str, num2: str) -> str:
        num1 = num1[::-1] + "0" * max(0, len(num2) - len(num1))
        num2 = num2[::-1] + "0" * max(0, len(num1) - len(num2))
        sum_s = ""
        carry = 0
        for i in range(len(num1)):
            s = int(num1[i]) + int(num2[i]) + carry
            sum_s += str(s%10)
            carry = s//10
        if carry > 0:
            sum_s += str(carry)
        return sum_s[::-1]
```
