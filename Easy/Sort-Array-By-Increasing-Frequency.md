```python
class Solution:
    def frequencySort(self, nums: List[int]) -> List[int]:
        dic = Counter(nums)
        return sorted(nums, key = lambda x: (dic[x],-x))
```
