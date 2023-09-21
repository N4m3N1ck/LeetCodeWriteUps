# Count Complete Tree Nodes
Just count all the nodes in the tree
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def countNodes(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        stack = [root]
        count = 0
        while stack:
            cur = stack.pop()
            count += 1
            if cur.left:
                stack.append(cur.left)
            if cur.right:
                stack.append(cur.right)
        return count
```
