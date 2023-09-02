```python
class Solution:
    def separateDigits(self, nums: List[int]) -> List[int]:
        d=[]
        for i in nums:
            x=[]
            while i!=0:
                x.append(i%10)
                i//=10
            d+=x[::-1]
        return d
```
