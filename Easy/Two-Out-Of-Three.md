# Two Out Of Three
```python
class Solution:
    def twoOutOfThree(self, nums1: List[int], nums2: List[int], nums3: List[int]) -> List[int]:
        ans = []
        nums1 = list(set(nums1))
        nums2 = list(set(nums2))
        nums3 = list(set(nums3))
        for i in nums1:
            if i in nums2 or i in nums3:
                ans.append(i)
        for i in nums2:
            if i in nums1 or i in nums3:
                ans.append(i)
        for i in nums3:
            if i in nums2 or i in nums1:
                ans.append(i)
        return list(set(ans))
```
