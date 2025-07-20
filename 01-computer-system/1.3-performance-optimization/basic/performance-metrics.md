# 1. 성능 측정 지표 (Latency, Throughput, QPS)

## 1.1 핵심 성능 지표

<img src="images\throughput_latency.jpg" width="500" height="250"/>

### Latency (지연 시간)

- 정의: 어떤 작업을 처리하는 데 걸리는 시간
- 단위: 밀리초(ms), 마이크로초(μs)
- 측정 방법: 요청 전송부터 응답 도착까지의 경과 시간
- 목표: 값이 작을수록 좋음

#### 예시

- 웹 애플리케이션: 사용자 요청부터 응답까지의 시간
- 데이터베이스: 쿼리 실행 시간
- 네트워크: 핑(Ping) 시간

### Throughput (처리량)

- 정의: 초당 처리하는 작업의 갯수
- 단위: 개수/시간 (request/sec, transactions/sec)
- 측정 방법: 일정 시간 동안 성공적으로 처리된 작업 수
- 목표: 값이 클수록 좋음

#### 처리량 지표의 종류

- **RPS (Request Per Second)**: 초당 요청 처리 수
- **TPS (Transaction Per Second)**: 초당 트랜재션 처리 수
- **QPS (Query Per Second)**: 초당 쿼리 처리 수
- **PPS (Page Per Second)**: 초당 페이지 처리 수

### QPS (Query Per Second)

- 정의: 데이터베이스나 웹 서버 API 등에서 특정 작업이나 요청이 초당으로 얼마나 처리되는지를 나타내는 지표
- 용도: 시스템의 성능과 처리 능력을 평가하는 중요한 측정 지표

## 1.2 성능 지표 간의 관계

### Latency vs Throughput

```
고속도로 예시
- Latency: 서울→부산 이동 시간 (4시간)
- Throughput: 시간당 통과 차량 수 (200대/시간)
```

### 트레이드오프 관계

- 처리하는 프로세서의 자원은 한정되어 있기 때문에 latency 낮추려면 즉, 어떤 작업을 최대한 빨리 끝내려고 한다면 자원을 그 작업에 최대한 많이 할당해야 한다.
- 반대로 Throughput을 높이려면 여러 작업을 동시에 처리해야 하므로 개별 작업의 Latency가 증가할 수 있음

#### 최적화 전략

1. **Latency 개선:** 개발된 애플리케이션을 개선하는 것으로 시작 (알고리즘 개선, I/O 최소화)
2. **Throughput 개선**: 병목 지점 해결, 하드웨어 확장
3. **균형점 찾기**: Latency와 Throughput의 가장 효율적인 최적점을 찾는 것이 핵심

## 핵심 요약

### 성능 측정의 핵심

- Latency: 작업 처리 시간 (작을수록 좋음)
- Throughput: 단위 시간당 처리량 (클수록 좋음)
- QPS: 초당 쿼리 처리 수 (시스템 처리 능력 지표)
- 균형점: Latency와 Throughput의 최적 균형 찾기
