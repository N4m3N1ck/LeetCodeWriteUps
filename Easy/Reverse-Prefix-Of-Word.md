```python
class Solution:
    def reversePrefix(self, word: str, ch: str) -> str:
        if ch not in word:
            return word
        ch_ind=0
        while word[ch_ind]!=ch:
            ch_ind+=1
        return word[:ch_ind+1][::-1]+word[ch_ind+1:]
```
