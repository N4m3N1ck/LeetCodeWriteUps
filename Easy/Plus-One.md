# Plus One
We can loop through each element in the list from the end and while the element is nine we replace it with zero and add one to the first element not equal to nine. If all elements are nine we add one to the start of the array
```python
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        length = len(digits) - 1
        while digits[length] == 9:
            digits[length] = 0
            length -= 1
        if(length < 0):
            digits = [1] + digits
        else:
            digits[length] += 1
        return digits
```
