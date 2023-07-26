# N-th Tribonacci number
We can solve the problem using a for loop:
```python
class Solution:
    def tribonacci(self, n):
        if n==0:
            return 0
        a, b, c = 0, 1, 1
        for i in range(n-2): 
            a, b, c = b, c, a + b + c
        return c
```
