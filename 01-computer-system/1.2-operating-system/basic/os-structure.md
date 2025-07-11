# 1. 운영체제의 기본 개념

## 1.1 운영체제란?

<img src="images\운영체제 구조.png" width="500" height="300"/>

**운영체제(Operating System, OS)** 는 컴퓨터 하드웨어와 응용 프로그램 사이에서 **중재자 역할**을 하는 시스템 소프트웨어이다. 사용자가 컴퓨터를 편리하게 사용할 수 있도록 하드웨어를 관리하고 다양한 서비스를 제공한다.

### 운영체제의 정의

- **하드웨어 관리**: CPU, 메모리, 저장장치, 입출력 장치 등의 시스템 자원 관리
- **서비스 제공**: 응용 프로그램이 하드웨어를 사용할 수 있도록 인터페이스 제공
- **추상화**: 복잡한 하드웨어를 단순하고 일관된 인터페이스로 제공

## 1.2 운영체제의 위치와 역할

```
사용자 (User)
    ↓
응용 프로그램 (Application Programs)
    ↓
운영체제 (Operating System)
    ↓
하드웨어 (Hardware)
```

# 2. 운영체제의 주요 역할

## 2.1 자원 관리 (Resource Management)

<img src="images\운영체제 자원 관리.png" width="500" height="300"/>

### CPU 관리 (프로세스 스케줄링)

- **멀티태스킹** : 여러 프로그램이 동시에 실행되는 것처럼 보이게 함
- **스케줄링** : 어떤 프로세스가 CPU를 언제, 얼마나 사용할지 결정
- **시분할** : 짧은 시간 단위로 CPU 사용권을 번갈아 할당

### 메모리 관리

- **메모리 할당** : 각 프로그램에 필요한 메모리 공간 할당
- **가상 메모리** : 물리 메모리보다 큰 메모리 공간을 제공하는 기술
- **메모리 보호** : 프로세스가 다른 프로세스의 메모리에 접근하지 못하도록 보호

### 파일 시스템 관리

- **파일 생성/삭제**: 파일과 디렉터리의 생성, 삭제, 이동
- **접근 권한**: 파일에 대한 읽기, 쓰기, 실행 권한 관리
- **저장 공간 관리**: 디스크 공간의 효율적 사용

### 입출력 장치 관리

- **디바이스 드라이버**: 각종 하드웨어 장치와의 통신 인터페이스
- **버퍼링**: 입출력 속도 차이를 완화하는 임시 저장 공간
- **스풀링**: 느린 장치(프린터 등)의 효율적 사용

## 2.2 하드웨어 추상화

<img src="images\하드웨어 추상화 계층.png" width="500" height="300"/>

운영체제는 복잡하고 다양한 하드웨어를 프로그래머가 쉽게 사용할 수 있도록 **일관된 인터페이스**를 제공한다.

### 추상화의 장점

- **하드웨어 독립성**: 다양한 하드웨어에서 동일한 프로그램 실행 가능
- **개발 편의성**: 복잡한 하드웨어 제어를 간단한 함수 호출로 대체
- **호환성**: 하드웨어 변경 시에도 응용 프로그램 수정 불필요

## 2.3 보안과 접근 제어

### 시스템 보호

- **사용자 인증** : 로그인을 통한 사용자 신원 확인
- **접근 권한** : 파일, 프로세스, 시스템 자원에 대한 접근 제어
- **프로세스 격리** : 프로세스 간 무단 접근 방지

# 3. 커널 (Kernel) - 운영체제의 핵심

## 3.1 커널의 정의와 역할

<img src="images\리눅스 커널 구조.png" width="600" height="400"/>

**커널**은 운영체제의 핵심 부분으로, 하드웨어와 가장 가까운 곳에서 시스템의 모든 것을 제어한다.

### 커널의 주요 기능

1. **하드웨어 직접 제어** : CPU, 메모리, 디스크 등 물리적 자원 관리
2. **시스템 호출 처리** : 응용 프로그램의 요청을 하드웨어 동작으로 변환
3. **프로세스 관리** : 프로세스 생성, 스케줄링, 종료 관리
4. **인터럽트 처리** : 하드웨어나 소프트웨어 인터럽트 처리

## 3.2 이중 모드 (Dual Mode)

<img src="images\운영체제 이중모드.png" width="550" height="300"/>

운영체제는 **이중 모드**를 통해서 시스템을 보호한다.

### 사용자 모드 (User Mode)

- 제한된 권한: 일반적인 연산만 수행 가능
- 보호된 실행: 하드웨어에 직접 접근 불가
- 응용 프로그램: 대부분의 응용 프로그램이 이 모드에서 실행

### 커널 모드 (Kernel Mode)

- 특권 모드: 모든 하드웨어와 메모리에 접근 가능
- 시스템 제어: 시스템의 모든 자원을 제어할 수 있는 권한
- 운영체제 코드: 커널과 디바이스 드라이버가 이 모드에서 실행

## 3.3 시스템 콜 (System call)

<img src="images\시스템 콜 동작과정.png" width="550" height="300"/>

**시스템 콜**은 응용 프로그램이 운영체제의 서비스를 요청하는 방법이다.

### 시스템 콜 동작 과정

1. 응용 프로그램이 API 함수 호출
2. 라이브러리가 시스템 콜 번호와 함께 커널에 요청
3. 모드 전환: 사용자 모드 → 커널 모드
4. 커널이 해당 서비스 실행
5. 결과 반환 후 사용자 모드로 복귀

### 주요 시스템 콜 유형

- 파일 관리: open(), read(), write(), close()
- 프로세스 제어: fork(), exec(), wait(), exit()
- 메모리 관리: malloc(), free(), mmap()
- 통신: socket(), send(), recv()

# 4. 운영체제의 구조

<img src="images\단일형 vs 마이크로커널.png" width="550" height="300"/>

## 4.1 단일형 커널 (Monolithic Kernel)

### 특징

- 통합 구조: 모든 운영체제 기능을 하나의 큰 커널에 통합
- 빠른 성능: 내부 함수 호출로 빠른 통신
- 복잡성: 크고 복잡한 구조로 유지보수가 어려움

### 대표 운영체제

- **Linux**: 모듈 시스템으로 유연성 향상
- **Windows**: NT 커널 기반
- **UNIX**: 전통적인 단일형 구조

## 4.2 마이크로커널 (Microkernel)

### 특징

- **최소 기능**: 커널에는 메모리 관리, CPU 스케줄링, IPC만 포함
- **사용자 공간 서비스**: 파일 시스템, 네트워크 등은 별도 프로세스
- **안정성**: 한 서비스 오류가 전체 시스템에 영향 주지 않음
- **성능 오버헤드**: 서비스 간 통신으로 인한 성능 저하

### 대표 운영체제

- **Mach**: macOS의 기반
- **QNX**: 실시간 운영체제
- **Minix**: 교육용 운영체제

## 4.4 하이브리드 구조

<img src="images\darwin 커널구조.png" width="550" height="330"/>

현대 운영체제는 여러 구조의 장점을 결합한 하이브리드 구조를 사용한다.

### 대표 사례

- **Windows NT**: 마이크로커널 기반에 성능상 일부 기능을 커널에 통합
- **macOS (Darwin)**: Mach 마이크로커널 + BSD 단일형 커널
- **Linux**: 단일형 기반에 모듈 시스템 추가

# 핵심 요약

## 운영 체제의 핵심 역할

- **자원 관리**: CPU, 메모리, 파일, 입출력 장치의 효율적 관리
- **하드웨어 추상화**: 복잡한 하드웨어를 간단한 인터페이스로 제공
- **보안과 보호**: 시스템과 사용자 데이터의 안전성 보장
- **서비스 제공**: 응용 프로그램이 필요로 하는 다양한 서비스 지원

## 커널의 중요성

- **시스템의 핵심**: 모든 하드웨어와 소프트웨어를 제어하는 중심부
- **이중 모드**: 사용자 모드와 커널 모드로 시스템 보호
- **시스템 콜**: 응용 프로그램과 운영체제 간의 안전한 통신 방법

## 구조적 발전

- **단일형**: 성능 우선, 복잡성 높음 (Linux, Windows)
- **마이크로커널**: 안정성 우선, 성능 오버헤드 (Mach, QNX)
- **하이브리드**: 두 방식의 장점 결합 (macOS, Windows NT)
