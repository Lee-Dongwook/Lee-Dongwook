# Lee Dongwook

## 👋 안녕하세요! 2년차 프론트엔드 엔지니어 이동욱입니다.

[![Resume Badge](https://img.shields.io/badge/notion-D3D3D3?style=flat&logo=notion&logoColor=white)](https://zigzag-citrus-12b.notion.site/cd0f3792573b4f45bfb94e4493be1adf)
[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![Axflow](http://img.shields.io/badge/Axflow-8000FF?style=flat&logo=null&logoColor=white&link=https://axflow.io)](https://axflow.io/)

- 제조 AI 에이전트 플랫폼(AxFlow)의 **Document Agent 단일 구조에서 Agent + Workflow 확장 개편을 주도**하고, FE 아키텍처 및 공통 스키마 설계를 총괄한 프론트엔드 엔지니어입니다.
- **Google A2UI 프로토콜 및 SSE 스트리밍 기반 동적 UI 렌더러 구축**, 데이터 시각화 공통 컴포넌트 총괄을 통해 비정형 AI 응답 및 대용량 데이터 렌더링 환경을 표준화했습니다.
- **테스트 인프라(Playwright, Storybook, Vitest) 구축 및 에이전트 판단 재현 설계**를 통해 품질 기준을 수립하고, Critical Path 최적화(52% 단축)로 서비스 안정성을 개선했습니다.

## Work Experience
|   회사명    |    직급     |  기간  | 
|--------|---------|---------|
| **(주) FutureWorkLab** | 대리 | 2024.10 - Present |
| **(주) EXEM** | 인턴 | 2023.07 - 2023.12 |

### 주요 성과

**1. 워크플로우 FE 아키텍처 총괄 및 Agent + Workflow 확장 개편**

- **문제**: 기존 Document Agent 중심 구조로는 복잡한 제조 현장의 다단계 작업 흐름(Workflow) 및 에이전트 간 연쇄 작용을 유연하게 표현하기 어려운 한계 존재
- **조치**:
    - 단일 에이전트 구조에서 **Agent + Workflow 확장 구조로 FE 아키텍처 전면 개편** 및 공통 스키마 설계 주도
    - 문서 생성 에이전트 이관(14건) 진행 및 데이터 시각화 공통 컴포넌트 설계/총괄
    - 작업장, 운영(Ops), 실험실·평가 등 핵심 도메인 메뉴의 FE 오너로서 서비스 전반의 도메인 파편화 해소
- **결과**: 확장 가능한 워크플로우 파이프라인 기반을 마련하여 신규 에이전트 및 연동 기능의 신속한 통합 구조 확보

**2. Google A2UI 프로토콜 기반 선언적 동적 UI 렌더러 구축**

- **문제:** AI 에이전트가 생성하는 문서 양식이 템플릿마다 구조가 다르고, 20종 이상의 다양한 필드 타입이 존재하여 정적 UI 컴포넌트 방식으로는 지속적인 변경 요구 대응 불가
- **조치**:
    - `fieldType` 기반 재귀적 렌더 트리(Render Tree) 설계 및 레이아웃/입력 요소 분리
    - `react-hook-form` 제네릭 연동을 통한 타입 안전한 동적 폼 제어
    - `allowedFieldPaths` 기반 필드 경로 검증 로직으로 비정상 스키마 사전 차단 및 렌더링 안정성 확보
- **결과:** 비정형 AI 응답에 유연하게 대응하는 렌더러를 구축하여, 신규 문서 양식 추가 시 프론트엔드 코드 수정 및 배포 없이 JSON 스키마 정의만으로 즉시 대응 가능한 파이프라인 확보

**3. SSE 기반 실시간 문서 생성 스트리밍 파이프라인 구축**

- **문제:** BE/AI 측의 문서 청킹·파싱 처리가 장시간 소요됨에 따라, 기존 단일 HTTP 요청 구조에서 타임아웃 응답 단절 및 대기 시간 동안의 사용자 불만 유발
- **조치:**
    - `axios`의 `ReadableStream` 미지원 한계를 분석하고, `fetch` + `ReadableStream` 기반 SSE 스트리밍 체계로 전면 전환
    - AsyncGenerator 기반 `readSSELines` 유틸 구현으로 청크 경계 버퍼링 및 불완전 메시지 파싱 처리
    - `onChunk` 파라미터 유무에 따른 이중 경로 설계로 기존 API 호환성 유지 및 401/429 예외 핸들링 표준화
- **결과:** AI 문서 생성 시 발생하던 요청 타임아웃 및 무응답 대기 상태를 해소하고, 청크 단위 점진적 렌더링을 통해 이탈 없는 연속적 사용자 경험(UX) 제공

**4. 품질 보증을 위한 테스트 인프라 구축 및 테스트 가능성 설계**

- **문제**: AI 에이전트의 비확정적 응답 특성으로 인해 UI 및 작업 흐름에 대한 무작위 결함 진단 및 정밀한 회귀 테스트(Regression Test) 실행의 어려움 발생
- **조치**:
    - Playwright, Storybook, Vitest 기반의 통합 **테스트 인프라 구축 및 조직 내 테스트 커버리지 기준 수립**
    - **에이전트 판단 재현 설계**를 통해 비확정적 AI 실행 경로를 결정론적으로 모킹(Mocking) 및 검증 가능한 구조로 개편
- **결과**: 테스트 가능성(Testability) 확보를 통해 에이전트 워크플로우의 렌더링/로직 결함을 사전에 검증할 수 있는 안정적 개발 환경 구축

**5. Critical Path 최적화 및 초기 렌더링 성능 개선**

- **문제:** 초기 서비스 진입(/main) 시 직렬화된 리소스 로딩 및 과도한 서비스 워커 프리캐시(Pre-cache) 세팅으로 인해 초기 렌더링 지연 발생
- **조치:**
    - Chrome DevTools 프로파일링을 통해 초기 진입 시 불필요한 리소스 로드 병목 지점 진단
    - 코드 스플리팅(Code Splitting) 및 렌더링 경로 분리로 핵심 리소스 즉시 로드 구조 전환
    - Service Worker 프리캐시 대상을 필수 리소스 중심으로 재정의하여 캐시 변동성 최소화 및 캐시 신뢰성 향상
- **결과:** 초기 진입 경로의 불필요한 작업 병목을 제거하여 Critical Path 지연 시간을 52% 단축하고, 사용자 체감 TTI(Time to Interactive) 유의미하게 개선


**기타 담당 업무 및 마이그레이션**
- **프로젝트 Zero-base 구축:** 린팅(ESLint/Prettier), 디렉토리 구조, 개발 환경 초기 세팅 전담
- **코어 라이브러리 마이그레이션:** Tailwind CSS (v3 → v4), Next.js (v15 → v16) 단계적 업그레이드 및 점진적 영역 영향도 검증
- Linear 기반으로 2주 단위 스프린트에서 티켓/서브 티켓을 생성하고 우선순위를 관리
- Slack 개발 채널에서 신규 이슈/트렌드/기술 고민을 공유하며 논의 문화에 참여
---

#### Open-Source

[![E2E-Healer](http://img.shields.io/badge/E2EHealer-20c997?style=flat&logo=null&logoColor=white&link=https://github.com/Lee-Dongwook/E2E-Self-Heal)](https://github.com/Lee-Dongwook/E2E-Self-Heal)
Reached **20+ contributors**,


Deployed Link: https://pypi.org/project/ai-driven-e2e/#description


Automatically repair broken Playwright E2E tests. When a UI change renames or restructures an element and a test's selector breaks, the engine diagnoses the failure, patches the broken selector/wait, verifies the new selector against the live DOM, then re-runs the test until it passes (or a retry cap is hit) and writes the fix back — as a local CLI or a CI GitHub Action that opens a patch PR.

#### Open Source Contribute List
- **https://github.com/VIDAKHOSHPEY22/news-daily-bot/pull/2**
- **https://github.com/VIDAKHOSHPEY22/news-daily-bot/pull/3** (worked as a collaborator)
- **https://github.com/jiunshinn/serve-emul/pull/46**
- **https://github.com/jiunshinn/serve-emul/pull/45**
- **https://github.com/facebook/astryx/pull/4292**
- **https://github.com/facebook/astryx/pull/4284**
- **https://github.com/facebook/astryx/pull/3747**
- **https://github.com/meursyphus/flitter/pull/91**
- **https://github.com/meursyphus/headless-chart/pull/8**
- **https://github.com/meursyphus/headless-chart/pull/12**

## Tech Stack
[![JavaScript](https://img.shields.io/badge/JavaScript-%23F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) [![TypeScript](https://img.shields.io/badge/TypeScript-%233178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
![Python](https://img.shields.io/badge/Python-%233178C6?style=flat&logo=python&logoColor=white)
[![React](https://img.shields.io/badge/React-%2361DAFB?style=flat&logo=react&logoColor=white)](https://reactjs.org/) [![React Native](https://img.shields.io/badge/React_Native-%2361DAFB?style=flat&logo=react&logoColor=white)](https://reactnative.dev/) [![Expo](https://img.shields.io/badge/Expo-000020?style=flat&logo=expo&logoColor=white)](https://expo.dev/) [![NextJS](https://img.shields.io/badge/Next.js-%23000000?style=flat&logo=next.js&logoColor=white)](https://nextjs.org/) [![Redux](https://img.shields.io/badge/Redux-%23764ABC?style=flat&logo=redux&logoColor=white)](https://redux.js.org/) [![Zustand](https://img.shields.io/badge/Zustand-%23000000?style=flat&logo=zustand&logoColor=white)](https://github.com/pmndrs/zustand)
 [![React Query](https://img.shields.io/badge/React_Query-%2385d0d3?style=flat&logo=react-query&logoColor=white)](https://react-query.tanstack.com/) [![express](https://img.shields.io/badge/express-green?style=flat&logo=express&logoColor=white)](https://www.npmjs.com/package/express) [![Node.js](https://img.shields.io/badge/Node.js-43853D?style=flat&logo=node.js&logoColor=white)](https://nodejs.org/) ![FastAPI](https://img.shields.io/badge/FastAPI-%233178C6?style=flat&logo=fastapi&logoColor=white) [![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat&logo=prisma&logoColor=white)](https://www.prisma.io/) ![MongoDB Badge](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=MongoDB&logoColor=white) ![PostgreSQL Badge](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=PostgreSQL&logoColor=white)
![Styled Components Badge](https://img.shields.io/badge/styled%20components-DB7093?style=flat-square&logo=styled-components&logoColor=white) [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-%231a202c?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/) 
[![Storybook](https://img.shields.io/badge/Storybook-%23FF4785?style=flat&logo=storybook&logoColor=white)](https://storybook.js.org/) [![Playwright](https://img.shields.io/badge/Playwright-%231099FF?style=flat&logo=playwright&logoColor=white)](https://playwright.dev/)
[![GitHub](https://img.shields.io/badge/GitHub_Action-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/) [![Docker](https://img.shields.io/badge/Docker-%232496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=Vercel&logoColor=white) ![Amazon AWS](https://img.shields.io/badge/Amazon%20AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white) ![LangGraph](https://img.shields.io/badge/LangGraph-Agents-2C3E50)



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
| **원티드 프리온보딩 프론트엔드 3월 챌린지**     | 2024.03           |
| **코드랩 AI Multi-Agent 서비스 실전 프로젝트**     | 2026.06 -           |
