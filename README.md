# LongLearn

```
개발자의 길을 가기 위한 정도(正道)를 여기 롱런에서 기록하고 추구합니다.

수박 겉핥기식이 아닌, How보다 What과 Why를 탐구하는 자세로 기본 개념부터 조금 딥한 내용까지 스스로 학습하는 능력을 키우는 공간입니다.
단순히 "어떻게 쓰는가"에 머물지 않고, "왜 이 기술이 필요한가"와 "이것의 본질은 무엇인가"를 끊임없이 질문하며 탐구합니다.

빠른 습득보다는 확실한 이해를, 많은 양보다는 깊은 깨달음을, 트렌드 쫓기보다는 기본기 다지기를 우선으로 합니다.
기술의 표면이 아닌 내부 동작 원리를 이해하고, 문제의 근본 원인을 파악하며, 스스로 답을 찾아가는 진정한 개발자로 성장하는 것이 목표입니다.

천천히, 바르게, 꾸준히, 멀리.
LongLearn
```

---

---

## 1. 컴퓨터 시스템 기초 (Computer System Fundamentals)

### 1.1 컴퓨터 구조 (Computer Architecture)

🟢 Basic

- [CPU, 메모리, 저장장치의 기본 구조](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.1-computer-architecture/basic/basic-structure.md)
- [폰 노이만 구조와 하버드 구조](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.1-computer-architecture/basic/von-neumann-harvard.md)
- [명령어 집합 구조 (ISA)](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.1-computer-architecture/basic/instruction-set.md)

🟡 Intermediate

- [파이프라인과 병렬 처리](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.1-computer-architecture/intermediate/pipeline-parallel.md)
- [캐시 메모리 구조와 동작 원리](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.1-computer-architecture/intermediate/cache-memory.md)

🔴 Advanced

- [브랜치 예측 (Branch Prediction)]()
- [Out-of-Order 실행]()
- [멀티코어 프로세서 아키텍처]()
- [메모리 일관성 모델]()

🟣 Expert

- [CPU 캐시 최적화 기법]()
- [NUMA 아키텍처]()
- [하드웨어 보안 (Spectre, Meltdown)]()

### 1.2 운영체제 (Operating System)

🟢 Basic

- [운영체제의 역할과 구조](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/basic/os-structure.md)
- [프로세스와 스레드](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/basic/process-thread.md)
- [프로세스 상태와 스케줄링](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/basic/process-scheduling.md)

🟡 Intermediate

- [동기화 (Mutex, Semaphore, Monitor)](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/intermediate/synchronization.md)
- [데드락과 해결 방법](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/intermediate/deadlock.md)
- [가상 메모리와 페이징](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/intermediate/virtual-memory.md)
- [파일 시스템](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.2-operating-system/intermediate/file-system.md)

🔴 Advanced

- [페이지 교체 알고리즘]()
- [메모리 단편화와 해결 방법]()
- [I/O 스케줄링]()
- [인터럽트와 시스템 콜]()
- [리눅스 커널 구조]()

🟣 Expert

- [커널 모듈 개발]()
- [시스템 성능 튜닝]()
- [컨테이너 기술의 내부 구조]()
- [eBPF와 고급 시스템 프로그래밍]()

### 1.3 시스템 성능과 최적화 (System Performance & Optimization)

🟢 Basic

- [성능 측정 지표 (Latency, Throughput, QPS)](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/basic/performance-metrics.md)
- [프로파일링 도구 사용법](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/basic/profiling-tools.md)
- [기본적인 병목 지점 식별](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/basic/bottleneck-identification.md)

🟡 Intermediate

- [메모리 프로파일링](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/intermediate/memory-profiling.md)
- [CPU 사용률 분석](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/intermediate/cpu-analysis.md)
- [I/O 성능 최적화](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/intermediate/io-optimization.md)
- [네트워크 성능 튜닝](https://github.com/KIM9909/LongLearn/blob/master/01-computer-system/1.3-performance-optimization/intermediate/network-tuning.md)

🔴 Advanced

- [시스템 콜 최적화]()
- [메모리 접근 패턴 최적화]()
- [락프리 프로그래밍]()
- [벤치마킹 방법론]()

🟣 Expert

- [커널 수준 최적화]()
- [하드웨어 특성을 활용한 최적화]()
- [대규모 시스템 성능 아키텍처]()

## 2. 프로그래밍 언어 (Programming Languages)

### 2.1 Java

🟢 Basic

- [기본 문법과 데이터 타입]()
- [객체지향 프로그래밍 (클래스, 상속, 다형성, 캡슐화)]()
- [컬렉션 프레임워크]()
- [예외 처리]()
- [제네릭스]()

🟡 Intermediate

- [스트림 API와 람다 표현식]()
- [함수형 인터페이스]()
- [리플렉션과 어노테이션]()
- [I/O와 NIO]()
- [직렬화]()

🔴 Advanced

- [JVM 메모리 구조 (Heap, Stack, Method Area)]()
- [가비지 컬렉션 원리와 튜닝]()
- [클래스 로딩 메커니즘]()
- [동시성 프로그래밍 (Thread, Executor, CompletableFuture)]()
- [메모리 모델과 가시성]()

🟣 Expert

- [JVM 인터널스와 바이트코드]()
- [JIT 컴파일러 최적화]()
- [커스텀 가비지 컬렉터]()
- [네이티브 메소드와 JNI]()
- [JVM 튜닝과 성능 분석]()
- [GraalVM과 네이티브 이미지]()

### 2.2 React

🟢 Basic

- [React 기본 개념과 JSX]()
- [컴포넌트와 Props]()
- [State와 이벤트 처리]()
- [리스트와 조건부 렌더링]()
- [폼 처리와 제어 컴포넌트]()

🟡 Intermediate

- [React Hooks (useState, useEffect, useContext)]()
- [커스텀 Hooks]()
- [상태 관리 (Context API, useReducer)]()
- [React Router]()
- [성능 최적화 (memo, useMemo, useCallback)]()

🔴 Advanced

- [고급 Hooks (useRef, useImperativeHandle, useLayoutEffect)]()
- [렌더링 최적화와 가상 DOM]()
- [서버사이드 렌더링 (SSR)]()
- [정적 사이트 생성 (SSG)]()
- [에러 바운더리와 에러 처리]()

🟣 Expert

- [React 내부 구조와 Fiber 아키텍처]()
- [동시성 기능 (Concurrent Features)]()
- [커스텀 렌더러 개발]()
- [React DevTools 고급 활용]()
- [성능 프로파일링과 최적화]()

### 2.3 JavaScript & TypeScript

🟢 Basic

- [JavaScript 기본 문법]()
- [함수와 스코프]()
- [객체와 배열]()
- [DOM 조작]()
- [TypeScript 기본 타입 시스템]()

🟡 Intermediate

- [클로저와 호이스팅]()
- [프로토타입과 상속]()
- [비동기 프로그래밍 (Promise, async/await)]()
- [모듈 시스템]()
- [TypeScript 고급 타입]()

🔴 Advanced

- [이벤트 루프와 마이크로태스크]()
- [메모리 관리와 가비지 컬렉션]()
- [웹 워커와 서비스 워커]()
- [TypeScript 컴파일러 API]()

🟣 Expert

- [V8 엔진 내부 구조]()
- [JIT 컴파일레이션]()
- [성능 최적화 기법]()
- [커스텀 TypeScript 트랜스포머]()

### 2.4 Go

🟢 Basic

- [기본 문법과 데이터 타입]()
- [구조체와 메서드]()
- [인터페이스]()
- [슬라이스와 맵]()
- [에러 처리]()

🟡 Intermediate

- [고루틴과 채널]()
- [컨텍스트 패키지]()
- [리플렉션]()
- [테스트와 벤치마킹]()

🔴 Advanced

- [고루틴 스케줄러]()
- [메모리 모델]()
- [cgo와 C 연동]()
- [어셈블리 최적화]()

🟣 Expert

- [런타임 내부 구조]()
- [가비지 컬렉터 구현]()
- [컴파일러 최적화]()
- [시스템 프로그래밍]()

## 3. 자료구조 & 알고리즘 (Data Structures & Algorithms)

### 3.1 자료구조

🟢 Basic

- [배열과 동적 배열]()
- [연결 리스트 (단일, 이중, 원형)]()
- [스택과 큐]()
- [해시 테이블 기본]()

🟡 Intermediate

- [이진 트리와 이진 탐색 트리]()
- [힙과 우선순위 큐]()
- [그래프 표현 (인접 리스트, 인접 행렬)]()
- [트라이 (Trie)]()

🔴 Advanced

- [균형 이진 탐색 트리 (AVL, Red-Black)]()
- [B-Tree와 B+Tree]()
- [해시 충돌 해결 (체이닝, 오픈 어드레싱)]()
- [유니온 파인드 (Disjoint Set)]()

🟣 Expert

- [퍼시스턴트 자료구조]()
- [세그먼트 트리와 펜윅 트리]()
- [스킵 리스트]()
- [LSM Tree]()

### 3.2 알고리즘

🟢 Basic

- [시간 복잡도와 공간 복잡도 (Big O)]()
- [기본 정렬 (버블, 선택, 삽입)]()
- [선형 탐색과 이진 탐색]()
- [재귀와 반복]()

🟡 Intermediate

- [고급 정렬 (병합, 퀵, 힙 정렬)]()
- [BFS와 DFS]()
- [백트래킹]()
- [그리디 알고리즘]()

🔴 Advanced

- [동적 프로그래밍]()
- [분할 정복]()
- [최단 경로 (다익스트라, 벨만-포드, 플로이드-와샬)]()
- [최소 신장 트리 (크루스칼, 프림)]()
- [네트워크 플로우]()

🟣 Expert

- [고급 문자열 알고리즘 (KMP, Rabin-Karp, Z 알고리즘)]()
- [기하 알고리즘]()
- [수론 알고리즘]()
- [근사 알고리즘]()
- [병렬 알고리즘]()

## 4. 데이터베이스 (Database)

### 4.1 관계형 데이터베이스

🟢 Basic

- [데이터베이스 기본 개념]()
- [테이블, 레코드, 필드]()
- [기본 SQL (SELECT, INSERT, UPDATE, DELETE)]()
- [기본 키와 외래 키]()

🟡 Intermediate

- [조인 (INNER, LEFT, RIGHT, FULL OUTER)]()
- [서브쿼리와 CTE]()
- [집계 함수와 윈도우 함수]()
- [뷰와 저장 프로시저]()
- [인덱스 기본]()

🔴 Advanced

- [쿼리 실행 계획과 최적화]()
- [인덱스 설계와 튜닝]()
- [정규화와 반정규화]()
- [트랜잭션과 격리 수준]()
- [락킹과 동시성 제어]()

🟣 Expert

- [쿼리 옵티마이저 내부 구조]()
- [고급 인덱싱 전략]()
- [파티셔닝과 샤딩]()
- [백업과 복구 전략]()
- [데이터베이스 내부 구조]()

### 4.2 NoSQL

🟢 Basic

- [NoSQL 개념과 종류]()
- [MongoDB 기본 CRUD]()
- [Redis 기본 데이터 타입]()

🟡 Intermediate

- [MongoDB 집계 파이프라인]()
- [Redis 고급 데이터 구조]()
- [일관성 모델 (Eventual Consistency)]()

🔴 Advanced

- [CAP 정리와 트레이드오프]()
- [분산 데이터베이스 설계]()
- [샤딩과 레플리케이션]()

🟣 Expert

- [분산 합의 알고리즘 (Raft, Paxos)]()
- [벡터 클록과 논리적 시계]()
- [분산 트랜잭션]()

### 4.3 데이터 모델링

🟢 Basic

- [ER 다이어그램]()
- [엔터티와 관계]()
- [속성과 도메인]()

🟡 Intermediate

- [개념적, 논리적, 물리적 모델링]()
- [정규화 과정]()
- [데이터 무결성]()

🔴 Advanced

- [성능을 고려한 모델링]()
- [시간 데이터 모델링]()
- [계층형 데이터 모델링]()

🟣 Expert

- [대용량 데이터 모델링]()
- [실시간 분석을 위한 모델링]()
- [이벤트 소싱 모델]()

## 5. 백엔드 개발 (Backend Development)

### 5.1 Spring Framework

🟢 Basic

- [Spring Core (IoC, DI)]()
- [Spring Bean과 컨테이너]()
- [기본 어노테이션]()
- [Spring MVC 기본]()

🟡 Intermediate

- [AOP (Aspect Oriented Programming)]()
- [Spring Security 기본]()
- [Spring Data JPA]()
- [트랜잭션 관리]()
- [프로파일과 설정]()

🔴 Advanced

- [Spring WebFlux와 리액티브 프로그래밍]()
- [Spring Batch]()
- [커스텀 스타터]()
- [고급 Security 설정]()
- [성능 최적화]()

🟣 Expert

- [Spring 내부 구조와 확장]()
- [커스텀 어노테이션과 AOP]()
- [Spring Cloud와 마이크로서비스]()
- [Native Image 최적화]()

### 5.2 JPA & Hibernate

🟢 Basic

- [JPA 기본 개념]()
- [엔터티 매핑]()
- [기본 CRUD 연산]()
- [관계 매핑 (OneToOne, OneToMany, ManyToMany)]()

🟡 Intermediate

- [JPQL과 Criteria API]()
- [영속성 컨텍스트]()
- [플러시와 detach]()
- [지연 로딩과 즉시 로딩]()

🔴 Advanced

- [N+1 문제와 해결]()
- [페치 조인과 배치 페치]()
- [2차 캐시]()
- [벌크 연산]()

🟣 Expert

- [Hibernate 내부 구조]()
- [커스텀 타입과 컨버터]()
- [멀티 테넌시]()
- [성능 튜닝과 최적화]()

### 5.3 API 설계

🟢 Basic

- [RESTful API 원칙]()
- [HTTP 메서드와 상태 코드]()
- [JSON과 직렬화]()
- [기본 에러 처리]()

🟡 Intermediate

- [API 버전 관리]()
- [페이지네이션]()
- [필터링과 정렬]()
- [검증과 예외 처리]()

🔴 Advanced

- [HATEOAS]()
- [GraphQL 기본]()
- [gRPC 프로토콜]()
- [API 게이트웨이]()

🟣 Expert

- [API 성능 최적화]()
- [고급 GraphQL (Federation, Subscription)]()
- [OpenAPI 스펙과 코드 생성]()
- [API 보안 고급 기법]()

### 5.4 테스트

🟢 Basic

- [단위 테스트 기본]()
- [JUnit과 AssertJ]()
- [Mock 객체 기본]()
- [테스트 더블]()

🟡 Intermediate

- [통합 테스트]()
- [테스트 슬라이스 (@WebMvcTest, @DataJpaTest)]()
- [Mockito 고급 기능]()
- [테스트 환경 구성]()

🔴 Advanced

- [TDD와 BDD]()
- [테스트 컨테이너]()
- [성능 테스트]()
- [카오스 엔지니어링 기본]()

🟣 Expert

- [고급 테스트 전략]()
- [대규모 테스트 자동화]()
- [Property-based Testing]()
- [Mutation Testing]()

## 6. 네트워크 & 웹 (Network & Web)

### 6.1 네트워크 기초

🟢 Basic

- [OSI 7계층 모델]()
- [TCP/IP 모델]()
- [IP 주소와 서브넷]()
- [기본 네트워크 명령어]()

🟡 Intermediate

- [TCP vs UDP]()
- [HTTP/HTTPS 프로토콜]()
- [DNS 동작 원리]()
- [라우팅 기본]()

🔴 Advanced

- [네트워크 성능 최적화]()
- [로드 밸런싱]()
- [CDN 구조와 활용]()
- [QUIC와 HTTP/3]()

🟣 Expert

- [네트워크 프로토콜 설계]()
- [소켓 프로그래밍 고급]()
- [네트워크 보안 고급]()
- [SDN과 네트워크 가상화]()

### 6.2 웹 통신

🟢 Basic

- [브라우저 동작 원리]()
- [웹 서버와 WAS]()
- [세션과 쿠키]()
- [CORS 기본]()

🟡 Intermediate

- [웹 캐싱 전략]()
- [압축과 최적화]()
- [웹소켓과 실시간 통신]()
- [서버사이드 렌더링 vs 클라이언트사이드 렌더링]()

🔴 Advanced

- [HTTP/2와 서버 푸시]()
- [웹 성능 최적화]()
- [프로그레시브 웹 앱 (PWA)]()
- [마이크로프론트엔드]()

🟣 Expert

- [브라우저 엔진 내부 구조]()
- [웹 표준과 호환성]()
- [고급 웹 보안]()
- [엣지 컴퓨팅]()

### 6.3 보안

🟢 Basic

- [인증과 인가]()
- [패스워드 해싱]()
- [HTTPS 기본]()
- [기본 웹 취약점 (XSS, CSRF, SQL Injection)]()

🟡 Intermediate

- [JWT와 OAuth 2.0]()
- [세션 관리]()
- [API 보안]()
- [보안 헤더]()

🔴 Advanced

- [고급 인증 방식 (SAML, OpenID Connect)]()
- [암호화와 디지털 서명]()
- [보안 아키텍처 설계]()
- [펜테스트 기본]()

🟣 Expert

- [암호학 고급 이론]()
- [제로 트러스트 아키텍처]()
- [블록체인과 분산 신원]()
- [하드웨어 보안 모듈]()

## 7. 시스템 아키텍처 (System Architecture)

### 7.1 아키텍처 패턴

🟢 Basic

- [레이어드 아키텍처]()
- [MVC 패턴]()
- [모놀리식 아키텍처]()
- [기본 디자인 패턴]()

🟡 Intermediate

- [마이크로서비스 아키텍처]()
- [이벤트 기반 아키텍처]()
- [CQRS 패턴]()
- [헥사고날 아키텍처]()

🔴 Advanced

- [서비스 메시]()
- [이벤트 소싱]()
- [사가 패턴]()
- [분산 모놀리스 회피]()

🟣 Expert

- [아키텍처 결정 레코드 (ADR)]()
- [진화적 아키텍처]()
- [카오스 엔지니어링]()
- [시스템 사고와 복잡성 관리]()

### 7.2 DDD (Domain Driven Design)

🟢 Basic

- [도메인과 서브도메인]()
- [엔터티와 값 객체]()
- [애그리거트]()
- [도메인 서비스]()

🟡 Intermediate

- [바운디드 컨텍스트]()
- [컨텍스트 맵]()
- [도메인 이벤트]()
- [리포지토리 패턴]()

🔴 Advanced

- [전략적 설계]()
- [이벤트 스토밍]()
- [헥사고날 아키텍처와 DDD]()
- [레거시 시스템 통합]()

🟣 Expert

- [복잡한 도메인 모델링]()
- [분산 도메인 모델]()
- [DDD와 마이크로서비스]()
- [도메인 전문가와의 협업]()

### 7.3 확장성과 성능

🟢 Basic

- [수직 확장 vs 수평 확장]()
- [로드 밸런싱 기본]()
- [캐시 기본 전략]()
- [성능 지표]()

🟡 Intermediate

- [데이터베이스 확장 (읽기 복제본, 샤딩)]()
- [CDN 활용]()
- [비동기 처리]()
- [메시지 큐]()

🔴 Advanced

- [분산 캐시]()
- [이벤트 기반 확장]()
- [백프레셔와 서킷 브레이커]()
- [글로벌 분산 시스템]()

🟣 Expert

- [대규모 시스템 설계]()
- [분산 시스템 이론]()
- [일관성과 가용성 트레이드오프]()
- [실시간 시스템 설계]()

## 8. DevOps & 클라우드 (DevOps & Cloud)

### 8.1 컨테이너화

🟢 Basic

- [Docker 기본 개념]()
- [이미지와 컨테이너]()
- [Dockerfile 작성]()
- [기본 Docker 명령어]()

🟡 Intermediate

- [Docker Compose]()
- [멀티 스테이지 빌드]()
- [컨테이너 네트워킹]()
- [볼륨과 데이터 관리]()

🔴 Advanced

- [Kubernetes 기본 개념]()
- [Pod, Service, Deployment]()
- [ConfigMap과 Secret]()
- [인그레스와 로드 밸런싱]()

🟣 Expert

- [Kubernetes 고급 운영]()
- [커스텀 리소스와 오퍼레이터]()
- [서비스 메시 (Istio)]()
- [컨테이너 보안]()

### 8.2 CI/CD

🟢 Basic

- [버전 관리 (Git)]()
- [기본 빌드 자동화]()
- [단순한 배포 파이프라인]()

🟡 Intermediate

- [GitHub Actions]()
- [테스트 자동화]()
- [아티팩트 관리]()
- [환경별 배포]()

🔴 Advanced

- [고급 배포 전략 (Blue-Green, Canary, Rolling)]()
- [인프라스트럭처 as 코드]()
- [보안 스캔 통합]()
- [성능 테스트 자동화]()

🟣 Expert

- [GitOps]()
- [멀티 클라우드 배포]()
- [복잡한 파이프라인 설계]()
- [컴플라이언스 자동화]()

### 8.3 클라우드 플랫폼

🟢 Basic

- [클라우드 기본 개념 (IaaS, PaaS, SaaS)]()
- [AWS 기본 서비스 (EC2, S3, RDS)]()
- [기본 네트워킹 (VPC)]()

🟡 Intermediate

- [로드 밸런서와 오토 스케일링]()
- [데이터베이스 서비스]()
- [모니터링과 로깅]()
- [IAM과 보안]()

🔴 Advanced

- [서버리스 아키텍처 (Lambda, API Gateway)]()
- [마이크로서비스 운영]()
- [비용 최적화]()
- [멀티 리전 설계]()

🟣 Expert

- [클라우드 네이티브 아키텍처]()
- [하이브리드 클라우드]()
- [클라우드 마이그레이션 전략]()
- [FinOps]()

### 8.4 모니터링

🟢 Basic

- [기본 메트릭 (CPU, 메모리, 디스크)]()
- [로그 기본]()
- [업타임 모니터링]()

🟡 Intermediate

- [애플리케이션 성능 모니터링 (APM)]()
- [구조화된 로깅]()
- [알림 설정]()
- [대시보드 구성]()

🔴 Advanced

- [분산 추적 (Distributed Tracing)]()
- [메트릭과 로그 상관관계]()
- [이상 탐지]()
- [SRE와 SLI/SLO]()

🟣 Expert

- [관찰 가능성 (Observability) 전략]()
- [대규모 모니터링 시스템]()
- [머신러닝 기반 모니터링]()
- [카오스 엔지니어링]()

## 9. 소프트웨어 공학 (Software Engineering)

### 9.1 디자인 패턴

🟢 Basic

- [생성 패턴 (Singleton, Factory, Builder)]()
- [구조 패턴 (Adapter, Decorator, Facade)]()
- [행동 패턴 (Observer, Strategy, Command)]()

🟡 Intermediate

- [아키텍처 패턴 (MVC, MVP, MVVM)]()
- [동시성 패턴]()
- [함수형 패턴]()

🔴 Advanced

- [엔터프라이즈 패턴]()
- [분산 시스템 패턴]()
- [리액티브 패턴]()

🟣 Expert

- [패턴의 철학과 원리]()
- [언어별 패턴 구현]()
- [안티패턴과 리팩토링]()
- [새로운 패턴 설계]()

### 9.2 소프트웨어 설계 원칙

🟢 Basic

- [SOLID 원칙]()
- [DRY, KISS, YAGNI]()
- [코딩 컨벤션]()

🟡 Intermediate

- [클린 코드 원칙]()
- [의존성 관리]()
- [인터페이스 설계]()

🔴 Advanced

- [도메인 모델링]()
- [아키텍처 결정]()
- [기술 부채 관리]()

🟣 Expert

- [소프트웨어 품질 메트릭]()
- [진화적 설계]()
- [레거시 코드 개선]()
- [아키텍처 거버넌스]()

### 9.3 개발 방법론

🟢 Basic

- [애자일 기본 원칙]()
- [스크럼 프레임워크]()
- [칸반 기본]()

🟡 Intermediate

- [TDD와 BDD]()
- [지속적 통합]()
- [페어 프로그래밍]()

🔴 Advanced

- [린 소프트웨어 개발]()
- [DevOps 문화]()
- [사이트 신뢰성 엔지니어링 (SRE)]()

🟣 Expert

- [조직 설계와 팀 구조]()
- [기술 리더십]()
- [변화 관리]()
- [학습 조직]()

### 9.4 코드 품질

🟢 Basic

- [코드 리뷰 기본]()
- [정적 분석 도구]()
- [코딩 스타일 가이드]()

🟡 Intermediate

- [리팩토링 기법]()
- [코드 메트릭]()
- [기술 부채 식별]()

🔴 Advanced

- [아키텍처 품질 속성]()
- [자동화된 품질 게이트]()
- [코드 스멜 탐지]()

🟣 Expert

- [품질 문화 구축]()
- [메트릭 기반 개선]()
- [대규모 코드베이스 관리]()
- [품질 엔지니어링]()
