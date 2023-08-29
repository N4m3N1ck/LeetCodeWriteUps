# Nim Game
We can prove that if n is 4, first player will lose. We can prove that for numbers like 5,6 and 7 player 1 will win, because they can make 4 out of these numbers and become the second player. We can prove that for number 8 player 1 will be forced to give the winning position to player 2. Etc.
```python
class Solution:
    def canWinNim(self, n: int) -> bool:
        return n%4!=0
```
