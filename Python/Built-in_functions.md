# Built-in functions

## min(), max()

> min(iterable, \*[, key, default])
>
> min(arg1, arg2, \*args[, keys])
>
> max(iterable, \*[, key, default])
>
> max(arg1, arg2, \*args[, keys])

- **2개 혹은 그 이상의 인자에서 가장 작은(큰) 값을 반환**한다.
- 같은 인덱스에 있는 값큰을 하나씩 비교하므로, 시간 복잡도는 **O(n)** 이다.

  ```python
  print(min(3, 4)) # 3


  n = "HelloWorld"
  m = "HelloPython"
  o = "Hello42"
  print(max(m, n, o)) # HelloWorld
  ```

## sorted()

- lambda 함수를 이용해 정렬하는 기준(key)를 설정하여 2차원 리스트를 정렬한다.

```python
arr = [[6, 1], [1, 2], [3, 5], [2, 5], [7, 0]]

sorted(arr, key=lambda a: a[0]) # [[1, 2], [2, 5], [3, 5], [6, 1], [7, 0]]
sorted(arr, key=lambda a: a[1]) # [[7, 0], [6, 1], [1, 2], [3, 5], [2, 5]]

```

### reference

- https://docs.python.org/3/library/functions.html#min
- https://wiki.python.org/moin/TimeComplexity
- https://stackoverflow.com/questions/18563680/how-to-sort-a-2d-list
