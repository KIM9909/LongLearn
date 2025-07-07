# 2. 캐시 메모리 구조와 동작 원리

## 2.1 캐시 메모리 기본 개념

<img src="images\메모리 계층 구조.png" width="500" height="300"/>

**캐시 메모리**는 CPU와 메인 메모리 사이의 속도 차이를 줄이기 위한 고속 임시 저장소이다. CPU가 필요로 할 가능성이 높은 데이터를 미리 저장해두어 평균 메모리 접근 시간을 단축시킨다.

### 캐시가 필요한 이유

- 속도 격차 : CPU는 매우 빠르지만 메인 메모리는 상대적으로 느림
- 비용 문제 : 빠른 매모리(SRAM)은 비싸고, 큰 용량의 메모리(DRAM)은 느림
- 80-20 법칙 : 프로그램의 80% 시간을 20% 코드에서 소비

### 캐시 계층 구조

```
CPU ↔ L1 Cache ↔ L2 Cache ↔ L3 Cache ↔ Main Memory ↔ Storage
```

- **L1 캐시**: 32-64KB, 1-2 클럭, CPU 내부, 명령어(I$)와 데이터(D$) 분리
- **L2 캐시**: 256KB-1MB, 3-10 클럭, CPU 가까이 또는 내부
- **L3 캐시**: 4-32MB, 10-30 클럭, 여러 코어가 공유

## 2.2 지역성의 원리 (Principle of Locality)

<img src="images\메모리 접근 패턴.png" width="500" height="300"/>

캐시가 높은 효율을 보이는 이유는 프로그램이 지역성의 원리를 따르기 때문이다.

### 시간적 지역성 (Temporal Locality)

- 의미: 최근에 접근한 데이터에 다시 접근할 가능성이 높음
- 예시
  - 반복문의 인덱스 변수 `i`
  - 함수 내 지역 변수들
  - 자주 호출되는 함수의 코드

### 공간적 지역성 (Spatial Locality)

- 의미: 최근 접근한 데이터 근처의 데이터에 접근할 가능성이 높음
- 예시
  - 배열 원소들의 순차적 접근 (array[0], array[1], array[2]...)
  - 구조체 멤버들의 연속 접근
  - 순차적 명령어 실행

## 2.3 캐시 동작 원리

### 캐시 히트 vs 미스

- 캐시 히트 : 찾는 데이터가 캐시에 있음 -> 빠른 응답
- 캐시 미스 : 찾는 데이터가 캐시에 없음 -> 메인 메모리에서 가져옴

### 캐시 미스 유형

```
Cold Miss (Compulsory Miss): 처음 접근하는 데이터 (불가피)
Conflict Miss: 캐시 매핑 방식으로 인한 충돌
Capacity Miss: 캐시 용량 부족으로 인한 교체
```

## 2.4 캐시 매핑 방식

<img src="images\캐시 매핑 방식 (Direct Mapping).png" width="500" height="300"/>

### Direct Mapped Cache

```
방식: 각 메모리 블록이 캐시의 정확히 한 위치에만 저장 가능
주소 구성: Tag + Index + Offset
장점: 하드웨어 구현 간단, 빠른 접근
단점: Conflict Miss 발생 가능성 높음
```

<img src="images\캐시 매핑 방식 (Set Associate).png" width="500" height="300"/>

### Set Associative Cache

```
방식: N-way Set Associative (보통 2-way, 4-way)
특징: 각 세트 내에서는 어느 위치든 저장 가능
장점: Direct Mapped보다 Conflict Miss 적음
단점: 하드웨어 복잡도 증가
```

<img src="images\캐시 매핑 방식 (Full Associate).png" width="500" height="300"/>

### Fully Associative Cache

```
방식: 메모리 블록이 캐시의 어느 위치든 저장 가능
장점: Conflict Miss 없음, 최고의 유연성
단점: 복잡한 하드웨어, 비용 증가
```

## 2.5 캐시 교체 및 쓰기 정책

### 교체 정책

- LRU(Least Recently Used) : 가장 오래전 사용된 블록 교체
- FIFO(First In First Out) : 가장 먼저 들어온 블록 교체
- Random : 무작위로 선책하여 교체

### 쓰기 정책

<img src="images\write-through vs write-back.png" width="500" height="300"/>

#### Write Through

- **동작**: 캐시와 메인 메모리에 동시 쓰기
- **장점**: 데이터 일관성 보장, 구현 단순
- **단점**: 쓰기 성능 저하

#### Write Back

- **동작**: 캐시에만 쓰고, 교체될 때 메모리에 반영
- **장점**: 빠른 쓰기 성능, 메모리 대역폭 절약
- **단점**: 복잡한 구현, Dirty Bit 필요

## 2.6 멀티코어 환경의 캐시 일관성

<img src="images\MESI 프로토콜.png" width="500" height="300"/>

### 캐시 일관성 문제

여러 코어가 같은 메모리 위치를 각자의 캐시에 저장할 때, 한 코어가 값을 변경하면 다른 코어들의 캐시는 구식 데이터를 가지게 되는 문제

### MESI 프로토콜

각 캐시 블록이 4가지 상태 중 하나를 가진다.

- M (Modified) : 이 캐시에서만 수정됨, 메모리와 다름
- E (Exclusive) : 이 캐시에만 있음, 메모리와 같음
- S (Shared) : 여러 캐시에 복사본 존재, 메모리와 같음
- I (Invalid) : 무효한 데이터, 사용 불가

### 스누핑 프로토콜

모든 캐시가 버스를 감시하여 다른 캐시의 메모리 접근을 관찰하고, 필요시 자신의 캐시 상태를 업데이트 한다.

## 핵심 요약

### 캐시 메모리의 핵심 원리

- **지역성**: 시간적, 공간적 지역성이 캐시 효율의 기반
- **계층 구조**: L1/L2/L3 캐시로 속도와 용량의 균형
- **매핑 방식**: 성능과 복잡도 사이의 트레이드오프
- **일관성**: 멀티코어에서 캐시 일관성 유지가 필수
