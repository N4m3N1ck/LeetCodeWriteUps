# Symmetric Tree
# Recursive Solution
We can create a function check_sym() which will check if two trees are symmetric. If both roots are None, return True. If only one is None, return False. if roots have different values, we also return False. Otherwise, we compare root1.left and root2.right and root1.right and root2.left in the same way.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        def check_sym(root1,root2):
            if root1 == None and root2 == None:
                return True
            elif root1 == None or root2 == None:
                return False
            if root1.val != root2.val:
                return False
            return check_sym(root1.left,root2.right) and check_sym(root1.right,root2.left)
        return check_sym(root.left, root.right)
```
# Iterative Solution
We can create a stack which stores arrays of two values - the trees we want to compare for each step. We will take the top pair and check if both values are None, we go to the next pair in the stack. If only one value is None, we return False. If both values are equal we add two elements to the stack: [l.left,r.right], [l.right, r.left]. If values are not equal, we return False. When the stack becomes empty, we return True.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        stack = [[root.left,root.right]]
        while stack:
            cur = stack.pop()
            l = cur[0]
            r = cur[1]
            if l == None and r == None:
                continue
            if l == None or r == None:
                return False
            if l.val == r.val:
                stack.append([l.left,r.right])
                stack.append([l.right,r.left])
            else:
                return False
        return True
```
