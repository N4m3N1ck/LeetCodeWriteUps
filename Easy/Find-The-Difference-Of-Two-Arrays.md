```python
class Solution:
    def findDifference(self, nums1: List[int], nums2: List[int]) -> List[List[int]]:
        ar1=[]
        ar2=[]
        nums1 = set(nums1)
        nums2 = set(nums2)
        for i in nums1:
            if i not in nums2:
                ar1.append(i)
        for i in nums2:
            if i not in nums1:
                ar2.append(i)
        return [ar1, ar2]
```
