# Top K Frequent Elements
We can keep the count of eafch element in the dictionary and return highest k keys in the dictionary
```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        dic = {}
        for i in nums:
            if i in dic:
                dic[i]+=1
            else:
                dic[i] = 1
        ans = []
        for i in range(k):
            maxkey = None
            for i in dic:
                if maxkey == None or dic[i] > dic[maxkey]:
                    maxkey = i
            ans.append(maxkey)
            del dic[maxkey]
            maxkey = None
        return ans
```
