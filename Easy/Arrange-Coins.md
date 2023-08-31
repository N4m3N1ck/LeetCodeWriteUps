```python
class Solution:
    def arrangeCoins(self, n: int) -> int:
        #n=x*(x+1)/2
        #x^2+x = 2n
        #x^2+x-2n=0 - Solve
        # D = 1 + 8n
        # x = (sqrt(1+8n)-1)/2
        return (int((1+8*n)**0.5)-1)//2
```
