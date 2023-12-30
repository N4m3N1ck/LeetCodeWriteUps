# Palindrome Linked List
Add first half of the list to the stack, and pop the last value if it's equal to the next value of the second half.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        stack = []
        length = 0
        cur = head
        while cur:
            cur = cur.next
            length += 1
        ptr1 = head
        for i in range(length//2):
            stack.append(ptr1.val)
            ptr1 = ptr1.next
        if length % 2 != 0:
            ptr1 = ptr1.next
        while ptr1 and stack:
            if stack[-1] == ptr1.val:
                stack.pop()
                ptr1 = ptr1.next
            else:
                return False
        return not stack
```
