# Kotlin + Spring 백엔드 16주 커리큘럼 (무료 자료 + Claude 튜터)

> 시작일: 2026-06-11 · 하루 2시간 × 주 5~6일 ≈ 총 ~180시간
> 제약: 책 구매·유료 강의 없음. 무료 공개 자료가 "뼈대(목차)", Claude가 "살(설명·실습·리뷰·퀴즈)".
> 모든 링크는 2026년 6월 기준 무료 접근 확인됨.

## 데일리 세션 운영법

매일 2시간을 **자료 1시간 : 직접 코딩 1시간**으로 나눈다. Claude Code에서:

1. **시작**: "오늘 수업 시작" → Claude가 `PROGRESS.md`를 읽고 오늘 범위를 안내
2. **학습**: 자료를 보다가 막히면 Claude에게 질문. 영어 자료는 "이 챕터 한국어로 해설해줘, TS와 비교해서" 패턴 활용
3. **실습**: 배운 것을 코드로. Claude는 리뷰만 (아래 튜터 규칙 참고)
4. **마무리**: "오늘 배운 거 퀴즈 내줘" → 3~5문제 → Claude가 `PROGRESS.md` 갱신

### Claude 튜터 규칙

- **1~4단계: 코드 생성 금지.** 설명, 코드 리뷰, 퀴즈, 디버깅 힌트만. 코드는 내 손으로
- **5단계부터: 생성 허용.** 단, 생성된 코드에서 문제(트랜잭션 누락, N+1, 검증 빠짐)를 내가 먼저 찾는 훈련
- Java 예제를 만나면 내가 먼저 Kotlin으로 변환 → Claude가 검사 (통변환 시키지 않기)
- 주 1회(주말) "이번 주 범위 종합 퀴즈 + 약한 부분 진단" 요청

---

## 1단계 · Kotlin 속성 — 1~2주차 (~24h)

| 자료 | 분량 | 메모 |
|---|---|---|
| [From TypeScript to Kotlin](https://www.casperfeng.com/blog/kotlin-for-typescript-developers) | 1h | 첫날 워밍업. TS↔Kotlin 개념 매핑 |
| [Kotlin Tour (공식)](https://kotlinlang.org/docs/kotlin-tour-welcome.html) | 6~10h | Beginner + Intermediate, 브라우저 실행 |
| [Kotlin Koans](https://play.kotlinlang.org/koans) | 6~8h | Tour와 병행, 손에 붙이기 |
| JVM 리터러시 | 2h | 강의 없음. Claude와 문답으로: JDK/JRE/JVM 차이, 바이트코드(왜 Kotlin·Java가 같이 동작?), GC, "서버는 오래 떠 있는 프로세스". 깊은 GC/힙 튜닝은 6단계+현업에서 |
| npm→Gradle 매핑 | 2h | 강의 없음. Claude와 "package.json의 scripts/deps는 Gradle에서 뭐야?" 문답으로 정리 |
| [Kotlin 공식 문서](https://kotlinlang.org/docs/home.html) | — | 책 대신 상시 레퍼런스 |

**완료 기준**: Koans 전체 풀이 + 작은 CLI 프로그램(예: JSON 파싱해서 집계) 하나를 Kotlin으로 작성 + "JVM이 뭔지 V8과 비교해서" 말로 설명 가능.

## 2단계 · HTTP + Spring 첫 발 — 3~4주차 (~20h)

| 자료 | 분량 | 메모 |
|---|---|---|
| [MDN HTTP 가이드 (한국어)](https://developer.mozilla.org/ko/docs/Web/HTTP) | 5~6h | 개요·메시지·세션·캐싱·상태코드·인증 섹션. 프론트 경험으로 아는 내용은 "백엔드 관점에서는?"을 Claude에게 묻기 |
| [스프링 입문 — 김영한 (인프런, 무료)](https://www.inflearn.com/course/스프링-입문-스프링부트) | 5.5h | 한국어로 전체 그림. 구버전 Boot 기준이라 차이나면 Claude에게 |
| [Get started with Spring Boot and Kotlin (JetBrains 공식)](https://kotlinlang.org/docs/jvm-get-started-spring-boot.html) | 2~3h | 4부작. Java 패턴 → Kotlin 관용구 전환 |

**완료 기준**: start.spring.io로 만든 Kotlin 프로젝트에서 GET/POST 엔드포인트 + 간단한 인메모리 CRUD 동작.

## 3단계 · Spring 핵심 원리 — 5~7주차 (~30h)

| 자료 | 분량 | 메모 |
|---|---|---|
| [Spring Framework Essentials (Spring Academy, 무료)](https://spring.academy/courses/spring-framework-essentials) | ~9h | IoC/DI 컨테이너, 빈 생명주기, AOP. Broadcom 계정 가입 필요. 영어 — 레슨마다 Claude에게 한국어 정리 요청 |
| [Building a REST API with Spring Boot (Spring Academy, 무료)](https://spring.academy/courses/building-a-rest-api-with-spring-boot) | ~5h | 실습 랩 포함. Initializr→Spring Data→Security→TDD 전 과정 |
| [Building web applications with Spring Boot and Kotlin (spring.io 공식 튜토리얼)](https://spring.io/guides/tutorials/spring-boot-kotlin) | 3~4h | Boot 4.x·Kotlin 최신 기준. 블로그 앱 전체 흐름 |
| [spring.io Guides](https://spring.io/guides) | — | 주제별 15~30분 레시피. 필요할 때 찾아보는 용도 |

**완료 기준**: "DI가 왜 필요한가"를 코드 없이 말로 설명 가능 + Java 예제 코드를 보고 Kotlin으로 변환 가능.

## 4단계 · DB·트랜잭션·JPA — 8~11주차 (~45h) ★ 핵심 구간

이 단계는 Claude 튜터 의존도가 가장 높다. 영상은 10분짜리 개요이므로, **영상 → Claude와 심화 문답 → 코드 실습** 사이클로.

### 4-1. SQL 기초 (8주차)
| 자료 | 메모 |
|---|---|
| [생활코딩 DATABASE2 - MySQL](https://opentutorials.org/course/3161) | SQL이 처음이면 여기부터. CRUD/JOIN |
| [MySQL 공식 Tutorial (Ch.5)](https://dev.mysql.com/doc/refman/8.4/en/tutorial.html) | 따라하기 실습 |
| 테코톡: [찰리의 인덱싱](https://www.youtube.com/watch?v=P5SZaTQnVCA) · [레베카의 인덱스](https://www.youtube.com/watch?v=9ZXIoh9PtwY) | 인덱스 개념. EXPLAIN 실습은 Claude와 |

### 4-2. 트랜잭션 (9주차)
| 자료 | 메모 |
|---|---|
| 테코톡: [러쉬의 MySQL 트랜잭션 격리 수준](https://www.youtube.com/watch?v=QHWwNTGkwAU) | Dirty/Phantom Read 시나리오는 Claude에게 예시 요청 |
| 테코톡: [후니의 스프링 트랜잭션](https://www.youtube.com/watch?v=cc4M-GS9DoY) · [리차드의 @Transactional](https://www.youtube.com/watch?v=taAp_u83MwA) | 프록시 기반 동작 원리 |
| [우아한형제들 — 응? 이게 왜 롤백되는거지?](https://techblog.woowahan.com/2606/) | 단원 마무리 심화 글 |

### 4-3. JPA (10~11주차)
| 자료 | 메모 |
|---|---|
| 테코톡: [아마찌의 ORM vs SQL Mapper vs JDBC](https://www.youtube.com/watch?v=VTqqZSuSdOk) | JVM 진영 DB 접근 기술 지형 (오리엔테이션) |
| 테코톡: [산초의 영속성 컨텍스트와 EntityManager](https://www.youtube.com/watch?v=c4rDrirE7Bc) | 1차 캐시·쓰기 지연·더티 체킹 |
| [Hibernate Introduction (short guide)](https://hibernate.org/orm/documentation/) | 개념 파트. User Guide 통독 금지 (사전식) |
| [Spring Data JPA 레퍼런스](https://docs.spring.io/spring-data/jpa/reference/index.html) | Getting Started → Core concepts → Repository Interfaces → Query Methods 순서만 |
| 테코톡: [수달의 JPA N+1 문제](https://www.youtube.com/watch?v=ni92wUkAmQI) | 연관관계 이해 후 시청 |
| [코프링 매우 알은 체하기 (우아한테크세미나)](https://www.youtube.com/watch?v=ewBri47JWII) + [JetBrains: JPA/Kotlin pitfalls](https://blog.jetbrains.com/idea/2026/01/how-to-avoid-common-pitfalls-with-jpa-and-kotlin/) | Kotlin+JPA 함정 (allopen, final 클래스) |
| [테코블](https://tecoble.techcourse.co.kr/) | 단원별 심화 글 아카이브 (Cascade, DTO vs Entity 등) |

**완료 기준**: 도커로 띄운 MySQL에 JPA로 연관관계 엔티티 CRUD + 의도적으로 N+1을 만들고 fetch join으로 해결해보기.

## 5단계 · 실전 프로젝트 + 인증·검증·테스트 — 12~14주차 (~33h)

**내가 만든 프론트엔드 프로젝트의 백엔드를 Kotlin + Spring Boot + MySQL로 구현한다.** 진행하며 필요한 조각 채우기:

| 주제 | 자료 |
|---|---|
| API 설계 감각 | [토스페이먼츠 블로그](https://docs.tosspayments.com/blog) — 멱등성, POST/PUT/PATCH 차이 등 |
| 검증·예외 처리 | spring.io Guides (Validation) + Claude와 `@RestControllerAdvice` 전역 예외 설계 |
| 인증 | [Spring Boot JWT Tutorial — 정은구 (인프런, 무료)](https://www.inflearn.com/course/스프링부트-jwt) + Spring Academy REST API 코스의 Security 파트 복습 |
| 테스트 | [우아한형제들 — 스프링에서 코틀린 스타일 테스트 코드 작성하기](https://techblog.woowahan.com/) (MockK/Kotest) + [mockk.io](https://mockk.io) 공식 문서 |
| (선택) 코루틴 | [Kotlin 공식 Coroutines Guide](https://kotlinlang.org/docs/coroutines-guide.html) basics~Context까지만. MVC+JPA 스택에선 당장 불필요 |

**완료 기준**: 인증 포함 API가 동작하고, 핵심 서비스 로직에 테스트가 있고, Claude가 생성한 코드에서 문제를 3개 이상 직접 찾아본 경험.

## 6단계 · 배포 + 회사 코드 — 15~16주차 (~22h)

| 자료 | 분량 | 메모 |
|---|---|---|
| [생활코딩 Docker 입구 수업](https://opentutorials.org/course/4781) | 1h | 컨테이너 개념, 한국어 |
| [Docker 공식 Get Started workshop](https://docs.docker.com/get-started/) | 3~4h | 이미지 빌드 → 멀티 컨테이너 → Compose. ⚠️ Docker Desktop은 기업 사용 시 유료 — 회사 기기면 사내 라이선스 확인 또는 colima/OrbStack 사용 |
| 5단계 프로젝트 배포 | ~8h | 컨테이너화 → 클라우드(AWS 프리티어 등) 배포. 막히는 지점마다 Claude와 |
| **회사 백엔드 코드 읽기** | 남는 시간 전부 | 평소 호출하던 API의 서버 구현을 컨트롤러→DB까지 추적. 가능하면 작은 티켓 받기 |

---

## 제외한 것들 (이유)

- 유료 전부: 김영한 핵심원리·HTTP·MVC·JPA·DB 강의, 최태현 강의, JSCODE Docker (→ 위 무료 대안으로 대체)
- 책 전부: 코틀린 인 액션, Real MySQL, 아토믹 코틀린, 코틀린 코루틴 Deep Dive (→ 공식 문서 + Claude)
- 참고: 무료로 확인된 김영한 강의는 "스프링 입문"과 "자바 입문" 단 2개. 자바 입문(13h)은 Kotlin 직행이라 생략하되, Java 문법이 답답하면 발췌 시청

## 학습 중후반 읽을거리 (2~3개월 차부터)

- [카카오페이 기술블로그 BE 태그](https://tech.kakaopay.com/tag/be/) — Kotlin+Spring 실무 사례가 가장 많음
- [우아한형제들 기술블로그](https://techblog.woowahan.com/) — "Spring" 검색
