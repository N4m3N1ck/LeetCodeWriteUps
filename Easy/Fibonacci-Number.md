# Fibonacci Number
We can implement this problem recursively. The base case will be if n<=1. Otherwise return fib(n-1)+fib(n-2)
```python
class Solution:
    def fib(self, n: int) -> int:
        if n<=1: return n
        return self.fib(n-1)+self.fib(n-2)
```
