# How to change a commit message?

## 가장 최신의 커밋 메시지를 변경할 경우

```bash
git commit --ammend
```

> `amend`: 수정하다

- 커밋 메시지를 변경하면 커밋 ID, 즉 커밋 이름을 정하는 SHA1 체크섬이 변경된다.

  > **SHA1(Secure Hash Algorithm 1)?**
  >
  > 암호화 해시 함수 중 하나로 파일이 변경되지 않았다는 것을 확인하는데 자주 사용된다.

  > **체크섬(checksum)?**
  >
  > SHA를 실행한 결과로 해시 합계라고도 한다.
  >
  > 파일 버전에서 생성한 체크섬과 파일 소스에서 체크섬을 비교하면서 파일 사본에 오류가 발생하지 않도록 막을 수 있다.

### 이미 push를 날렸다면?

- 위 명령어를 실행하고 오래된 커밋을 강제로 덮는다.

  ```bash
  git push --force-with-lease
  ```

## 오래되거나 여러 커밋 메시지를 변경할 경우

- 현재 위치(HEAD)에서 이전 n개의 커밋을 되돌린다.

  ```bash
  git rebase -i HEAD~n
  ```

  > `rebase`: 새로운 기준을 설정하다 → base를 새롭게 설정한다.
  >
  > `-i`: `--interactive`로 `git rebase` 명령어를 대화형으로 실행한다.

- 변경하고 싶은 커밋 메시지 앞단에 있는 `reword`를 `pick`으로 고치고 메시지도 고친다.

  ```bash
  pick e499d89 Delete CNAME
  reword 0c39034 Better README
  reword f7fde4a Change the commit message but push the same commit.
  ```

- `:wq`로 저장하고 파일을 닫는다.

### 이미 push를 날렸다면?

- 위 명령어를 실행하고 오래된 커밋을 강제로 덮는다.

  ```bash
  git push --force origin EXAMPLE-BRANCH
  ```

### reference

- https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message
- https://ko.eyewated.com/sha-1%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C/
- https://git-scm.com/docs/git-rebase
