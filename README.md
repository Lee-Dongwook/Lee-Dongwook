## 안녕하세요, 이동욱 (Lee Dongwook) 입니다.

> **AI 에이전트의 비확정적 실행 흐름을 검증 가능한 구조와 인터페이스로 구현하는 2년차 프론트엔드 엔지니어입니다.**

[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![PyPI](https://img.shields.io/badge/PyPI-ai--driven--e2e-3776AB?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/project/ai-driven-e2e/)

---

## Key Metrics & Highlights

| 영역 | 성과 및 지표 | 기술적 내용 |
| :--- | :--- | :--- |
| **Performance** | Critical Path 지연 시간 **52% 단축** | Chrome DevTools 프로파일링 기반 코드 스플리팅 및 프리캐시 재정의 |
| **UI Architecture** | Google A2UI 기반 선언적 동적 렌더러 구축 | `fieldType` 제네릭 연동 및 프론트엔드 배포 Zero화 스키마 파이프라인 |
| **Streaming** | fetch + ReadableStream 기반 SSE 구축 | 타임아웃 및 무응답 대기 해소, 청크 단위 점진적 렌더링 |
| **Testability** | Playwright · Storybook · Vitest 인프라 | 비확정적 AI 실행 경로의 결정론적 모킹 및 회귀 검증 체계 |

## Tech Stack

- **Frontend:** TypeScript, React, Next.js, Tailwind CSS, TanStack Query, Zustand, Feature-Sliced Design (FSD)
- **AI & Workflow:** LangGraph, Multi-Agent Architecture, Supervisor Agent, SSE Streaming, Google A2UI Protocol
- **Data & Infra:** Python, FastAPI, Kafka, PyFlink, Apache Superset, ClickHouse, Neo4j, Docker

## Work Experience

### (주) FutureWorkLab — Frontend Developer
`2024.10 - Present` | **제조 AI 플랫폼 AxFlow의 Agent + Workflow 확장 개편**
- **Google A2UI 기반 동적 UI 렌더러:** `fieldType` 기반 재귀 렌더 트리 및 `react-hook-form` 연동으로 20여 종의 문서 양식 수용
- **SSE 스트리밍 파이프라인:** `fetch` + `ReadableStream` 기반 `AsyncGenerator` 유틸 구축
- **성능 최적화:** 코드 스플리팅 및 프리캐시 재정의로 Critical Path 지연 시간 **52% 단축**

<details>
<summary><b>상세 업무 성과 보기</b></summary>

- **워크플로우 FE 아키텍처 총괄:** 단일 에이전트 구조에서 Agent + Workflow 확장 구조로 FE 아키텍처 전면 개편 및 공통 스키마 설계
- **테스트 인프라 구축:** Playwright, Storybook, Vitest 기반 통합 테스트 인프라 구축 및 에이전트 판단 재현 설계
</details>

## Featured Projects (Pinned Repositories)

### 1. [E2E-Self-Heal](https://github.com/Lee-Dongwook/E2E-Self-Heal) `Python` `PyPI` `GitHub Action`
> **LangGraph 기반 Playwright E2E 테스트 자율 복구 엔진**
- **아키텍처:** Diagnoser ➔ Patch Generator ➔ Selector Verifier ➔ Test Runner 4레이어 자율 피드백 루프
- **핵심 기능:** UI 변경으로 파손된 셀렉터를 Live DOM과 대조 검증(1:1 매칭)하여 자동 복구 및 CI/CD Patch PR 자동 생성

### 2. [Conflow](https://github.com/Lee-Dongwook/Conflow) `Python`
> **Supervisor Agent 기반 엔터프라이즈 협업 OS**
- **기능 개요:** PM, Comms, HR, 문서발급 기능을 하나로 통합한 엔터프라이즈 멀티 에이전트 협업 플랫폼
- **구조:** Supervisor Agent 모델을 통한 에이전트 간 연쇄 작업 제어 및 워크플로우 검증

### 3. [superset-bi-metrics](https://github.com/Lee-Dongwook/superset-bi-metrics) `Python`
> **Apache Superset 기반 BI Metrics 아키텍처 및 대시보드**
- **구조:** 커스텀 비즈니스 지표 정의, 데이터 시각화 파이프라인 및 엔터프라이즈 BI 대시보드 연동 구성

### 4. [kafka-principle](https://github.com/Lee-Dongwook/kafka-principle) `Java`
> **Apache Kafka 아키텍처 및 동작 원리 학습 리포지토리**
- **내용:** 분산 메시징 시스템의 핵심 원리(메시지 브로커, 토픽, 파티션, 오프셋 관리 및 컨슈머 그룹 동작 메커니즘) 분석 및 구현

### 5. [Renewal_TripPlannerZ](https://github.com/Lee-Dongwook/Renewal_TripPlannerZ) `TypeScript`
> **여행 일정 관리 · 예산 설계 · 동행자 매칭 플랫폼 (SaaS 리뉴얼)**
- **기능:** 여행 일정 수립, 실시간 예산 정산, 동행자 매칭 기능 및 단일 흐름 SaaS 아키텍처 구현

### 6. [PortFolio](https://github.com/Lee-Dongwook/PortFolio) `TypeScript`
> **개인 엔지니어링 포트폴리오 리포지토리**

## Open Source Contributions

- [`facebook/astryx`](https://github.com/facebook/astryx): UI 컴포넌트 개선 및 버그 수정 기여 (`#6389`, `#5964`, `#4292`, `#4284`)
- [`meursyphus/headless-chart`](https://github.com/meursyphus/headless-chart): 차트 라이브러리 기능 확장 기여
- [`jiunshinn/serve-emu`](https://github.com/jiunshinn/serve-emu): 에뮬레이터 제어 및 스트리밍 기여

## Activities

| 활동                                      | 기간                    |
|-------------------------------------------|-------------------------|
| **홍익대학교 컴퓨터공학전공 학술동아리 _P.C.R.C_ 32기** | 2018.03 - 2019.12   |
| **고려대학교 창업 준비 동아리 _Novelia_ FE 개발** | 2023.01 - 2023.05        |
| **홍익대학교 학습튜터링2 (홍익투게더) 멘토 _이끄미_ 활동** | 2023.03 - 2023.07   |

## Education 

|                                      | 기간                    |
|-------------------------------------------|-------------------------|
| **홍익대학교 정보컴퓨터공학부 컴퓨터공학전공**    | 2018.03 - 2024.08 |
| **인프런 X 코드캠프 고농축 프론트엔드 온라인 코스** |  2023.07 - 2024.01 |
| **코드랩 AI Multi-Agent 서비스 실전 프로젝트 - 최우수 수료**     | 2026.06 - 2026.09   |
