## Здравствуйте, товарищи!

Я постараюсь пройтись по основным темам/задачам и в коротких видео предоставить необходимый теоретический материал, советы по написанию кода и важные, на мой взгляд, замечания, чтобы вы могли уверенно и успешно проходить такого рода интервью.

### 0. Friendly SWE Guide Manifesto
* У меня есть [документ](https://quip.com/A6azAP9ze7DM), в котором я собираю дельные советы начинающим программистам. Там про настройку рабочей среды и всего такого. Иногда добавляю туда что-то новенькое. Комментарии приветствуются.

### 1. Бинарный поиск
<table>
<tr VALIGN=top>
<td style="width: 40%">

* Теория: https://youtu.be/fZ9VKq8ybq4
* Практика: https://leetcode.com/problems/binary-search
* [Код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/binsearch.md)

</td>
<td>

```cpp
int search(const vector<int>& nums, int target) {
  if (nums.empty()) return -1;

  int l = 0;
  int r = nums.size(); // element after the last!!

  while (l + 1 < r) {
    int m = (l + r) / 2;
    if (a[m] > target) {
      r = m;
    } else {
      l = m;
    }
  }

  return nums[l] == target ? l : -1;
}
```

</td>
</tr>
</table>

### 2. Быстрое возведение в степень
* [видео-разбор](https://youtu.be/swktXq5COtI)
* [leetcode: быстрое возведение в степень](https://leetcode.com/problems/powx-n)

### 3. Задача о кузнечике
Простейшая одномерная динамика. Два красивых математических решения с использованием быстрого возведения в степень.
* [видео-разбор](https://youtu.be/qoo_P3nbfic)
* [leetcode: задачка о кузнечике](https://leetcode.com/problems/climbing-stairs)

### 4. Задача о водопаде
Простая задачка на смекалку. Довольно сумбурный разбор - придется смотреть в собранном состоянии.
* [видео-разбор](https://youtu.be/4ntW5KknHPQ)
* [leetcode: задача о водопаде 1D](https://leetcode.com/problems/trapping-rain-water)
  * [пишем код онлайн](https://youtu.be/lXPKZSUJb94)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/trapping_rain_water.md)

### 5. Тупые задачки (на владение языком)
* [Проверка, что строка - IP адрес](https://youtu.be/Mch6evN0Zmk)

### 6. Список (структура данных)
* [видео по общей теории](https://youtu.be/MGkDPkQMSR4)
* [leetcode: имплементация односвязного списка](https://leetcode.com/problems/design-linked-list)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/design_linked_list.md)
* [leetcode: переворот односвязного списка](https://leetcode.com/problems/reverse-linked-list)
  * [пишем код онлайн (рекурсивный способ)](https://youtu.be/fS7MkpRwbZs)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/reverse_linked_list.md)
* [leetcode: есть ли цикл в списке?](https://leetcode.com/problems/linked-list-cycle)
  * [пишем код онлайн](https://youtu.be/Hcapz3ixZmQ)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/linked_list_cycle.md)
* [leetcode: первый элемент в цикле (первый после прецикла)](https://leetcode.com/problems/linked-list-cycle-ii/)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/linked_list_cycle_ii.md)
* [leetcode: слияние двух отсортированных списков](https://leetcode.com/problems/merge-two-sorted-lists)
  * [пишем код онлайн](https://youtu.be/UiMNCXxqNpM)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/merge_two_sorted_lists.md)

### 7. Массив
* [видео по общей теории](https://youtu.be/KAuwhdYrN-8)
* [leetcode: нахождение общих элементов двух массивов](https://youtu.be/PIJJswU3B2U)
  * [код и замечания](https://github.com/sashuIya/leetcode_solutions/blob/master/350.intersection-of-two-arrays-ii.py)
* k-ая порядковая статистика
  * [видео-разбор](https://www.youtube.com/watch?v=gK9r5bGG604)
  * [задача на leetcode](https://leetcode.com/problems/kth-largest-element-in-an-array/)

### 8. Перебор (backtracking)
* [видео с простейшим примером](https://youtu.be/UtUpDFwyiiQ)
* [видео с простейшим примером перебора на графе](https://youtu.be/KIDSVOjVDrg)

### 9. Бинарное дерево
<table>
<tr VALIGN=top>
<td style="width: 40%">

* [видео по общей теории](https://youtu.be/2N4j4Jiy5Ac)
* [leetcode: является ли дерево деревом поиска](https://leetcode.com/problems/validate-binary-search-tree/)
  * [разбор и код онлайн](https://youtu.be/bZ6Dpoe9Ycc)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/is_bst.md)
* [(домашка) leetcode: наименьшая разница между значениями в BST](https://leetcode.com/problems/minimum-distance-between-bst-nodes/)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/min_diff_in_bst.md)
* [(домашка) leetcode: найти значение в BST](https://leetcode.com/problems/search-in-a-binary-search-tree/)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/find_value_in_bst.md)
* [задачка про наименьшего общего предка (LCA) без предподсчета](https://www.youtube.com/watch?v=hiR6NlDn0zo)
  * [ссылка на эту задачу на leetcode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)
  * [ссылка на домашку](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)
* [видео по десериализации бин. дерева](https://www.youtube.com/watch?v=G8BuzXMfdKQ)
  * [leetcode: десериализация по inorder и postorder](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/in_and_post_orders_deserialization.md)

</td>
<td>

```python
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

</td>
</tr>
</table>

### 10. Бор
* [видео с базовой теорией](https://youtu.be/-eDAuPu7bkM)

### 11. Графы
* [определение и примеры](https://youtu.be/HJcryz9xb9w)
* [методы представления графов, часть 1](https://youtu.be/MGhvKGTXWpc)

### 12. Комбинаторика
* [leetcode-разбор: next permuation (с кодом)](https://youtu.be/pgaf6W7XFuU)

### 13. Два указателя
* [leetcode-разбор: Minimum Window Substring (с кодом)](https://youtu.be/-HxxzBTtLqk)
* [leetcode: поиск двух элементов массива с данной суммой](https://youtu.be/7Cwl5PSS-Nc)
  * [код и замечания](https://github.com/sashuIya/sashuIya.github.io/blob/master/solutions/two_sum_array.md)

### 14. Динамическое программирование
* [leetcode видео-разбор: Stock Price (с кодом)](https://youtu.be/fbPABPZBO8I)
* [leetcode видео-разбор: Regex](https://youtu.be/LbeflFeDONU)
  * [мой код](https://gist.github.com/sashuIya/527ed3335561fb2b9b31c659d399e6a0)
* [leetcode видео-разбор: Jump Game II (теория - корневая оптимизация и segment tree)](https://youtu.be/hWVTOr6phl8)
  * [пишем код online (segment tree)](https://youtu.be/tmv7W9Xw3lo)
  * [мой код](https://gist.github.com/sashuIya/9afbe716e0475e2a0c5cc5a3c58e248f)

### 15. Разделяй и властвуй
* [leetcode-разбор: Different Ways to Add Parentheses](https://youtu.be/-oclJ3KCPqM)
  * [ссылка на литкод](https://leetcode.com/problems/different-ways-to-add-parentheses/)

### 16. Бор + Перебор + ДП
* Задача про расстановку пробелов в строке ([leetcode-140](https://leetcode.com/problems/word-break-ii
))
  * [видео-разбор](https://youtu.be/R_hZJLmBhA4)
  * [пишу код](https://youtu.be/7uVUXerWa7E)
  * [мой код на гите](https://gist.github.com/sashuIya/e2c2aa691aa13b0672dee1406d9ed0f3)

## Advanced Level (просто интересные задачки)

### Теория вероятностей
* [задачка про поиск памяти](https://youtu.be/K5-UUpDWnoQ)
* [задачка про прохождение игры](https://youtu.be/pstBUzWotTI)
