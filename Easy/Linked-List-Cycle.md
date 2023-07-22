# Linked List Cycle
To solve the problem we can implement tortoise and hare algorithm: https://en.wikipedia.org/wiki/Cycle_detection#Tortoise_and_hare
We can create to pointers: slow and fast and every iteration until the pointers meet assign slow to slow.next and fast to fast.next.next. If they meet we return True, but if there is an error beacuse there is no fast.next.next pointer, it means there is no loop and linked list has an end. The slow and the fast pointer will meet because each iteration the fast pointer will get one step closer to the slow pointer from behind.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        if not head:
            return False
        slow = head
        fast = head.next
        try:
            while slow!=fast:
                slow = slow.next
                fast = fast.next.next
            return True
        except:
            return False
```
