# sys

- python 인터프리터가 제공하는 변수와 함수를 직접 제어할 수 있는 모듈.

## sys.stdin, sys.stdout, sys.stderr

- 인터프리터가 표준 입력, 출력 및 오류를 위해 사용하는 파일 객체

> 💡 `sys.stdio.readline`이 `input()`보다 빠른 이유?
>
> - `input()`
>
>   - 사용자가 입력하고 enter(`\n`)를 누르기 전까지 프로그램은 중지된다.
>   - _입력될 때마다 1개의 해당 데이터가 버퍼에_ 들어간다.
>   - `\n`은 읽지 않는다.
>
> - `sys.stdin.readline`
>   - 사용자가 입력한 escape 문자(`\n` 등) 또한 읽는다.
>   - _입력받은 데이터를 한 번에 읽어와_ 버퍼에 저장한다.

## sys.setrecursionlimit(limit)

- C 스택의 오버플로우를 발생시키는 무한 재귀와 python이 충돌하는 것을 방지한다.
  - `C 스택`: 인터프리터 루프의 재귀 호출이 담기는 스택
- `limit`
  - python 인터프리터 스택의 최대 깊이
  - 플랫폼에 따라 limit의 최대 한도는 다르다.
- 현재 재귀 depth에서 limit이 너무 낮으면 `RecursionError`를 발생시킨다.(3.5.1 ver)

<br>
</br>

### reference

- https://docs.python.org/3/library/sys.html
- https://www.geeksforgeeks.org/difference-between-input-and-sys-stdin-readline/#:~:text=The%20input%20takes%20input%20from,value%20before%20the%20user%20input
- https://countingalaxy.tistory.com/entry/%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%9D%98-%EC%9E%85%EB%A0%A5%EA%B3%BC-%EC%B6%9C%EB%A0%A5
