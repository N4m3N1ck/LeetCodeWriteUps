# Roman To Integer
  Here is the best way to solve the problem:
```python
class Solution:
    def romanToInt(self, s: str) -> int:
        nums = {
            "I": 1,
            "V": 5,
            "X": 10,
            "L": 50,
            "C": 100,
            "D": 500,
            "M": 1000
            }
        x = 0
        for i in range(len(s)):
            if i != len(s)-1:
                if nums[s[i]]>=nums[s[i+1]]:
                    x+=nums[s[i]]
                else:
                    x-=nums[s[i]]
        x += nums[s[-1]]
        return x
```
We can store each letter in a dictionary to represent it with the corresponding number. We can then loop through each element in the string and add its value to the result if the next element is smaller or subtract if the next element is larger than the current element
