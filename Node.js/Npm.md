# npm(Node Package Manager)

- Node.js 환경에서 JavaScript 런타임을 위한 기본 패키지 매니저.

## package.json

- 프로젝트 동작시 필요한 모듈을 담고 있는 텍스트 파일로 `npm init`을 입력했을 때 생성된다.
- `npm install [package]`를 통해 생성된 패키지와 버전 정보는 `dependencies`에 저장된다. -> node_modules가 존재하지 않아도 `npm i`로 `dependencies` 내 패키지들이 자동으로 설치된다.

  > **node_modules**? `npm`으로 설치한 패키지와 의존성을 갖는 다른 패키지들이 저장된다.
  >
  > **devDependency**?
  >
  > - 개발자에게 필요한 `dependency`
  >
  >   ex) Babel은 최신 자바스크립트 언어로 바꾸기 위해 사용되기 때문에 `--save-dev` 옵션을 사용해 `devDependencies`에 저장된다.

## package-lock.json

- `npm`이 `node_modules` 또는 `package.json`을 수정할 때 자동으로 생성되는 파일.
- 패키지가 수정됐는지의 여부는 해쉬값(`integrity`)으로 알 수 있다.

> [좀 더 자세히 알아보자](https://velog.io/@songyouhyun/Package.json%EA%B3%BC-Package-lock.json%EC%9D%98-%EC%B0%A8%EC%9D%B4)

### reference

- https://docs.npmjs.com/cli/v8/configuring-npm/package-json
- https://docs.npmjs.com/cli/v7/configuring-npm/package-lock-json
