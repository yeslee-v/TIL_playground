# Path variable vs Query parameter

## Path variable

- 경로를 변수로 사용한다 → `자원을 식별`하고 싶을 때

```typescript
// 전체 post 가져오기
// id가 1인 post 가져오기

/post
/post/1
```

## Query parameter

- 백엔드(서버)에서 id 변수를 가져온다 → `정렬하거나 필터링`할 때

```typescript
// date가 2022인 post 리스트 가져오기

/post?date=2022
```

### reference

- https://medium.com/@fullsour/when-should-you-use-path-variable-and-query-parameter-a346790e8a6d
