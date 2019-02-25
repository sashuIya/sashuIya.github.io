## Решение:
Найдем длину цикла `K`. Затем, заведем два указателя. Один поставим на начало списка, а второй двинем `K` раз. 
После этого, будем двигать оба указателя на 1 элемент, пока они не совпадут. 
А произойдет это ровно тогда, когда первый указатель шагнет на первый элемент цикла.  

## Код:
```py
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

def countElementsInCycle(head):
  if head == None: return None

  current = head
  steps = 1

  cycle_length = 0
  while True:
    next_node = current

    for step in range(steps):
      if next_node.next == None:
        return None # no cycle
      
      next_node = next_node.next
      if next_node == current:
        return step + 1 # if step == 0, there is 1 element in cycle

    current = next_node
    steps *= 2


class Solution(object):
  def detectCycle(self, head):
    """
    :type head: ListNode
    :rtype: ListNode
    """
    if head == None: return None
    
    elements_in_cycle_num = countElementsInCycle(head)
    if not elements_in_cycle_num: return None # no cycle
    
    p1 = head
    p2 = head
    
    # Move p2 by elements_in_cycle_num forward.
    for step in range(elements_in_cycle_num):
      p2 = p2.next
    
    # Move p1 and p2 by 1 element each time and compare.
    # Once p1 passes pre-cycle, p1 and p2 will point to the same element.
    while p1 != p2:
      p1 = p1.next
      p2 = p2.next
    return p1
```

## Замечания:
* Асимптотика по времени - `O(n)` (по каждому элементу списка мы шагнем не более 2 раз). Асимптотика по доп. памяти - `O(1)`.
