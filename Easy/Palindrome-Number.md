# Palindrome Number
  There are multiple ways to approach the problem
## Easy way
  The easiest way to do it is to convert the number into a string and check if the reversed string is equal to the original string:
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        return str(x) == str(x)[::-1]
```
## Algorithmic way
  We can check if the first half of the number is equal to the second half of the number reversed. For example 123321, 123|321, 123=123.
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if 0<=x<10:
            return True
        if x % 10==0 or x<0:
            return False
        y = 0
        while y < x:
            y *= 10
            y += x % 10
            x //= 10
        return y == x or y // 10 == x
```
  Firstly we check if x is a digit and return True. Then we check if x ends with a zero or is a negative number and return False. Then we need to calculate the reverse of the last half of the number. We can do so by multiplying the number by ten and adding the last digit of x. We will then use // to divide x by 10. we will do it while the second half of the number is less than the first half. We can than check if x==y or if the number has an odd amount of digits x==y//10 not to include the number in the middle
