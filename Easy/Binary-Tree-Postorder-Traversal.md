# Binary Tree Postorder Traversal
This is similar to the previous traversals, but we add left nodes first, then we add right nodes and only after that we add the current node to ans.
# Recursive
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        ans = []
        def traversal(root):
            if not root:
                return
            traversal(root.left)
            traversal(root.right)
            ans.append(root.val)
        traversal(root)
        return ans
```
