# Lee Dongwook | Product Engineer

**제품의 요구사항을 이해하고, 기술적 제약 안에서 유지보수 가능한 구현으로 연결하는 Product Engineer를 지향합니다.**

기능을 구현하는 것에서 그치지 않고, 복잡한 데이터 흐름과 상태 전이에서 발생하는 문제를 추적하고, 예외 상황에서도 일관되게 동작하는 구조를 만드는 데 관심이 있습니다. 문서·AI 워크플로, 온프레미스 계정 관리, 데이터 시각화 영역을 경험하며 제품의 기능 구현부터 공통 컴포넌트, 테스트 및 CI 환경까지 개발 범위를 넓혀 가고 있습니다.

[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![PyPI](https://img.shields.io/badge/PyPI-ai--driven--e2e-3776AB?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/project/ai-driven-e2e/)

## What I Do

### 제품의 전체 흐름을 연결합니다
사용자가 수행하는 업무를 화면, API, 데이터 구조로 연결합니다. 프론트엔드와 서버의 책임을 함께 살피며, 기능이 실제 업무 흐름 안에서 동작하도록 구현합니다.

### 예외 상황에서도 일관된 동작을 고민합니다
인증 상태에 따른 화면 전환, 문서 데이터의 정합성, 비동기 작업의 상태 변화처럼 정상적인 흐름만으로 설명하기 어려운 문제를 추적하고 해결합니다.

### 지속적으로 개선할 수 있는 개발 기반을 만듭니다
공통 도메인과 UI 문서화, 테스트 및 CI 실행 구조를 정비해 기능을 추가하고 변경할 때 검증할 수 있는 기반을 마련합니다.


## Work Experience

### FutureWorkLab — Frontend Developer / Product Engineer
2024.10 – Present

**제조 AI 플랫폼 Axflow의 Agent 및 Workflow 관련 기능**을 개발하고 있습니다.

- **Agent Workflow** 개편: 기존 기능을 확장할 수 있도록 프론트엔드 구조와 공통 모델을 정리하고, Workflow 설정 및 실행 화면을 구현했습니다.

- **문서 템플릿**: 템플릿의 생성·조회와 문서 생성 흐름을 연결하고, 관련 데이터 구조와 API 연동을 개발했습니다.

- **동적 UI**: 문서 유형에 따른 UI 렌더링과 폼 입력 구조를 구성해 여러 형태의 문서를 다룰 수 있도록 했습니다.

- **SSE 스트리밍**: fetch와 ReadableStream을 활용해 서버에서 전달되는 데이터를 점진적으로 처리하는 공통 유틸리티를 구현했습니다.

- **성능 및 개발 환경**: 코드 스플리팅과 프리캐시 구조를 개선하고, Storybook·테스트·CI를 통해 컴포넌트 개발과 검증 환경을 정비했습니다.

실무에서 기능을 구현할 때는 개별 화면의 완성도뿐 아니라 데이터가 전달되는 경로, 상태 변화에 따른 동작, 기존 기능과 새로운 구조의 연결을 함께 고려합니다.

## Featured Projects 

### 1. [E2E-Self-Heal](https://github.com/Lee-Dongwook/E2E-Self-Heal)
#### AI 기반 Playwright E2E 테스트 자동 복구 도구

UI 변경으로 테스트의 selector가 깨졌을 때 실패 원인을 분석하고, 수정 후보를 검증한 뒤 테스트를 다시 실행하는 오픈소스 프로젝트입니다.

- **실패 진단 및 복구**: Diagnoser → Patch Generator → Selector Verifier → Test Runner 흐름을 통해 selector 및 대기 조건의 수정과 검증을 수행합니다.

- **수정 범위 제한**: assertion과 테스트 로직을 변경하지 않도록 패치 범위를 제한하고, 수정 결과를 사람이 검토할 수 있도록 설계했습니다.

- **DOM 기반 검증**: 수정한 selector가 실제 DOM에서 유일한 요소를 가리키는지 확인합니다.

- **실행 방식**: 로컬 CLI와 GitHub Actions 기반 워크플로를 지원합니다.

- **리뷰 모드**: 테스트 코드를 자동 수정하는 대신, 원인이 된 소스 코드에 대한 개선 제안을 제공하는 흐름도 지원합니다.

이 프로젝트에서는 LLM의 판단을 그대로 적용하는 것보다, 수정 가능한 범위를 제한하고 실행 결과를 검증하는 구조에 집중하고 있습니다.

기술: Python, LangGraph, Playwright, GitHub Actions

### 2. [superset-bi-metrics](https://github.com/Lee-Dongwook/superset-bi-metrics) 
BI 제품에서 시각화와 지표 정의, 비동기 쿼리 처리 상태를 어떻게 연결할 수 있는지 탐색하는 프로젝트입니다.

- **Apache Superset**과 **Cube.js**를 연결하는 구조를 설계했습니다.

- 쿼리 실행 및 사전 집계 진행 상태를 전달하기 위한 이벤트 흐름을 구성했습니다.

- 프론트엔드 클라이언트, API 계층, 실시간 이벤트 전달 계층의 역할을 구분했습니다.

이 프로젝트는 BI 시스템의 여러 구성 요소를 연결하는 아키텍처를 탐색하는 데 초점을 둡니다. 저장소에 정의된 구조와 실제로 구현·검증된 기능은 구분해서 살펴볼 수 있습니다.

기술: Apache Superset, Cube.js, Python, Go, TypeScript, Rust, Redis

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

Frontend
TypeScript · JavaScript · React · Next.js · Tailwind CSS · TanStack Query · Zustand

Backend & Data
Python · FastAPI · SQL · Redis

AI & Workflow
LangGraph · Multi-Agent Architecture · SSE Streaming

Testing & Developer Tools
Playwright · Vitest · Storybook · GitHub Actions · Docker

기술 스택은 실무와 개인 프로젝트에서 사용한 기술을 중심으로 정리했습니다. 프로젝트별 구체적인 사용 범위는 각 저장소에서 확인할 수 있습니다.

## Education

홍익대학교 — 정보컴퓨터공학부 컴퓨터공학전공 (2018.03 – 2024.08)
코드랩 — AI Multi-Agent 서비스 실전 프로젝트 - 최우수 수료 (2026.06 – 2026.09)

---

제품의 요구사항을 이해하고, 데이터와 사용자 흐름을 연결하며, 예외 상황까지 고려해 구현하는 엔지니어로 성장하고 있습니다. 새로운 기술을 도입하는 것 자체보다 실제 문제를 해결하는 데 필요한 구조와 검증 방법을 찾는 것을 중요하게 생각합니다.
