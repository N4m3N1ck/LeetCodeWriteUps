# Even Odd Tree
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isEvenOddTree(self, root: Optional[TreeNode]) -> bool:
        queue = [(root, 0)]
        prev = None
        while queue:
            cur = queue.pop(0)
            if cur[0].val % 2 == cur[1] % 2:
                return False
            if prev and prev[1] == cur[1]:
                if prev[0].val >= cur[0].val and cur[1] % 2 == 0:
                    return False
                if prev[0].val <= cur[0].val and cur[1] % 2 == 1:
                    return False
            if cur[0].left:
                queue.append((cur[0].left, cur[1] + 1))
            if cur[0].right:
                queue.append((cur[0].right, cur[1] + 1))
            prev = cur
            
        return True
```
