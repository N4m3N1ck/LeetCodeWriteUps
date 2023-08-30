# Middle Of The Linked List
We can solve the problem by creating two pointers: slow and fast. The fast pointer will be moving twice faster than the slow pointer, so when fast reaches the nth node(n is the length of the list) slow will reach n/2 node.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        fast, slow = head, head
        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next
        return slow
```
