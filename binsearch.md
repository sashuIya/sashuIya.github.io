```cpp
int search(const vector<int>& nums, int target) {
  if (nums.empty()) return -1;

  int l = 0;
  int r = nums.size(); // element after the last

  while (l + 1 < r) {
    int m = l + (r - l) / 2; // rather than `(l + r) / 2`, to avoid int overflow
    if (a[m] > target) {
      r = m;
    } else {
      l = m;
    }
  }

  return nums[l] == target ? l : -1;
}
```

## Замечания:
1. `r` указывает на элемент после последнего, что позволяет избежать `+/- 1` при обновлении `l` и `r`.
2. Если писать `(l + r) / 2`, то могут придраться, что `l + r` может вылезти за границы типа int.
3. Данный код находит самый правый элемент, равный `target`. Если хочется искать самый левый, то считаем, что `a[-1] = -oo` и `a[l]` всегда меньше `target`. Конкретнее:

```cpp
...

  int l = -1;
  int r = nums.size() - 1;
...

    if (a[m] < target) {
      l = m;
    } else {
      r = m;
    }
...
  return nums[r] == target ? r : -1;
...
```
