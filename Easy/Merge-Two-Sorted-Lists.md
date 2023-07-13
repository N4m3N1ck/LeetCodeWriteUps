# Merge Two Sorted Lists
## Explanation
We could solve the problem by repeating few simple steps:
1. Create two variables: cur_1, cur_2 which will store current element of each list
2. Compare them and add the smallest value to the third list. Replace the smallest value with next element in the list
## Example
Let's say we have to lists: [1,2,4] and [1,3,4]
1. cur_1 = 1, cur_2 = 1, smallest = 1. We will add cur_1 to the new list: [1]
2. cur_1 = 2, cur_2 = 1, smallest = 1. We will add cur_2 to the list [1, 1]
3. cur_1 = 2, cur_2 = 3, smallest = 2. We will add cur_1 to the list [1,1,2]
4. cur_1 = 4, cur_2 = 3, smallest = 3. We will add cur_2 to the list [1,1,2,3]
5. cur_1 = 4, cur_2 = 4, smallest = 4. We will add cur_1 to the list [1,1,2,3,4]
6. cur_1 = None, cur_2 = 4, cur_1 is None so we add cur_2 to the list [1,1,2,3,4,4]
7. cur_1 = None, cur_2 = None, both variables are None so we return our list.
## Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        list3 = cur = ListNode()
        while list1 or list2:
            if list1 == None:
                cur.next = list2
                list2 = list2.next
            elif list2 == None:
                cur.next = list1
                list1 = list1.next
            elif list1.val <= list2.val:
                cur.next = list1
                list1 = list1.next
            else:
                cur.next = list2
                list2 = list2.next
            cur = cur.next
        return list3.next
```
Note: We return list3.next instead of list3 because it will always start with item 0. 
