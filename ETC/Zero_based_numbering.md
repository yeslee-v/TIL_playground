# Zero-based numbering

- 시퀀스의 초기 요소에서 index에 0을 할당하는 번호 매기기.

## 배열에서 랜덤 엑세스가 필요하다.

- `arr + i` : 배열의 시작 요소에서 i 거리에 있는 주소
- 시작 요소가 배열의 시작 요소에서 거리가 0인 곳에 있기 때문에

  ```c++
  #include <iostream>

  using namespace std;

  int main() {
    int arr[] = {1, 2, 3, 4};

    // Below two statements mean same thing
    cout << *(arr + 1) << " ";
    cout << arr[1] << " ";

    return 0;
  }
  ```

## 대용량 데이터 처리시, 성능 및 속도가 향상된다.

```c++
// case 1: array indices start from 0
// performing 4
&(arr[i][j]) = &arr + [(i) * n + (j)] * (sizeof(int));

// case 2: array indices start from 1
// performing 6
&(arr[i][j]) = &arr + [(i - 1) * n + (j - 1)] * (sizeof(int));
```

- index를 0으로 설정하면 1로 설정했을 때보다 2번의 연산을 덜 수행한다.
- Lua 배열은 index를 1로 설정하기 때문에 거의 사용하지 않는 이유 중 하나라고 한다.

### reference

- https://en.wikipedia.org/wiki/Zero-based_numbering
- https://www.geeksforgeeks.org/why-array-index-starts-from-zero/
