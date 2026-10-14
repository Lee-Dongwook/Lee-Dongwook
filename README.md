# Lee Dongwook | Product Engineer

**제품의 요구사항을 이해하고, 기술적 제약 안에서 유지보수 가능한 구현으로 연결하는 Product Engineer를 지향합니다.**

기능을 구현하는 것에서 그치지 않고, 복잡한 데이터 흐름과 상태 전이에서 발생하는 문제를 추적하고, 예외 상황에서도 일관되게 동작하는 구조를 만드는 데 관심이 있습니다. 문서·AI 워크플로, 온프레미스 계정 관리, 데이터 시각화 영역을 경험하며 제품의 기능 구현부터 공통 컴포넌트, 테스트 및 CI 환경까지 개발 범위를 넓혀 가고 있습니다.

[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![PyPI](https://img.shields.io/badge/PyPI-ai--driven--e2e-3776AB?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/project/ai-driven-e2e/)

## Work Experience

### FutureWorkLab — Product Engineer · Oct 2024 – Present

제조 AI 에이전트 플랫폼과 업무 자동화 서비스를 개발하며, 프론트엔드를 중심으로 API 및 데이터 모델과 연결되는 기능을 구현하고 있습니다.

#### Agent Workflow & Domain Architecture
기존 Document Agent 중심의 구조를 Agent와 Workflow를 함께 다룰 수 있는 형태로 확장하면서, 독립적인 앱 구조와 공통 도메인 모델을 정비했습니다.

- Workflow 설정 및 실행 화면과 관련 API 연동

- 문서 템플릿의 모델, 스키마, 생성·조회 API 및 사용자 화면 구현

- 공통 모델과 패키지를 활용한 도메인 구조 정리 및 기존 기능 이관

- 기능 간 의존성을 분리하고 앱별 책임을 명확히 하는 방향으로 구조 개선

- 문서 생성부터 Workflow 실행까지 이어지는 사용자 흐름 구현

#### On-premise Authentication & Account Management

온프레미스 환경의 계정 관리 기능을 개발하며 인증 정책과 사용자 상태가 서버와 클라이언트에서 일관되게 처리되도록 구현했습니다.

- 계정 생성·조회·수정, 관리자 및 일반 사용자 화면 구현

- Excel 기반 일괄 등록, 행별 검증, 오류 및 처리 결과 표시

- 비밀번호 변경, 세션 갱신, 계정 잠금 및 비활성화에 따른 상태 처리

- 로그인 실패, 토큰 만료, 비밀번호 변경 필요 등 인증 상태별 예외 흐름 분리

- 계정 탈퇴 요청·철회·승인 과정의 상태 정합성과 동시 요청 처리 고려

- 서버 오류 코드와 클라이언트 동작을 연결해 실패 상황별 안내 및 후속 처리 구현

#### Document Processing & PDF Rendering

다양한 문서 형식과 OCR 데이터를 다루는 기능을 개발하고, PDF 열람 과정에서 발생하는 렌더링 및 자원 관리 문제를 개선했습니다.

- DOCX, TXT, HWP, CSV 등 문서 형식별 뷰어 및 데이터 처리 흐름 구현

- OCR 결과의 메타데이터와 텍스트 유무를 검증해 데이터 유실 경로 보완

- 비동기 처리 상태와 polling 흐름을 분리하고 갱신 시점 관리

- 화면 위치를 기준으로 PDF 페이지를 지연 렌더링하도록 구현

- 화면에서 멀어진 페이지의 렌더링 자원 정리 및 요청 취소 처리

- 문서 교체 시 캐시 무효화와 페이지 렌더링 상태 관리

#### Monitoring, KPI & Real-time Data

운영 데이터를 화면에서 탐색하고 해석할 수 있도록 실시간 이벤트, 기간 필터, 집계 결과를 연결했습니다.

- SSE 기반 작업 상태 수신 및 UI 상태 동기화

- 기간 필터와 KPI 집계 기준을 연결하고 조회 범위에 따른 계산 로직 보완

- 이전 기간 비교, 평균 계산, 집계 시점 등 지표 표시의 일관성 개선

- 기간 변경에 따른 상태 동기화 및 반복 갱신 문제 수정

#### Shared UI & Development Infrastructure

기능 개발뿐 아니라 공통 UI를 검증하고 변경 사항을 지속적으로 확인할 수 있는 개발 환경을 정비했습니다.

- Storybook 기반 공통 UI 컴포넌트 문서화 및 사용 예시 구성

- 컴포넌트 상태와 상호작용을 확인할 수 있는 스토리 및 테스트 구성

- 변경된 워크스페이스를 기준으로 테스트 대상을 결정하는 CI 흐름 개선

- 테스트 샤딩, 결과 집계 및 머지 게이트 구성

- 공통 모듈과 테스트 환경의 의존성 및 실행 설정 정리

#### Current Focus: BI & Data Visualization

온프레미스 BI 제품의 프론트엔드 시각화 계층을 개발하고 있습니다.

- 사용자 시각화 설정과 차트 렌더링을 연결하는 컴포넌트 구조 설계

- 시각화 설정의 검증과 호스트 애플리케이션 간 인터페이스 설계

- 차트 라이브러리와 BI 도메인 모델 사이의 추상화 경계 검토

## Projects 

### 1. [E2E-Self-Heal](https://github.com/Lee-Dongwook/E2E-Self-Heal)
#### AI 기반 Playwright E2E 테스트 자동 복구 도구

Playwright E2E 테스트가 UI 변경으로 인해 실패했을 때, 실패 원인을 분석하고 수정안을 생성한 뒤 실행 결과로 검증하는 오픈소스 프로젝트입니다.

**Technical Highlights**

- **Repair Workflow**: 실패 진단, 수정안 생성, selector 검증, 테스트 재실행으로 이어지는 복구 흐름 구성

- **Constrained Patching**: locator와 wait condition을 중심으로 수정 범위를 제한하고 assertion 및 테스트 검증 로직은 보호

- **Live DOM Verification**: 수정된 selector를 실제 DOM에서 확인한 뒤 테스트 실행으로 유효성 검증

- **Shadow Testing**: 기록된 네트워크 데이터를 활용해 실제 백엔드 요청에 대한 의존성을 줄인 검증 경로 구현

- **CLI & CI Integration**: 로컬 CLI와 GitHub Actions를 통한 실행 및 검토 가능한 수정 결과 전달

- **Review Mode**: 테스트 파일을 직접 수정하는 방식 외에도 실패 원인과 수정 제안을 리뷰 형태로 제공

단순히 LLM으로 테스트 코드를 수정하는 것이 아니라, 수정 가능한 범위를 제한하고 실행 결과를 검증하는 폐쇄 루프를 구성하는 것을 핵심 설계 방향으로 삼고 있습니다.


### 2. [superset-bi-metrics](https://github.com/Lee-Dongwook/superset-bi-metrics) 
BI 제품에서 시각화와 지표 정의, 비동기 쿼리 처리 상태를 어떻게 연결할 수 있는지 탐색하는 프로젝트입니다.

- **Apache Superset**과 **Cube.js**를 연결하는 구조를 설계

- 쿼리 실행 및 사전 집계 진행 상태를 전달하기 위한 이벤트 흐름을 구성

- 프론트엔드 클라이언트, API 계층, 실시간 이벤트 전달 계층의 역할을 구분

이 프로젝트는 BI 시스템의 여러 구성 요소를 연결하는 아키텍처를 탐색하는 데 초점을 둡니다. 저장소에 정의된 구조와 실제로 구현·검증된 기능은 구분해서 살펴볼 수 있습니다.

### 3. [Conflow](https://github.com/Lee-Dongwook/Conflow) 
#### AI 기반 협업 워크플로 프로젝트

- 여러 업무 영역을 하나의 데이터 모델과 워크플로로 연결하는 방향을 탐색하는 개인 프로젝트입니다.

- 여러 업무 기능을 연결하기 위한 도메인 및 애플리케이션 구조를 설계했습니다.

- UI와 비즈니스 로직, 외부 시스템 연동을 분리하는 구조를 적용하고자 했습니다.

AI 에이전트가 업무 흐름에 참여할 수 있도록 관련 기능과 확장 방향을 탐색하고 있습니다.

기술: Python, TypeScript, React, AI Agent


## Open Source Contributions

- [`facebook/astryx`](https://github.com/facebook/astryx): UI 컴포넌트 개선 및 버그 수정 기여 (`#6389`, `#5964`, `#4292`, `#4284`)
- [`meursyphus/headless-chart`](https://github.com/meursyphus/headless-chart): 차트 라이브러리 기능 확장 기여
- [`jiunshinn/serve-emu`](https://github.com/jiunshinn/serve-emu): 에뮬레이터 제어 및 스트리밍 기여

## Tech Stack

### Frontend
TypeScript · JavaScript · React · Next.js · Tailwind CSS · TanStack Query · Zustand

### Backend & Data
Python · FastAPI · PostgreSQL · Redis · REST API · SSE

### Testing & Developer Tools
Playwright · Vitest · Storybook · GitHub Actions · Docker

### AI & Workflow
LLM · LangGraph · Multi-Agent Systems · Workflow Automation

## Education

홍익대학교 — 정보컴퓨터공학부 컴퓨터공학전공 (2018.03 – 2024.08)
코드랩 — AI Multi-Agent 서비스 실전 프로젝트 - 최우수 수료 (2026.06 – 2026.09)
