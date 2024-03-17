# Contiguous Array
```python
class Solution:
    def findMaxLength(self, nums: List[int]) -> int:
        answer = 0
        hashmap = {0:0}
        count = 0
        for i in range(1, len(nums) + 1):
            if nums[i - 1] == 1:
                count += 1
            else:
                count -= 1
            if count in hashmap:
                if i - hashmap[count] > answer:
                    answer = i - hashmap[count]
            else:
                hashmap[count] = i
        return answer
```
