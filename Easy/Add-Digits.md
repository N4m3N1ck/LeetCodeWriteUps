# Add Digits
There are multiple ways to approach the problem
# Recursive
We can solve this problem recursively. The base case is when num<10 we will return num. Otherwise we will find the sum of the digits of num (x) by adding num%10 to x and applying whole division to num while num is more than zero. We will calculate addDigits of x
```python
class Solution:
    def addDigits(self, num: int) -> int:
        if num < 10:
            return num
        x = 0
        while num>0:
            x+=num%10
            num//=10
        return self.addDigits(x)
```
# O(1)
If we check the output for some numbers we can notice a pattern:

1 1,
2 2,
3 3,
4 4,
5 5,
6 6,
7 7,
8 8,
9 9,
10 1,
11 2,
12 3,
13 4,
14 5,
15 6,
16 7,
17 8,
18 9,
19 1,
20 2,
21 3,
22 4,
23 5,
24 6,
25 7,
26 8,
27 9,
28 1,
29 2,
30 3,
31 4,
32 5,
33 6,
34 7,
35 8,
36 9,
37 1,
38 2,
39 3,
40 4,
41 5,
42 6,
43 7,
44 8,
45 9,
46 1,
47 2,
48 3,
49 4,
Every ninth number has the same output: d(39) = d(30) = d(21) = d(12) = d(3) = 3. Why? Because every time we subtract(add) nine from a number lets say xy (x and y are digits) we will get a number in which x is one less(more) and y is one more(less) than it was, so the total sum of the digits will not change.
```python
class Solution:
    def addDigits(self, num: int) -> int:
        if num==0: 
            return 0
        return 1 + (num - 1) % 9;
```
What this code does i that it checks if number is zero and returns zero if it is the case. If it isn't we return 1 + (num - 1) % 9. This is almost equal num%9 except when num is equal to 9. When num is not nine it is the same as calculating num%9 and getting value out of this sequence: [0,1,2,3,4,5,6,7,8,9]. But we dont want to return zero for num=9, which can be fixed by subtracting one away from num which returns the remainder shifted to left by one. And then we add one to the result and get the answer.
