# Merge Sorted Array
We can have to pointers which will point at the current max value of each array. We will pick the biggest one and move it to left. We will repeat the process while both pointers are more than 0. If m is more than zero then we don't have to do anything else. But if n is more than zero it means that we haven't added some items from m yet. We can replace first n items of the nums1 array to first n numbers of nums2 array
```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        while m > 0 and n > 0:
            if nums1[m-1] > nums2[n-1]:
                nums1[m+n-1] = nums1[m-1]
                m -= 1
            else:
                nums1[m+n-1] = nums2[n-1]
                n -= 1
        if n > 0:
            nums1[:n] = nums2[:n]
```
