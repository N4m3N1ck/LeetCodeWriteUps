# Fibonacci Number
We can implement this problem recursively. The base case will be if n<=1. Otherwise return fib(n-1)+fib(n-2)
```python
class Solution:
    def fib(self, n: int) -> int:
        if n<=1: return n
        return self.fib(n-1)+self.fib(n-2)
```
We can also sovle the problem using DP
```python
class Solution:
    def fib(self, n: int):
        a,b = 0,1
        for i in range(n):
            a, b = b, a+b
        return a
```
