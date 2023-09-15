# Add Two Numbers
Luckily, the linked lists are already reversed, so adding will be easier. We will create a linked list for sum and a pointer to that linked list. We will go though each corresponding element of the linked lists and add them together plus carry. If there is carry left in the end with no other elements, we will add to the sum linked list.
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        sum_list = ListNode()
        ptr = sum_list
        current_l1_node = l1
        current_l2_node = l2
        carry = 0
        while current_l1_node or current_l2_node or carry:
            val1 = 0
            val2 = 0
            if current_l1_node:
                val1 = current_l1_node.val
                current_l1_node = current_l1_node.next
            if current_l2_node:
                val2 = current_l2_node.val
                current_l2_node = current_l2_node.next
            s = val1 + val2 + carry
            carry = s // 10
            s = s % 10
            ptr.next = ListNode(s)
            ptr = ptr.next
        return sum_list.next
```
