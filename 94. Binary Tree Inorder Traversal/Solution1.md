Question: https://leetcode.com/problems/binary-tree-inorder-traversal/description/
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        output = []
        def inorder(list):
            if not list:
                return []
            inorder(list.left)
            output.append(list.val)
            inorder(list.right)
        
        inorder(root)
        return output
```
