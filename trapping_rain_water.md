```cpp
int countTrappingWater(const vector<int>& heights) {
  if (heights.empty()) return 0;

  int max_element_index = 0;
  for (int index = 0; index < heights.size(); index++) {
    if (heights[index] > heights[max_element_index]) {
      max_element_index = index;
    }
  }

  int result = 0;

  int max_left = 0;
  for (int index = 0; index < max_element_index; index++) {
    if (heights[index] < max_left) {
      result += max_left - heights[index];
    }

    max_left = max(max_left, heights[index]);
  }

  int max_right = 0;
  for (int index = heights.size() - 1; index > max_element_index; index--) {
    if (heights[index] < max_right) {
      result += max_right - heights[index];
    }

    max_right = max(max_right, heights[index]);
  }

  return result;
}
```

## Замечания:
Сложность по времени: `O(n)`  
Сложность по дополнительной памяти: `O(1)`
