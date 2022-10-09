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

### reference

- https://docs.python.org/3/library/functions.html#min
- https://wiki.python.org/moin/TimeComplexity
