# Fizz Buzz
This problem is extremely simple. We can loop throuch each number up to n and check it's divisibility by 3 and by 5.
```python
class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        ar = []
        for i in range(n):
            if (i+1)%3==0 and (i+1)%5==0:
                ar.append("FizzBuzz")
            elif (i+1)%3==0:
                ar.append("Fizz")
            elif (i+1)%5==0:
                ar.append("Buzz")
            else:
                ar.append(str(i+1))
        return ar
```
