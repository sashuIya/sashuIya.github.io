## Здравствуйте, товарищи!

Я постараюсь пройтись по основным темам/задачам и в коротких видео предоставить необходимый теоретический материал, советы по написанию кода и важные, на мой взгляд, замечания, чтобы Вы могли уверенно и успешно проходить такого рода интервью.

### Бинарный поиск
* [видео-разбор](https://youtu.be/fZ9VKq8ybq4)
* [задачка на leetcode](https://leetcode.com/problems/binary-search)
<details><summary>код</summary>
<p>

```C++
int search(vector<int>& nums, int target) {
  if (nums.empty()) return -1;

  int l = 0;
  int r = nums.size(); // element after the last

  while (l + 1 < r) {
    int m = l + (r - l) / 2;
    if (a[m] > target) {
      r = m;
    } else {
      l = m;
    }
  }

  return a[l] == target ? l : -1;
}
```

</p>
</details>

### Быстрое возведение в степень
* [видео-разбор](https://youtu.be/swktXq5COtI)
* [задачка на leetcode](https://leetcode.com/problems/powx-n)
