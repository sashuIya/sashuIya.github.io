```py
class Solution:
    def buildTree(self, inorder: List[int], postorder: List[int]) -> TreeNode:
      if not inorder:
        return None
      
      index_by_value = {}
      for index, value in enumerate(inorder):
        index_by_value[value] = index
        
      root = TreeNode(postorder[-1])
      
      stack = [(root, None)] # (node, min_index), below node all indexes are greater than min_index
                             # None == -oo
        
      for value in reversed(postorder[:-1]):
        new_node = TreeNode(value)
        new_node_index = index_by_value[value]
        
        node, min_index = stack[-1]
        
        if new_node_index > index_by_value[node.val]:
          node.right = new_node
          stack.append((new_node, index_by_value[node.val]))
        else:
          while stack[-1][1] is not None and new_node_index < stack[-1][1]:
            stack.pop()
          
          node, min_index = stack[-1]
          node.left = new_node
          stack.append((new_node, min_index))
      
      return root
```

## Замечания:
O(n) по памяти (hashtable + stack)
O(n) по времени (все числа обходим по примерно одному разу)
