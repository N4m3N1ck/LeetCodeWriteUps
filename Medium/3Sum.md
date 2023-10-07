# 3Sum
We can sort the array, and for each element we can solve the two sum II problem, where the left pointer is the one right to the element and the right pointer is in the end of the array. We can avoid adding same answers to ans by checking if the previous element is not the same as the current element. We can also move l and r pointers of current element when we find 3 sum until they are not the same as they were.
```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        nums.sort()
        ans = []
        for i in range(len(nums) - 2):
            if i == 0 or nums[i-1] != nums[i]:
                l = i + 1
                r = len(nums) - 1
                while l < r:
                    if nums[l] + nums[r] > -nums[i]:
                        r -= 1
                    elif nums[l] + nums[r] < -nums[i]:
                        l += 1
                    else:
                        ans.append([nums[i], nums[l], nums[r]])
                        while l < r and nums[l] == nums[l + 1]:
                            l += 1
                        while l < r and nums[r] == nums[r - 1]:
                            r -= 1
                        l += 1
                        r -= 1
        return ans
```
