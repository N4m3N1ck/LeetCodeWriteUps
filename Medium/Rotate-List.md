# Rotate List
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if head == None or head.next == None:
            return head
        # Identify the length of the linked list
        ptr = head
        length = 1
        while ptr.next:
            ptr = ptr.next
            length += 1
        # Reduce k
        k = k % length
        if k == 0:
            return head
        # Identify k's node from the end
        slow = head
        fast = head
        for i in range(k - 1):
            fast = fast.next
        while fast.next:
            fast = fast.next
            slow = slow.next
        # Remove last k elements from head
        ptr2 = head
        for i in range(length-k-1):
            ptr2 = ptr2.next
        ptr2.next = None
        # Add slow and head together
        ptr3 = slow
        while ptr3.next:
            ptr3 = ptr3.next
        ptr3.next = head
        return slow
```
