# Subarray Sum Equals K
```python
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        answer = 0
        prefix_sum = {0:1}
        cur_sum = 0
        for i in nums:
            cur_sum += i
            prefix_required = cur_sum - k
            if prefix_required in prefix_sum and prefix_sum[prefix_required] > 0:
                answer += prefix_sum[prefix_required]
            if cur_sum in prefix_sum:
                prefix_sum[cur_sum] += 1
            else:
                prefix_sum[cur_sum] = 1
        return answer
```
