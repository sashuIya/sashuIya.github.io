```py
# Definition for a binary tree node.
class TreeNode(object):
  def __init__(self, x):
    self.val = x
    self.left = None
    self.right = None
```

```py
class Solution(object):
  def isValidBSTRecursive(self, node, min_value, max_value):
    if node is None:
      return True
    
    # min_value < node.val < max_value
    if min_value is not None and node.val <= min_value:
      return False
    if max_value is not None and node.val >= max_value:
      return False
    
    return (self.isValidBSTRecursive(node.left, min_value, node.val) and
           self.isValidBSTRecursive(node.right, node.val, max_value))
    
  
  def isValidBST(self, root):
    """
    :type root: TreeNode
    :rtype: bool
    """
    return self.isValidBSTRecursive(root, None, None)
```

## Замечания:
Время: `O(n)`; доп. память: `O(n)`
