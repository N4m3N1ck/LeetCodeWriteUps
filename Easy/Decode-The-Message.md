# Decode The Message
# Solution 1
We will format the key to follow the rules and then we will go though each character in the message and align the key with the alphabet
```python
class Solution:
    def decodeMessage(self, key: str, message: str) -> str:
        x = ""
        alphabet = "abcdefghijklmnopqrstuvwxyz"
        for i in key:
            if i not in x and i in alphabet:
                x+=i
        decode = ""
        print(x)
        for i in message:
            if i not in alphabet:
                decode += i
            else:
                decode += alphabet[x.index(i)]
        return decode
```
# Solution 2
```python
class Solution:
    def decodeMessage(self, key: str, message: str) -> str:
        dic = {' ': ' '}
        i = 0
        ans = ""
        alphabet = "abcdefghijklmnopqrstuvwxyz"
        for j in key:
            if j not in dic:
                dic[j] = alphabet[i]
                i += 1
        for j in message:
            ans += dic[j]
        return ans
```
