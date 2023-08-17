# Remove Nth Node From End Of List
We can calculate the length of the linked list and see what n is from the start. After that we will loop up to the element before n and assign next value of the element to next.next
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        if not head or not head.next:
            return None
        d = head
        length = 1
        while d.next:
            d = d.next
            length+=1
        if n==length:
            return head.next
        n = length-n+1
        p = head
        for i in range(max(0,n-2)):
           p = p.next
        p.next = p.next.next
        return head
```
