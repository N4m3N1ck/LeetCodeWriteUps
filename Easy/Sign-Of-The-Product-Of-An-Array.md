# Sign Of The Product Of An Array
If the arraay contains zero, than the product will also be zero. Otherwise, we can count the amount of negative numbers. If the amount of negative numbers is divisible by 2, the number is positive, otherwise the number is negative
```python
class Solution:
    def arraySign(self, nums: List[int]) -> int:
        if 0 in nums:
            return 0
        neg = 0
        for i in nums:
            if i < 0:
                neg+=1
        if neg%2==0:
            return 1
        return -1
```
