# Remove Nth Node From End Of List
# Solution 1
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
# Solution 2: One Pass
We can create two pointers: slow and fast. We can move the fast pointer n times forward to offset the slow and the fast pointers by n. After that we can move both pointers forward until fast.next exists. The slow.next element will be the one we want to remove. So we can say slow.next = slow.next.next. The only issue is if fast equals None because of the first for loop. This means that n is equal to the length of linked list and we will remove the first element by returning head.next
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
        slow,fast = head,head
        for i in range(n):
            fast = fast.next
        if fast == None:
            return head.next
        while fast.next:
            fast = fast.next
            slow = slow.next
        slow.next = slow.next.next
        return head
``
