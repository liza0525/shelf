# Rust 학습 커리큘럼

배경: Python 익숙, Java/C 경험 있음
기간: 약 8주 (주당 5~8시간 기준)

## 1주차 — 기초 문법
- `cargo` 사용법 (new, build, run, test)
- 변수, 타입, 함수, 제어문
- The Book 1~3장
- 실습: 간단한 CLI 계산기

## 2~3주차 — 소유권과 빌림 (Rust의 핵심)
- Ownership, Borrowing, Lifetimes (The Book 4장)
- Python/Java의 GC, C의 수동 메모리 관리와 비교하며 이해하기
- 실습: 문자열 처리 프로그램 (소유권 이동 vs 참조 비교)

## 4주차 — 구조체, 열거형, 패턴 매칭
- struct, enum, `Option<T>`, `Result<T, E>`
- match, if let
- 에러 핸들링 (`?` 연산자)
- 실습: 파일 파싱 도구 (CSV → struct 벡터)

## 5주차 — 컬렉션과 트레잇
- Vec, HashMap, Iterator
- Trait, Generic, impl
- 실습: 간단한 인메모리 key-value 스토어

## 6주차 — 동시성
- 스레드, `Arc<Mutex<T>>`, 채널
- async/await 기초 (tokio 소개만)
- 실습: 멀티스레드 워커 풀

## 7주차 — 실전 프로젝트 1: CLI 툴
- clap으로 CLI 만들기
- 예: 로그 파서, TODO 관리 툴

## 8주차 — 실전 프로젝트 2: 웹 서버
- axum 또는 actix-web으로 간단한 REST API
- sqlx로 DB 연동 (board CRUD를 Rust로 재구현)

## 참고 자료
- The Rust Programming Language (공식 무료 book, rust-lang.org) — 뼈대
- Rustlings — 짧은 연습문제, 1~5주차 병행 추천
- Rust by Example — 문법 참고용
