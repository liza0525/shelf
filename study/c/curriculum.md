# C 학습 커리큘럼

배경: Python 전문가 수준, Java/C 경험 있음 (기초 문법은 익숙하나 깊이는 부족)
기간: 약 8주 (주당 5~8시간 기준)

## 1주차 — 빌드 도구체인과 문법 재정비
- 컴파일 과정: 전처리(`#include`, `#define`) → 컴파일 → 어셈블 → 링킹
- `gcc`/`clang` 플래그 (`-c`, `-o`, `-I`, `-L`, `-l`, `-Wall -Wextra`)
- `Makefile` 기초 (타겟, 의존성, `$@`/`$<` 자동 변수)
- 기본 문법 빠른 복습: 타입, 제어문, 함수, 스코프 (Python/Java와 다른 점 위주로)
- 실습: 여러 `.c`/`.h` 파일로 나눈 소스를 `Makefile`로 빌드하기

## 2주차 — 포인터 심화
- 포인터와 배열의 관계, 배열이 함수 인자로 넘어갈 때 포인터로 decay되는 원리
- 포인터 연산 (`ptr + n`, 포인터 간 뺄셈), `const` 포인터 조합
- 다중 포인터(`int **`)와 함수 포인터 (`void (*fp)(int)`)
- `void*`를 이용한 제네릭 스타일 코드 (`qsort` 비교 함수 등)
- 실습: 함수 포인터 배열로 간단한 커맨드 디스패치 테이블 구현

## 3주차 — 메모리 관리
- 스택 vs 힙, 프로세스 메모리 레이아웃 (text/data/bss/heap/stack) 개요
- `malloc`/`calloc`/`realloc`/`free`의 동작과 반환값 체크
- 메모리 누수, `double free`, `use-after-free`, `dangling pointer` 사례
- `valgrind`로 누수/오류 잡아보기
- 실습: 가변 크기 동적 배열(`realloc` 기반) 구현 + `valgrind`로 검증

## 4주차 — 구조체, 유니온, 동적 자료구조
- `struct`/`union` 메모리 배치, 패딩과 정렬(alignment) 개념
- 구조체 포인터와 `->` 연산자, 중첩 구조체
- 연결 리스트(단일/이중) 직접 구현 (`malloc`로 노드 생성/해제)
- 스택/큐를 연결 리스트 기반으로 구현
- 실습: 이중 연결 리스트 기반 스택 자료구조 + 삽입/삭제/순회 함수

## 5주차 — 파일 입출력과 표준 라이브러리
- `fopen`/`fread`/`fwrite`/`fclose`, 텍스트 vs 바이너리 모드
- 문자열 처리 함수 (`strcpy`/`strncpy`/`strtok`/`sscanf`)와 버퍼 오버플로우 주의점
- 에러 처리 관례: `errno`, `perror`, `strerror`, 반환값 체크 패턴
- 표준 라이브러리 훑기 (`string.h`, `stdlib.h`, `ctype.h`)
- 실습: 텍스트 파일을 읽어 단어 빈도수를 세는 프로그램

## 6주차 — 디버깅과 Undefined Behavior
- `gdb` 기초 (breakpoint, step, print, backtrace, watch)
- Undefined Behavior 사례: 정수 오버플로우, 초기화되지 않은 변수, out-of-bounds 접근, 타입 punning
- 컴파일러 경고 최대로 켜기 (`-Wall -Wextra -Wpedantic -fsanitize=address,undefined`)
- 정적 분석 도구 맛보기 (`clang-tidy`, `cppcheck`)
- 실습: 일부러 버그를 심은 코드를 `gdb`와 sanitizer로 찾아 고치기

## 7~8주차 — 실전 프로젝트: 미니 셸(shell) 구현
- `fork`/`exec`/`wait`로 프로세스 생성 및 명령 실행
- 파이프(`pipe`)와 파일 디스크립터 리다이렉션(`dup2`)으로 `|`, `>`, `<` 지원
- `cd`, `exit` 같은 빌트인 명령 처리
- 입력 파싱 (토크나이징), 4~5주차의 문자열/파일 처리 지식 활용
- 3주차 메모리 관리 원칙 적용: 동적으로 할당한 인자 배열/버퍼 해제 확인 (`valgrind`로 최종 검증)
- 실습: 파이프와 리다이렉션을 지원하는 미니 셸 완성 + README에 설계 정리

## 참고 자료
- The C Programming Language (K&R, 2nd Edition) — 고전이자 핵심 개념 정리용
- Beej's Guide to C Programming — 포인터/메모리/파일 입출력 등 실전 감각 잡기 좋음
- cppreference.com (C 섹션) — 표준 라이브러리 함수 레퍼런스
- Beej's Guide to Network Programming — 7~8주차 셸 프로젝트에서 `fork`/`pipe` 개념 참고용
