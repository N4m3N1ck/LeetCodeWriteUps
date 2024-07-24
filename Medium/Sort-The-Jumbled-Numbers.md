# Sort The Jumbled Numbers
```python
class Solution:
    def sortJumbled(self, mapping: List[int], nums: List[int]) -> List[int]:
        dic = {}
        for i in nums:
            x = 0
            c = i
            d = 1
            if c == 0:
                x = mapping[0]
            while c:
                x += mapping[(c % 10)] * 10 ** (d - 1)
                c //= 10
                d += 1
            dic[i] = x
        print(dic)
        return sorted(nums, key=lambda x: dic[x])
```
