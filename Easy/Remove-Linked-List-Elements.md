# Remove Linked List Elements
This was my first solution to the problem which somehow is faster than 100% of solutions:
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        while head and head.val == val:
            head = head.next
        pointer = head
        while pointer and pointer.next:
            while pointer.next and pointer.next.val == val:
                pointer.next = pointer.next.next
            pointer = pointer.next
        return head
```
Firstly I will change head to head.next while head.val == val. After that I will create a pointer which will check if the next element.val is equal to val and assign pointer.next to pointer.next.next. Then the pointer will be moved forward. When we reach the end of the list we return head.
A better solution would be this to remove the first while loop:
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        prev = ListNode(-1)
        prev.next = head
        pointer = prev
        while pointer and pointer.next:
            if pointer.next.val == val:
                pointer.next = pointer.next.next
            else:
                pointer = pointer.next
        return prev.next
```
