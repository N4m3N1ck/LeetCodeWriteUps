# Convert Binary Number in a Linked List to Integer
Each new digit of the binary number we will double the amount of numbers we went through. For example 100 goes through 4 numbers: 1, 10, 11, 100. 1000 goes through 1, 10, 11, 100, 101, 110, 111, 1000. It's the same with decimal numbers, but instead of doubling we multiply by 10: 10 goes through ten numbers, 100 goes through 100 numbers etc. If the next digit of the biary number is 1 instead of zero we will double it and an extra 1.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        ans = 0
        while head: 
            ans = 2 * ans + head.val 
            head = head.next 
        return ans
```
