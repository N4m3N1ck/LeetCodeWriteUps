# Last Visited Integer
```python
class Solution:
    def lastVisitedIntegers(self, words: List[str]) -> List[int]:
        nums = []
        cur_last = 1
        ans = []
        for i in words:
            if i != "prev":
                nums.append(int(i))
                cur_last = 1
            else:
                if cur_last <= len(nums):
                    ans.append(nums[-cur_last])
                else:
                    ans.append(-1)
                cur_last += 1
        return ans
```
