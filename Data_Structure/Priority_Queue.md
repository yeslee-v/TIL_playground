# Priority Queue

- 우선 순위 큐.
- 일반 queue는 FIFO의 특징을 가지는데 비해 priority queue는 우선 순위에 따라 제거 순서가 달라진다.
- python의 경우, queue 클래스에서 priority queue를 불러올 수 있다.

  ```python
  from queue import PriorityQueue

  q = PriorityQueue(maxsize) # maxsize <= 0 👉 infinite queue size
  ```

## heapify

- 이진 트리를 힙으로 바꾸는 과정.
- max-heap 혹은 min-heap으로 만들 때 사용한다.

### reference

- https://docs.python.org/3/library/queue.html
- https://www.programiz.com/dsa/priority-queue
- https://www.tutorialspoint.com/data_structures_algorithms/heap_data_structure.htm
