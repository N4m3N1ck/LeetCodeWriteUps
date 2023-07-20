# Invert Binary Tree
There are multiple ways to approach this problem:
# Recursive
We can swap the children of each node and then swap the children of the children etc.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root == None:
            return None
        root.left, root.right = self.invertTree(root.right), self.invertTree(root.left)
        return root
```
# Depth First Search
We can create a stack to implement DFS traversal and swap children of each node we visit.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root == None:
            return None
        stack = [root]
        cur_root = root
        while len(stack) > 0:
            cur_root = stack.pop()
            cur_root.right, cur_root.left = cur_root.left, cur_root.right
            if(cur_root.right != None): stack.append(cur_root.right)
            if(cur_root.left != None): stack.append(cur_root.left)

        return root
```
