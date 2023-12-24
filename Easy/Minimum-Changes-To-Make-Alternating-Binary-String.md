# Minimum Changes To Make Alternating Binary String
There are only two possible answers to any input:\
Let's say the length of input is 10. The possible correct strings are:\
"1010101010",\
"0101010101"\
The string must have all even and all odd indexes the same. We will create two variables to store the amount of changes we have to make to get to one of those cases: count_0 and count_1.\
count_0 represents the amount of changes if 0 is at even indexes.\
count_1 represents the amount of changes if 1 is at even indexes.\
We will loop through each index, check it's parity and value. According to the value we will check if we need to swap it for each of the above cases and change the value of count_0 and count_1 correspondingly.
```python
class Solution:
    def minOperations(self, s: str) -> int:
        count_0 = 0
        count_1 = 0
        for i in range(len(s)):
            if i % 2 == 0:
                if s[i] == "0":
                    count_1 += 1
                else:
                    count_0 += 1
            else:
                if s[i] == "1":
                    count_1 += 1
                else:
                    count_0 += 1
        return min(count_0, count_1)
```
