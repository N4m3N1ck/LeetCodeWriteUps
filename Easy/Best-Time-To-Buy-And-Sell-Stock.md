# Best Time To Buy And Sell Stock
This was my first solution to the problem:
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_v = 0
        res = [0]*len(prices)
        for i in range(1,len(prices)):
            res[i] = max(0,res[i-1]+prices[i]-prices[i-1])
            if res[i]>max_v:
                max_v = res[i]
        return max_v
```
We create an array of max profit calculated for each day. It is calculated by firstly assigning 0 to the first element, then calculating each next number's max value by finding the difference between the two numbers and checking if it's positive. If it's negative we return 0.
