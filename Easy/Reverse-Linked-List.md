# Reverse Linked List
We can create a **prev** pointer which will initially point at null and we can create **cur** pointer which will point at head. We can create pointer **nxt** for cur.next as well. Then, we will repeat this process: cur.next = prev, prev = cur, cur = nxt. Basically we assignthe previous node to the current node and then we go on to the next node to repeat the process.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        cur = head
        while cur:
            nxt = cur.next
            cur.next = prev
            prev = cur
            cur = nxt
        return prev
```
