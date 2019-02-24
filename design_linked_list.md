```py
class Node(object):
  
  def __init__(self, value):
    self.val = value
    self.next = None

    
class MyLinkedList(object):
  
  def __init__(self):
    """
    Initialize your data structure here.
    """
    self.head = None
    self.tail = None
    self.size = 0

  def get(self, index):
    """
    Get the value of the index-th node in the linked list.
    If the index is invalid, return -1.
    :type index: int
    :rtype: int
    """
    if index >= self.size: return -1

    current = self.head
    for i in range(index):
      current = current.next
      
    return current.val


  def addAtHead(self, val):
    """
    Add a node of value val before the first element of the linked list.
    After the insertion, the new node will be the first node of the linked list.
    :type val: int
    :rtype: None
    """
    new_node = Node(val)
    new_node.next = self.head
    self.head = new_node
    self.size += 1
    
    # If this is the only element in the list - update the tail.
    if self.size == 1:
      self.tail = new_node  

    
  def addAtTail(self, val):
    """
    Append a node of value val to the last element of the linked list.
    :type val: int
    :rtype: None
    """
    new_node = Node(val)
    if self.size > 0:
      self.tail.next = new_node
    self.tail = new_node
    self.size += 1
    
    #if this is the only element in the list - update the head.
    if self.size == 1:
      self.head = new_node


  def addAtIndex(self, index, val):
    """
    Add a node of value val before the index-th node in the linked list.
    If index equals to the length of linked list, the node will be appended
    to the end of linked list. If index is greater than the length, the
    node will not be inserted.
    :type index: int
    :type val: int
    :rtype: None
    """
    if index > self.size:
      return
    
    if index == 0:
      self.addAtHead(val)
      return
    if index == self.size:
      self.addAtTail(val)
      return
    
    current = self.head
    for i in range(index - 1):
      current = current.next
    
    new_node = Node(val)
    new_node.next = current.next
    current.next = new_node
    self.size += 1

    
  def deleteAtIndex(self, index):
    """
    Delete the index-th node in the linked list, if the index is valid.
    :type index: int
    :rtype: None
    """
    if index >= self.size:
      return
    
    if index == 0:
      self.head = self.head.next
    else:
      current = self.head
      for i in range(index - 1):
        current = current.next
      current.next = current.next.next
    
    if index == self.size - 1:
      self.tail = current

    self.size -= 1
    
    if self.size == 0:
      self.tail = None

    
# Your MyLinkedList object will be instantiated and called as such:
# obj = MyLinkedList()
# param_1 = obj.get(index)
# obj.addAtHead(val)
# obj.addAtTail(val)
# obj.addAtIndex(index,val)
# obj.deleteAtIndex(index)
```

## Замечания:
1. Важно следить за `head` и `tail`. Они могут менятся одновременно, когда список пустой (или становится пустым).
2. Важно делать присваивания указателей в правильном порядке.
