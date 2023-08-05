# Left And Right Sum Differences
We can create left_sum and right_sum. We can set right_sum to the sum of the entire array. On each iteration we can subtract current item from the right_sum, because it doesnt belong there. After we calculate the differnce, we can add current item to left_sum, because it belongs there
```python
class Solution:
    def leftRightDifference(self, nums: List[int]) -> List[int]:
        left_sum = 0
        right_sum = sum(nums)
        s=[]
        for i in nums:
            right_sum -= i
            s.append(abs(left_sum-right_sum))
            left_sum+=i
        return s
```
