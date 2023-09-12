# Check if Word Equals Summation of Two Words
```python
class Solution:
    def isSumEqual(self, firstWord: str, secondWord: str, targetWord: str) -> bool:
        x = ""
        for i in firstWord:
            x += str(ord(i)-97)
        y = ""
        for i in secondWord:
            y += str(ord(i)-97)
        z = ""
        for i in targetWord:
            z += str(ord(i)-97)
        return int(x)+int(y) == int(z)
```
