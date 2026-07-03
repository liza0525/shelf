# JavaScript 학습 커리큘럼

배경: Python 전문가 수준, Java/C 기본 문법 경험 있음, JavaScript는 사실상 처음
기간: 약 8주 (주당 5~8시간 기준)

## 1주차 — 실행 환경과 기본 문법
- 브라우저 콘솔 vs Node.js — JS가 돌아가는 두 가지 무대
- `let` / `const` / `var` 차이와 스코프 (`var`의 함수 스코프 vs `let`/`const`의 블록 스코프)
- 동적 타이핑과 타입 변환 — Python과 달리 `==`와 `===`가 다르게 동작함, `typeof`
- 기본 제어문·연산자는 Python/Java/C와 크게 다르지 않으니 빠르게 훑기
- 실습: Node.js REPL과 브라우저 콘솔에서 타입 강제 변환(`"5" + 3`, `"5" - 3` 등) 실험하며 규칙 정리

## 2주차 — 함수와 클로저
- 함수 선언문 vs 함수 표현식 vs 화살표 함수 (`function`, `const f = () => {}`)
- 일급 객체로서의 함수 — Python의 함수도 일급이지만 JS는 콜백 패턴이 훨씬 일상적임
- 클로저(`closure`) — Python의 클로저와 비교하며 렉시컬 스코프 이해하기
- 기본 매개변수, `arguments` vs `...rest`
- 실습: 클로저를 이용한 카운터/캐시 함수(memoization) 만들기

## 3주차 — 객체와 프로토타입, this
- 객체 리터럴, `class` 문법이 있지만 내부는 프로토타입 체인 기반이라는 점 (`Object.getPrototypeOf`, `__proto__`)
- `prototype` 기반 상속과 `class`/`extends`의 관계
- `this` 바인딩 규칙 — 일반 함수 vs 화살표 함수, `call`/`apply`/`bind`
- Python의 `self`(명시적 첫 인자)와 JS `this`(호출 방식에 따라 결정)의 근본적 차이
- 실습: `class` 없이 프로토타입만으로 객체 생성기 구현 후 `class` 버전과 비교

## 4주차 — 배열/객체 메서드 심화
- `Array.prototype.map` / `filter` / `reduce` — Python의 list comprehension/`map`/`filter`와 비교
- 구조 분해 할당(`destructuring`) — 배열과 객체
- spread(`...`)와 rest 문법, 얕은 복사 vs 깊은 복사
- 옵셔널 체이닝(`?.`)과 nullish coalescing(`??`)
- 실습: JSON 형태 데이터를 구조 분해 + 배열 메서드 체이닝으로 가공하는 함수 작성

## 5주차 — 비동기 프로그래밍
- 콜백 → `Promise` → `async`/`await`로 이어지는 비동기 패턴의 역사
- 이벤트 루프, 콜스택, 태스크 큐/마이크로태스크 큐 개념
- Python `asyncio`(코루틴 명시적 실행)와 JS(싱글 스레드 + 이벤트 루프 기본 내장)의 차이
- `Promise.all`, `Promise.race`, 에러 처리(`try/catch`, `.catch`)
- 실습: `fetch`로 외부 API 호출 후 `async`/`await`로 여러 요청을 병렬 처리하는 스크립트

## 6주차 — 모듈 시스템과 생태계
- ESM(`import`/`export`) vs CommonJS(`require`/`module.exports`)
- `npm`/`package.json`/`node_modules` — Python의 `pip`/`requirements.txt`와 비교
- 번들러(`Vite`, `webpack`) 개념 소개 — 왜 필요한지, 무엇을 하는지
- `Babel`/`TypeScript` 등 트랜스파일 도구의 존재 이유 가볍게 짚기
- 실습: 여러 파일로 모듈을 나눈 뒤 `npm init`으로 패키지 구성하고 Vite로 번들링해보기

## 7주차 — 실전 프로젝트 1: 브라우저 DOM 위젯
- DOM 조작 기본 (`document.querySelector`, `addEventListener`, `classList`)
- 이벤트 위임(event delegation), 폼 처리
- 상태를 순수 JS로 관리하며 화면을 갱신하는 흐름 (프레임워크 없이)
- 실습: 할 일 목록(TODO list) 위젯 — 추가/삭제/완료 토글, `localStorage`로 영속화

## 8주차 — 실전 프로젝트 2: Node.js REST API
- `Express`로 라우팅, 미들웨어 구성
- 요청 검증, 에러 핸들링 미들웨어
- 간단한 인메모리 또는 파일 기반 데이터 저장소 연동
- 실습: board API를 Express로 구현 (CRUD 엔드포인트 + 비동기 핸들러)

## 참고 자료
- MDN Web Docs (developer.mozilla.org) — 문법/API 레퍼런스의 정석
- javascript.info — 기초부터 심화까지 순서대로 읽기 좋은 튜토리얼
- You Don't Know JS (Kyle Simpson, 무료 공개 book) — 클로저·프로토타입·비동기 등 "이상한 부분" 심층 이해용
- Node.js 공식 문서 (nodejs.org/docs) — 6~8주차 실습 시 참고
