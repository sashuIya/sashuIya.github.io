```py
class Solution:
  def twoSum(self, numbers: List[int], target: int) -> List[int]:
    first_index = 0
    second_index = len(numbers) - 1
    
    while first_index < second_index:
      current_sum = numbers[first_index] + numbers[second_index] 
      if current_sum == target:
        return [first_index + 1, second_index + 1]
      elif current_sum < target:
        first_index += 1
      else:
        second_index -= 1
    
    return None
```
