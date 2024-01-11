# Maximum Difference Between Node And Ancestor
We will use iterative DFS to pass through the nodes, each element in the stack will be a tuple with three values: cur, smallest ancestor value, largest ancestor value. For each cur we will check the max difference and if it is bigger than the answer, we will update it.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxAncestorDiff(self, root: Optional[TreeNode]) -> int:
        if root == None:
            return 0
        ans = 0
        stack = [(root,root.val,root.val)]
        while stack:
            cur = stack.pop()
            m_diff = max(abs(cur[0].val - cur[1]), abs(cur[0].val - cur[2]))
            if m_diff > ans:
                ans = m_diff
            if cur[0].left:
                stack.append((cur[0].left,min(cur[1],cur[0].val),max(cur[2],cur[0].val)))
            if cur[0].right:
                stack.append((cur[0].right,min(cur[1],cur[0].val),max(cur[2],cur[0].val)))
        return ans
```
