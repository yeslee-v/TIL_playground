# Static Analysis vs Dynamin Analysis

## Static Analysis

- 코드를 실행하고 나서 어플리케이션 테스팅 및 평가
- 실행 중에 호출되는 경로뿐만 아니라 가능한 모든 실행 경로와 변수 값 검사 => 보안 보증에서 중요

  ex) linter

## Dynamin Analysis

- 런타임 중에 어플리케이션 테스팅 및 평가
- 프로그램 내 결함 및 취약점 분석, 메모리 및 스레드 결험 분석

  ex) Valgrind, debugging, Jest, TDD

### reference

- https://ojava.tistory.com/190
- https://www.intel.com/content/www/us/en/develop/documentation/inspector-user-guide-windows/top/getting-started/dynamic-analysis-vs-static-analysis.html
- https://www.technoarchsoftwares.com/blog/what-the-debugging-is-and-why-we-need-to-debug/
