# Reverse Words In A String
Just convert the string to list by splitting by space, reverse it and add elements to a return string.
```python
class Solution:
    def reverseWords(self, s: str) -> str:
        ar = s.split()
        ans = " ".join(ar[::-1])
        return ans
````
