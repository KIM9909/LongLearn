# 1. 동기화 (Synchronization)

## 1.1 동기화가 필요한 이유

<img src="images\동기화.png" width="500" height="250"/>

프로세스가 동시에 같은 공유자원에 접근할 때 접근 순서를 보장해주는 과정이 동기화이다.

### Race Condition (경쟁 상태)

- 정의: 여러 프로세스가 동시에 공유 데이터에 접근할 때 실행 순서에 따라 결과가 달라지는 상황
- 문제점: 데이터의 일관성이 깨질 수 있음

### Critical Section (임계 영역)

```
do {
    Entry section       // 진입 구역
    Critical section    // 임계 영역 (공유 자원 접근)
    Exit section        // 출구 구역
    Remainder section   // 나머지 구역
} while(1);
```

### 동기화 조건

공유 자원의 접근 순서를 제어하기 위해서 만족해야할 3가지 조건

1. **상호배제(Mutual Exclusion)**: 하나의 프로세스만 임계 영역 실행
2. **진행(Process)**: 데드락 방지, 프로세스가 작업을 진행할 수 있어야 함
3. **한정 대기(Bounded Watiting)**: 무한 대기 방지

# 2. 동기화 기법

## 2.1 뮤텍스 (Mutex)

<img src="images\뮤텍스.png" width="500" height="250"/>

Ex. 음식점들이 공용 화장실(공유 자원) 관리 차원에서 화장실을 잠궈두고(Locking) 다니는 것

### 특징

- **정의**: MUT와 EX의 합성어, 상호배제 메커니즘
- **값**: 0또는 1(이진 세마포어와 유사)
- **소유권**: 키를 소유한 스레드를 제외한 다른 스레드는 키를 가진 스레드 즉, 임계 영역 안의 스레드의 작업에 간섭할 수 없음

### 동작 방식

```c
mutex = 1;

void lock() {
    while (mutex != 1) {
        // 대기
    }
    mutex = 0; // 락 획득
}

void unlock() {
    mutex = 1; // 락 해제
}
```

### 장점

- 간단한 구현
- busy-waiting 방지
- 소유권 개념으로 안전성 보장

### 단점

- 하나의 스레드만 접근 가능
- 우선순위 역전 문제 가능성

## 2.2 세마포어 (Semaphore)

<img src="images\세마포어.png" width="500" height="250"/>

Ex. 화장실이 여러 개 있고, 화장실 입구에는 현재 빈 화장실의 개수를 알려주는 전광판이 있는 식당

### 특징

- **정의**: 동시에 리소스에 접근 허용이 가능한 개수를 가진 counter
- **값**: 0 이상의 정수 (사용 가능한 자원 수)
- **소유권 없음**: 세마포어는 소유 개념이 없기 때문에 소유하고 있지 않은 스레드도 세마포어 해제 가능

### 동작 방식

```c
semaphore S = n; // 자원 개수로 초기화

void wait(S) {     // P 연산
    S.value--;
    if (S.value < 0) {
        // 프로세스를 대기 큐에 추가
        block();
    }
}

void signal(S) {   // V 연산
    S.value++;
    if (S.value <= 0) {
        // 대기 큐에서 프로세스 제거
        wakeup();
    }
}
```

### 세마포어 종류

- **이진 세마포어**: 뮤텍스와 같이 임계 영역에 두 개의 스레드만 들어옴 (1 또는 0으로 초기화)
- **계수 세마포어**: 여러 개의 스레드를 들어오게 할 수 있음 (사용 가능한 자원 수로 초기화)

## 2.3 모니터 (Monitor)

<img src="images\Monitor.png" width="600" height="300"/>

**동시 수행 중인 프로세스** 사이에서 **추상 데이터의 안전한 공유**를 보장하기 위한 **High-level 동기화** 구조

### 특징

- **정의**: 공유 객체, 임계 영역이 코딩된 프로시저, 초기화 코드로 구성된 모듈
- **접근 제어**: 프로시저를 통해서만 공유 데이터에 접근 가능
- **자동 상호배제**: 모니터는 락(Lock)을 걸 필요가 없다

### 장점

- 모니터 내부를 몰라도 상호배제를 쉽게 구현할 수 있기 때문에 사용하기 편리함
- 프로그래머가 직접 동기화를 관리할 필요 없음
- 자바의 스레드 관련 라이브러리와 그 기능(wait, join, notify 등)을 생각하면 됨

## 2.4 뮤텍스 vs 세마포어 vs 모니터

| 구분            | 뮤텍스          | 세마포어       | 모니터    |
| --------------- | --------------- | -------------- | --------- |
| **동기화 대상** | 1개             | 여러 개        | 1개       |
| **소유권**      | 있음            | 없음           | 있음      |
| **구현 복잡도** | 중간            | 중간           | 높음      |
| **사용 편의성** | 중간            | 어려움         | 쉬움      |
| **적용 분야**   | 일반적 상호배제 | 자원 개수 제한 | 고급 언어 |

## 핵심 요약

### 동기화

- **목적**: 공유 자원에 대한 안전한 접근 보장
- **핵심 기법**: 뮤텍스(1:1), 세마포어(1:N), 모니터(고급)
- **선택 기준**: 동기화 대상 수와 구현 편의성
