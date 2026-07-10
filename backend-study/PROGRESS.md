# 학습 진도 기록

> Claude 튜터용: 세션 시작 시 이 파일을 읽고 이어서 진행. 세션 종료 시 갱신할 것.
> 시작일 2026-06-11 · 목표 16주 · 하루 ~2시간

## 현재 위치

- **단계**: 1단계 · Kotlin 속성 (1~2주차) — Day 1 진행 중
- **다음 할 일**: Kotlin Tour Beginner 나머지(Functions, Classes, Null safety) → 1단계 CLI 프로그램 작성. (JVM 리터러시 + 기초 문법 퀴즈 진행 중)

## 단계별 체크리스트

- [ ] 1단계 · Kotlin 속성 (1~2주차) — 완료 기준: Koans 전체 + Kotlin CLI 프로그램 1개 + JVM 리터러시(V8 비교 설명 가능)
- [ ] 2단계 · HTTP + Spring 입문 (3~4주차) — 완료 기준: Kotlin 프로젝트로 인메모리 CRUD API
- [ ] 3단계 · Spring 핵심 원리 (5~7주차) — 완료 기준: DI를 말로 설명 + Java→Kotlin 변환 가능
- [ ] 4단계 · DB·트랜잭션·JPA (8~11주차) — 완료 기준: N+1 재현·해결 실습
- [ ] 5단계 · 실전 프로젝트 (12~14주차) — 완료 기준: 인증 포함 API + 테스트
- [ ] 6단계 · 배포 + 회사 코드 (15~16주차) — 완료 기준: 클라우드 배포 + 회사 코드 추적

## 세션 로그

| 날짜 | 학습 내용 | 퀴즈 결과 / 약한 부분 | 다음에 할 것 |
|---|---|---|---|
| 2026-06-26 | JVM 리터러시 강의 (JDK/JRE/JVM, 바이트코드, GC, long-running process) + TS→Kotlin 멘탈 모델 | 퀴즈는 다음 세션 (실습 후) | Kotlin Tour Beginner 실습, JDK+IntelliJ 설치 |
| 2026-06-26 | 학습 환경 구축(OpenJDK 21 + IntelliJ 2026.1, JAVA_HOME 설정) + Kotlin Tour Beginner 1~4(Hello world·Basic types·Collections·Control flow) | 퀴즈 진행 중 (결과 다음 세션 기록) | Tour 나머지(Functions/Classes/Null safety), CLI 프로그램 |
| 2026-07-10 | 개념 예습(2~3단계 선행 문답): JVM(V8/Node 비유·바이트코드·JIT·GC·Write Once Run Anywhere)·Spring/Spring Boot(React/Next.js)·DI와 어노테이션·Actuator·SDD → [학습노트 HTML](notes/2026-07-10-jvm-spring-for-frontend.html)로 정리 | 예습이라 퀴즈 없음 | 커리큘럼 순서대로 1단계 Kotlin Tour·CLI 실습 계속 |
| 2026-07-10 | 학습노트 코드 예시를 **Java / Kotlin / TS 3탭**으로 확장 + GitHub Pages 배포. Java↔Kotlin 문법 차이(생성자 주입·`val`=final·`fun` 식 본문·Kotlin all-open/final 함정) 정리, TS 탭은 **NestJS** 대응(`@Injectable`·`@Controller`/`@Get`/`@Param`, 생성자 주입=파라미터 프로퍼티)임을 확인 | 퀴즈 없음. 기억할 것: ① Kotlin 클래스 기본 final → `kotlin-spring`(all-open) 플러그인 필요 ② NestJS는 Angular/Spring 계보라 Spring과 거의 1:1 | 1단계 Kotlin Tour·CLI 실습 계속 |

## 약한 부분 누적 (복습 대상)

- (퀴즈에서 틀리거나 헷갈린 개념을 여기에 누적)
