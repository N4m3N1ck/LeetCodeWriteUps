# Pascal's Triangle
We can solve this problem using DP. The first item will be [1] - the base of the triangle. We can create the next item by creating two pointers l and r. We will add those pointers on each step to find current element of dp[i]. This pointers represent items above dp[i]. If the pointer is out of bounds it's zero
```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        dp = [None]*numRows
        dp[0] = [1]
        for i in range(1,numRows):
            l = -1
            r = 0
            dp[i] = []
            while l<len(dp[i-1]):
                if l==-1:
                    dp[i].append(dp[i-1][r])
                elif r == len(dp[i-1]):
                    dp[i].append(dp[i-1][l])
                else:
                    dp[i].append(dp[i-1][r]+dp[i-1][l])
                l+=1
                r+=1
        return dp
```
