```cpp
int countTrappingWater(const vector<int>& heights) {
  if (heights.empty()) return 0;

  // Find the max element index.
  int max_element_index = 0;
  for (int index = 0; index < heights.size(); index++) {
    if (heights[index] > heights[max_element_index]) {
      max_element_index = index;
    }
  }

  int result = 0;

  int max_left = 0;
  for (int index = 0; index < max_element_index; index++) {
    // Current element is less or equal to the max element (which is on the right from index).
    // If there is an element higher on the left, the current element is in a pit.
    if (heights[index] < max_left) {
      result += max_left - heights[index];
    }

    // We always want to know the max on the left, to know the pit height.
    max_left = max(max_left, heights[index]);
  }

  // Similar to previous loop, but for the tail of the array.
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
