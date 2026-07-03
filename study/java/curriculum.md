# Java 학습 커리큘럼

배경: Python 전문가 수준, Java/C 사용 경험 있음 (기본 문법은 익숙하나 깊이는 부족)
기간: 약 7주 (주당 5~8시간 기준)

## 1주차 — JVM과 빌드 생태계
- JVM 동작 방식: 바이트코드, 클래스 로더, `JIT` 컴파일, GC 개요 (Python의 CPython 인터프리터/참조 카운팅 GC와 비교)
- 빌드 도구: `Maven`(pom.xml)과 `Gradle`(build.gradle) 기본 구조, 의존성 관리 개념 (Python의 pip/poetry와 비교)
- 강한 정적 타입 시스템: 컴파일 타임 타입 체크, `var`를 이용한 타입 추론, 오토박싱/언박싱 (`int` vs `Integer`)
- 기본 문법 복습은 짧게: 배열, 제어문, 메서드 오버로딩 — Python과 다른 부분 위주로만
- 실습: Maven/Gradle 프로젝트 초기 세팅 후 간단한 hello-world 실행 + `javap`로 바이트코드 확인

## 2주차 — OOP 심화
- 클래스 설계: 생성자 오버로딩, `this`/`super`, 정적 vs 인스턴스 멤버
- 인터페이스와 추상 클래스 차이, `default`/`static` 메서드 (Python의 ABC, Protocol과 비교)
- 상속 vs 컴포지션: "합성 우선" 원칙, `final` 클래스/메서드로 상속 제한
- 접근제어자(`public`/`protected`/`private`/package-private)와 캡슐화
- `equals()`/`hashCode()`/`toString()` 오버라이드 규칙, `record` 타입으로 대체하기
- 실습: 도서관 대출 시스템 도메인 모델링 (클래스 계층 + `equals`/`hashCode` 직접 구현 후 `record`로 리팩터링)

## 3주차 — 제네릭과 컬렉션 프레임워크
- 제네릭 기초: `<T>`, 타입 경계(`extends`), 와일드카드(`? extends`, `? super`)
- `List` 구현체 비교: `ArrayList` vs `LinkedList`
- `Set` 구현체 비교: `HashSet` vs `TreeSet` vs `LinkedHashSet`
- `Map` 구현체 비교: `HashMap` vs `TreeMap` vs `LinkedHashMap`, Python `dict`와의 내부 구조 차이
- `Optional<T>`로 null 안전성 다루기 (Python의 `None` 체크 관행과 비교)
- 실습: CSV 데이터를 읽어 `Map<String, List<T>>`로 그룹핑하는 유틸리티 작성

## 4주차 — 스트림 API와 람다
- 함수형 인터페이스: `Function<T,R>`, `Predicate<T>`, `Supplier<T>`, `Consumer<T>`
- 람다 표현식과 메서드 레퍼런스(`::`)
- `Stream` 파이프라인: `filter`/`map`/`reduce`/`collect` — Python의 `map`/`filter`/list comprehension과 1:1 비교
- `Collectors`(`groupingBy`, `toMap`, `joining`)와 병렬 스트림(`parallelStream`) 주의점
- 실습: 대량 레코드 데이터를 스트림으로 집계/필터링하는 리포트 생성기 (Python 버전과 성능/가독성 비교)

## 5주차 — 예외 처리와 동시성 기초
- Checked vs Unchecked 예외, 커스텀 예외 설계, `try-with-resources`
- 스레드 기초: `Thread`, `Runnable`, `synchronized`, `volatile` (Python GIL과의 차이 — 진짜 병렬 실행)
- `ExecutorService`와 스레드 풀, `Future`/`CompletableFuture`로 비동기 조합
- 실습: 여러 URL을 동시에 호출해 결과를 취합하는 멀티스레드 다운로더

## 6~7주차 — 실전 프로젝트: Spring Boot REST API
- `Spring Boot` 소개: 의존성 주입(DI), `@RestController`/`@Service`/`@Repository` 계층 구조
- JPA/Hibernate로 DB 연동 (board CRUD API를 Java로 재구현)
- 계층별 예외 처리와 `@ExceptionHandler`, 검증(`@Valid`)
- `JUnit 5`와 `Mockito`로 서비스/레포지토리 단위 테스트 작성
- 실습: 게시판 CRUD REST API 완성 + 테스트 코드 + Postman/curl로 동작 검증

## 참고 자료
- Effective Java (Joshua Bloch) — 관용적인 Java 작성법의 바이블
- Oracle 공식 Java Tutorials/JLS — 언어 스펙 및 표준 라이브러리 레퍼런스
- Baeldung — 스트림, 컬렉션, Spring 관련 실전 예제가 풍부한 튜토리얼 사이트
- Spring Boot 공식 가이드(spring.io/guides) — 6~7주차 프로젝트 진행 시 참고
