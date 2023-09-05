# Recursive
```python
"""
# Definition for a Node.
class Node:
    def __init__(self, val=None, children=None):
        self.val = val
        self.children = children
"""

class Solution:
    def maxDepth(self, root: 'Node') -> int:
        if root == None:
            return 0
        max_d = 0
        for i in root.children:
            d = self.maxDepth(i)
            if d > max_d:
                max_d = d
        return max_d + 1
```
