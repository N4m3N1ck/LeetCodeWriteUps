# Valid Palindrome
There are multiple ways to solve this problem.
# Simple for loop and reverse
We can create a second string in which we will add all alpha numeric characterst converted to lowercase and check if this string is the same in reverse.
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        s2 = ""
        for i in s:
            if i.isalnum():
                s2+=i.lower()
        return s2==s2[::-1]
```
# Shorter version
class Solution:
    def isPalindrome(self, s):
        s = ''.join(e for e in s if e.isalnum()).lower()
        return s==s[::-1]
# Two pointers
We can create to pointers - left and right, if both of them are alphanumeric we can compare them, otherwise we will move the pointer to the next alphanumeric character.
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        l = 0
        r = len(s)-1
        while l<r:
            if s[l].isalnum() and s[r].isalnum():
                if s[l].lower() != s[r].lower():
                    return False
                l+=1
                r-=1
            elif not s[l].isalnum():
                l+=1
            else:
                r-=1
        return True
```
