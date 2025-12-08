# <img width="50" height="50" alt="image" src="https://github.com/user-attachments/assets/dd2d9522-3591-454c-9cd2-0b534b75b8b9" /> CouponPop

![Thumbnail (7)](https://github.com/user-attachments/assets/c86b02a6-185b-4ee6-ba1a-c7599983aa3d)
<img width="4000" height="2828" alt="팀프로젝트_상장_대상(CouponPop)" src="https://github.com/user-attachments/assets/180a69e7-eb48-444c-a4cb-abfce1197b47" />
[![GitHub Stars](https://img.shields.io/github/stars/CouponPop?style=social)](https://github.com/CouponPop)
[![Tech Stack](https://img.shields.io/badge/Tech-Java%20%7C%20Spring%20Boot%20%7C%20MSA-blue)]()
[![AWS](https://img.shields.io/badge/Cloud-AWS%20ECS%20Fargate-orange)]()

> **위치 기반 실시간 쿠폰 발급 플랫폼**  
> 지금 이 순간, 이 장소에서만 받을 수 있는 특별한 혜택을 경험하세요!

---

## 📚 목차

- [✨ Overview](#-overview)
- [🕹️ 핵심 기능](#️-핵심-기능)
- [🫂 개발 문화](#-개발-문화)
- [🏗️ 아키텍처](#️-아키텍처)
- [💡 기술적 의사결정](#-기술적-의사결정)
- [⚡ 트러블 슈팅](#-트러블-슈팅)
- [🎯 성능 개선](#-성능-개선)
- [📁 설계 문서](#-설계-문서)
- [🥇 팀원 소개](#-팀원-소개)

---

## ✨ Overview

### 서비스 소개

**CouponPop**은 사용자의 **현재 위치 기반**으로 주변 매장에서 제공하는 **한정 수량 쿠폰을 실시간 발급**해주는 지역 특화 프로모션 플랫폼입니다.

소상공인 및 프랜차이즈의 **효율적인 지역 마케팅**을 돕고, 사용자는 "지금 이 순간, 이 장소에서만 받을 수 있는" 새로운 혜택 경험을 제공합니다.

### 기획 배경

**소상공인의 문제**
- 높은 광고비 대비 낮은 고객 유입 효과
- 지역 기반 실시간 마케팅 시스템의 부재
- 프로모션·쿠폰 관리의 한계

**사용자의 문제**
- 넘쳐나는 광고 속에서 **지금 내 상황과 위치에 맞는 혜택** 찾기 어려움
- 오프라인 매장에서 즉각적인 보상을 주는 경험 부족

> CouponPop은 `실시간성 + 희소성 + 경쟁 요소`를 결합해 `오프라인 소비 경험을 혁신`합니다.

### 기대 효과

**✔ 소상공인·프랜차이즈**
- 광고비 대비 높은 방문 유도 효과
- 실시간 쿠폰 발행으로 유동 인구의 즉각적 전환
- 지역 단위 타깃 마케팅 가능

**✔ 사용자**
- "지금 여기서만 받을 수 있는" 즉시성 + 재미 요소
- 게임화된 쿠폰 획득 경험
- 가까운 매장의 혜택을 쉽게 확인

---

## 🕹️ 핵심 기능

### 🔎 위치 기반 쿠폰 노출
- 사용자의 GPS 좌표 기반
- 특정 지역(홍대, 강남역 등) 진입 시 주변 매장 쿠폰이 자동 노출
- 매장 반경 내 거리 기반 필터링(예: 300m)

### 🎟 한정 수량 선착순 쿠폰 발급
- 매장별 쿠폰 수량 제한
- 실시간 선착순 경쟁 처리
- **Redis Redisson 기반 분산 락**으로 동시성 제어

### 🗺 지도 기반 UI에 적합한 API 제공
- 지도 상에서 매장 위치 + 쿠폰 정보 표시
- 한눈에 가까운 매장의 혜택 파악 가능

### 🧾 사용 이력 관리
- 발급 이력, 사용 내역 저장
- 매장별 성과 분석 가능

### 📊 사업자용 대시보드
- 특정 시간대 발급량, 사용량
- 방문 유저 패턴
- 지역/시간별 최적 쿠폰 전략 추천

---

## 🫂 개발 문화

### Core Principles

짧은 기간 안에 완성도 높은 결과물을 만들기 위해 우리 팀은 '**코드만 잘 짜는 팀**'이 아니라 '**같은 방향으로 일하는 팀**'을 목표로 했습니다.

| 원칙 | 설명 |
|------|------|
| **공유(Sharing)** | 기술 지식과 설정을 팀 전체가 공유할 수 있도록 문서화 |
| **일관성(Consistency)** | 환경과 구조가 통일되도록 공통 템플릿과 규칙 정의 |
| **투명성(Transparency)** | 코드와 설정, 테스트 결과를 모두 문서화해 누구나 검증 가능하게 구성 |
| **재사용성(Reusability)** | 반복되는 작업을 최소화하고, 공통 모듈과 가이드를 통해 효율 향상 |

### 공통 기술 가이드 문서

#### 🧩 Infrastructure & Deployment
- [MySQL Master–Slave 복제 구성 가이드](https://www.notion.so/MySQL-Master-Slave-2a62dc3ef5148060832ee1e7e2649248?source=copy_link)
- [웹 페이지 / Data Resource / ECS·EC2 접속 가이드](https://www.notion.so/Data-Resource-ECS-EC2-2a42dc3ef5148076a147fc2d6b46445d?source=copy_link)

#### ⚙️ Development & Architecture
- [MSA 전환 및 공통 모듈 적용 가이드](https://www.notion.so/MSA-29e2dc3ef514801b8173d61759598eb6?source=copy_link)
- [MSA 신규 서비스 생성 가이드](https://www.notion.so/MSA-2a02dc3ef5148048b747fbb3925af0f1?source=copy_link)

#### 🧾 API & Testing
- [Spring RestDocs 가이드](https://www.notion.so/REST-Docs-Swagger-ui-29a2dc3ef514809f8c6ee00db62f4a6c?source=copy_link)
- [JMeter 부하 테스트 가이드](https://www.notion.so/JMeter-Apache-JMeter-297cdb8ae85b8075aa81eceb921641ff?source=copy_link)

#### 📈 Monitoring & Operation
- [APM 모니터링 설정 가이드 (로컬용)](https://www.notion.so/APM-2a32dc3ef5148080ac11eff9aa3dc170?source=copy_link)

---

## 🏗️ 아키텍처

### System Architecture

- [Architecture Diagram](https://github.com/CouponPop/.github/issues/1#issue-3636723446)

### Microservices

| Service | 설명 | 기술 스택 |
|---------|------|-----------|
| [api-gateway](https://github.com/CouponPop/couponpop-api-gateway) | API Gateway 및 라우팅 | Spring Cloud Gateway |
| [member-service](https://github.com/CouponPop/couponpop-member-service) | 회원 관리 | Java, Spring Boot |
| [store-service](https://github.com/CouponPop/couponpop-store-service) | 상점 관리 | Java, Spring Boot, Elasticsearch |
| [coupon-service](https://github.com/CouponPop/couponpop-coupon-service) | 쿠폰 발급 및 관리 | Java, Spring Boot, Redis |
| [notification-service](https://github.com/CouponPop/couponpop-notification-service) | 알림 전송 | Java, Spring Boot, FCM |
| [batch-service](https://github.com/CouponPop/couponpop-batch-service) | 배치 작업 | Java, Spring Boot, Spring Batch |

### Common Modules

| Module | 설명 | Repository |
|--------|------|------------|
| [security-module](https://github.com/CouponPop/couponpop-security-module) | JWT 인증/인가 공통 모듈 | GitHub Packages |
| [core-module](https://github.com/CouponPop/couponpop-core-module) | 공통 DTO 및 유틸리티 | GitHub Packages |

### Infrastructure

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Cloud Platform** | AWS | 전체 인프라 호스팅 |
| **Container Runtime** | ECS Fargate | 서버리스 컨테이너 실행 |
| **Service Discovery** | AWS Service Connect | 마이크로서비스 간 통신 |
| **Database** | MySQL (Master-Slave) | 트랜잭션 데이터 저장 |
| **Cache & Lock** | Redis | 캐싱 및 분산 락 |
| **Search Engine** | Elasticsearch | 전문 검색 및 하이브리드 검색 |
| **Message Queue** | RabbitMQ | 비동기 메시징 |
| **Monitoring** | Prometheus + Grafana | 애플리케이션 모니터링 |
| **Logging** | ELK Stack (Filebeat, Logstash, Elasticsearch, Kibana) | 로그 수집 및 분석 |
| **CI/CD** | Jenkins + SonarQube | 빌드, 테스트, 배포 자동화 |

---

## 💡 기술적 의사결정

<details>
<summary><strong>MySQL 선택 이유</strong></summary>

MySQL은 우리 시스템의 핵심 트랜잭션 데이터베이스 역할을 합니다.

**주요 장점:**
- **신뢰성**: 높은 부하 상황에서도 데이터가 올바르게 저장됨
- **일관성**: 동시에 발생하는 작업이 충돌 없이 처리됨
- **지속성**: 관리 및 분석을 위해 장기간 안전하게 데이터가 보존됨

</details>

<details>
<summary><strong>Elasticsearch + 하이브리드 검색 도입</strong></summary>

### 배경
기존 RDB(MySQL)는 복잡한 한글 전문 검색과 고속 검색 요구사항을 충족시키기 어려웠습니다.

### 요구사항
- 고속 검색 (밀리초 단위 응답)
- 한글 형태소 분석 기반 정확한 검색
- AI 검색 지원 (벡터 저장 및 하이브리드 검색)

### 하이브리드 검색 구조
1. **Embedding 생성** (OpenAI API)
2. **의미 검색** (KNN in Elasticsearch)
3. **키워드 검색** (BM25)
4. **결과 융합** 및 점수 합산

**효과:**
- 의도형 검색어("조용한 카페")에 강점
- 정확 키워드형 검색어("스타벅스")에 강점
- 혼합형 검색어에서 최적의 결과 제공

</details>

<details>
<summary><strong>Redis Redisson 분산 락 선택</strong></summary>

### 쿠폰 발급 동시성 제어 실험

| Lock 방식 | 처리시간 (1000명) | Throughput | CPU 사용률 |
|-----------|-------------------|------------|-----------|
| Synchronized | 11.6s | 3.0 건/s | 16.4% |
| Pessimistic Lock | 23.4s | 11.4 건/s | 21.1% |
| Optimistic Lock | 2m 37s | 9.7 건/s | **81.1%** |
| Named Lock | 19.1s | 48.6 건/s | 19.9% |
| Redis Lettuce | 33.3s | 35.9 건/s | 11.2% (Redis) |
| **Redis Redisson** | **31.3s** | **44.5 건/s** | **3.2%** (Redis) |

**선택 이유:**
- pub/sub 기반 락 해제 알림으로 스핀락 제거
- 낮은 Redis 부하 (3.2%)
- 분산 환경 지원
- 균형 잡힌 성능과 안정성

</details>

<details>
<summary><strong>MSA 환경 구성</strong></summary>

### 컨테이너 런타임: ECS Fargate
- EC2 인스턴스 관리 불필요
- 자동 스케일링
- 운영 부담 최소화

### Service Discovery: AWS Service Connect
- ECS/Fargate와 완벽한 통합
- 논리적 DNS 이름만으로 서비스 간 통신
- Blue/Green 배포 기본 제공

### API Gateway: Spring Cloud Gateway
- 프로필 기반 라우팅 (로컬/운영 환경 분리)
- Spring Boot 생태계와 일관성
- 빠른 개발 및 배포

### 인증/인가: 분산 인증 + Security 모듈
- 각 서비스가 독립적으로 JWT 검증
- 공통 security-module 라이브러리 사용
- 내부 서비스 간 통신도 보호

</details>

<details>
<summary><strong>CI/CD: Jenkins + SonarQube (Self-hosted)</strong></summary>

**선택 이유:**
- AWS VPC 내부 구성으로 보안 강화
- 코드 품질 자동 검증 (SonarQube)
- 내부 전용 도메인 (jenkins.couponpop.net)
- 장기적 비용 효율성

</details>

---

## ⚡ 트러블 슈팅

<details>
<summary><strong>FCM 알림 중복 발송 방지 (Redis 멱등성 락)</strong></summary>

### 문제
FCM 알림이 재시도 로직 개입 시 중복 발송되는 문제 발생

### 해결
1. **traceId 생성**: 알림을 고유하게 식별
2. **Redis 멱등성 락**: `SET NX`로 처리 여부 판단
3. **정상 발송 시 TTL 연장**: 7일간 중복 차단
4. **실패 시 키 삭제**: 재시도 가능하도록 설정

</details>

<details>
<summary><strong>MSA 전환 후 JOIN 문제 해결</strong></summary>

### 문제
DB가 분리되면서 `Store DB`와 `Coupon DB`를 JOIN하는 쿼리 사용 불가

### 해결 방안 비교
- **API Composition** ✅ (채택)
  - Store 서비스 API 호출 후 애플리케이션에서 조합
  - 실시간 데이터 조회 가능
  - 구현 단순, 빠른 적용
  
- **CQRS + Snapshot**
  - 읽기 전용 테이블 유지
  - 이벤트 기반 동기화
  - 운영 복잡도 증가

### 최종 구현
- Chunk 처리 + Bulk API
- 필터링 로직 최적화
- MQ 비동기 처리

</details>

<details>
<summary><strong>시스템 간 Feign Client 인증 문제</strong></summary>

### 문제
배치 서버에서 내부 API 호출 시 `401 Unauthorized` 발생

### 해결
1. **SYSTEM 토큰 타입 도입**
   - `tokenType = SYSTEM` 클레임 추가
   - 시스템 전용 JWT 발급
   
2. **JwtAuthFilter 분기 처리**
   - USER / SYSTEM 타입 구분
   
3. **Feign RequestInterceptor**
   - SYSTEM 토큰 자동 주입
   - 배치 코드에서 토큰 관리 불필요

</details>

<details>
<summary><strong>Prometheus ECS Fargate 연동</strong></summary>

### 문제
Prometheus가 ECS Fargate Task의 동적 IP를 자동 탐색할 방법 필요

### 해결
1. **오픈소스 활용**: `prometheus-ecs-discovery`
2. **공유 볼륨**: EC2의 `./targets` 디렉터리를 통한 파일 교환
3. **중복 타겟 제거**: Service Connect 프록시 필터링

</details>

---

## 🎯 성능 개선

### 매장 검색 성능 (Elasticsearch 도입 효과)

| 지표 | DB 검색 | Elasticsearch | 개선율 |
|------|---------|---------------|--------|
| 평균 응답 시간 | 8,090 ms | **57.07 ms** | **99.29% ↓** |
| p95 | 15,400 ms | **255.82 ms** | **98.3% ↓** |
| 처리량 (RPS) | 11.79 /s | **1,490 /s** | **126.4배 ↑** |

**결과**: 약 **141.8배** 빠른 검색 속도 달성

### 쿠폰 발급 성능 테스트

| 시나리오 | VUs | 평균 응답 | p95 | 실패율 |
|----------|-----|-----------|-----|--------|
| Smoke Test | 5 | 14ms | 32ms | 91%* |
| Spike Test | 50 | 1.17s | 2.01s | 26% |
| Ramp-Up | 300 | 6.23s | 18.8s | 20% |

(*비즈니스 로직상 실패, 시스템 오류 아님)

### AOP vs 템플릿 메서드 패턴 (락 처리)

| 테스트 | AOP (기존) | 템플릿 패턴 | 개선율 |
|--------|-----------|------------|--------|
| Spike 실패율 | 26% | **0%** | **100% ↓** |
| Spike 평균 응답 | 1.17s | **0.94s** | **19.7% ↓** |
| Ramp-Up 실패율 | 20% | **1.33%** | **93.4% ↓** |
| Ramp-Up p95 | 18s | **9.25s** | **48.6% ↓** |

**결론**: 템플릿 메서드 패턴이 락 범위 제어와 성능 면에서 우수

---

## 📁 설계 문서

### 🧠 브레인스토밍
- [TLDraw 문서 보기](https://www.tldraw.com/f/e5Roz5BijagLg-W4-2Amk?d=v-4514.2606.11803.6302.page)

### 🌐 API 명세서
- [CouponPop API](https://teamsparta.notion.site/S-A-2872dc3ef5148113aa66d8063e655851?pvs=143)

### 📎 ERD

#### v1 (모놀리식 설계)
<details>
  <summary>ERD v1</summary>

  - [ERD v1](https://github.com/CouponPop/.github/issues/2#issue-3636767097)

</details>


#### v2 (MSA 적용)

<details>
  <summary>MemberService</summary>

  - [Member ERD](https://github.com/CouponPop/.github/issues/3#issue-3636771904)

</details>

<details>
  <summary>StoreService</summary>

  - [Store ERD](https://github.com/CouponPop/.github/issues/4#issue-3636790940)

</details>

<details>
  <summary>CouponService</summary>

  - [Coupon ERD](https://github.com/CouponPop/.github/issues/5#issue-3636797497)

</details>

<details>
  <summary>NotificationService</summary>

  - [Notification ERD](https://github.com/CouponPop/.github/issues/6#issue-3636805098)

</details>

## 🥇 팀원 소개

</div>

<table>
<tr>
<td align="center" width="20%">
<a href="https://github.com/seyoung5744">
<img src="https://github.com/seyoung5744.png" width="120px" style="border-radius: 50%;" alt="원세영"/>
<br/><b>원세영</b><br/>
<sub>리더</sub>
</a>
</td>
<td align="center" width="20%">
<a href="https://github.com/seonrizee">
<img src="https://github.com/seonrizee.png" width="120px" style="border-radius: 50%;" alt="김필선"/>
<br/><b>김필선</b><br/>
<sub>부리더</sub>
</a>
</td>
<td align="center" width="20%">
<a href="https://github.com/younghunkimm">
<img src="https://github.com/younghunkimm.png" width="120px" style="border-radius: 50%;" alt="김영훈"/>
<br/><b>김영훈</b><br/>
<sub>팀원</sub>
</a>
</td>
<td align="center" width="20%">
<a href="https://github.com/4x2vk">
<img src="https://github.com/4x2vk.png" width="120px" style="border-radius: 50%;" alt="구안득"/>
<br/><b>구안득</b><br/>
<sub>팀원</sub>
</a>
</td>
</tr>
</table>

<br/>

---

## 🚀 Quick Start

### Prerequisites
```bash
- Java 17+
- Docker & Docker Compose
- AWS CLI (운영 환경 배포 시)
```

### Local Development

1. **Clone repositories**
```bash
git clone https://github.com/CouponPop/local-docker-infra.git
cd local-docker-infra
```

2. **Start infrastructure**
```bash
docker-compose up -d
```

3. **Run services**
각 서비스 디렉터리에서:
```bash
./gradlew bootRun --args='--spring.profiles.active=local'
```

### Environment Variables
```properties
# Common
SPRING_PROFILES_ACTIVE=local

# Database
DB_MASTER_URL=jdbc:mysql://localhost:3306/couponpop
DB_SLAVE_URL=jdbc:mysql://localhost:3307/couponpop
DB_USERNAME=root
DB_PASSWORD=password

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379

# Elasticsearch
ES_HOST=localhost
ES_PORT=9200
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
## 🔗 Links

- [자세한 내용은 팀 브로셔를 참고하시기 바랍니다](https://teamsparta.notion.site/9-CouponPop-2a32dc3ef514806d894bfe5ae653f0eb)
---
<div align="center">

**<img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/dd2d9522-3591-454c-9cd2-0b534b75b8b9" /> CouponPop Team 9**

</div>
