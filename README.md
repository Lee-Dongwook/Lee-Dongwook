# Lee Dongwook

## 👋 안녕하세요! 2년차 프론트엔드 엔지니어 이동욱입니다.

[![Resume Badge](https://img.shields.io/badge/notion-D3D3D3?style=flat&logo=notion&logoColor=white)](https://zigzag-citrus-12b.notion.site/cd0f3792573b4f45bfb94e4493be1adf)
[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![Axflow](http://img.shields.io/badge/Axflow-8000FF?style=flat&logo=null&logoColor=white&link=https://axflow.io)](https://axflow.io/)

#### My newly planned to operating an Open-Source

[![E2E-Healer](http://img.shields.io/badge/E2EHealer-20c997?style=flat&logo=null&logoColor=white&link=https://github.com/Lee-Dongwook/E2E-Self-Heal)](https://github.com/Lee-Dongwook/E2E-Self-Heal)
Reached **10+ contributors**, 14/07/2026 16:00 KST


Automatically repair broken Playwright E2E tests. When a UI change renames or restructures an element and a test's selector breaks, the engine diagnoses the failure, patches the broken selector/wait, verifies the new selector against the live DOM, then re-runs the test until it passes (or a retry cap is hit) and writes the fix back — as a local CLI or a CI GitHub Action that opens a patch PR.

#### Open Source Contribute List
- **https://github.com/jiunshinn/serve-emul/pull/46**
- **https://github.com/jiunshinn/serve-emul/pull/45**
- **https://github.com/facebook/astryx/pull/3747**
- **https://github.com/meursyphus/flitter/pull/91**
- **https://github.com/meursyphus/headless-chart/pull/8**
- **https://github.com/meursyphus/headless-chart/pull/12**

---

### 단순한 UI 구현을 넘어서 데이터의 진정한 가치를 전달하는 개발자로 성장합니다.
프로젝트를 수행하며 발생한 문제들을 해결하고, 더 나은 사용자 경험 제공과 성능 향상을 목표로 새로운 기술을 적용해보며 학습을 꾸준히 합니다.

단순 UI 구현을 넘어, 렌더링 / 흐름 / 리소스 로딩 / 브라우저 & 런타임 메모리 관점까지 고려하며 문제의 근본 원인을 파악하고 구조적으로 해결하는데 집중합니다.

동료 피드백을 수용하여 부족한 부분을 지속적으로 개선하고자 노력합니다.


## Work Experience
|   회사명    |    직급     |  기간  | 
|--------|---------|---------|
| **(주) FutureWorkLab** | 사원 | 2024.10 - Present |
| **(주) EXEM** | 인턴 | 2023.07 - 2023.12 |


### 요약 (3줄)

- 제조 AI 에이전트 플랫폼(AxFlow)의 프론트엔드를 초기 구축부터 운영까지 담당, 초기 렌더링 Critical Path를 **52% 단축한** 프론트엔드 개발자입니다.
- 초기 렌더링 경로 최적화, 캐시 구조 개선 등 **성능/안정성** 문제를 주도적으로 개선해왔습니다.
- DevTools 프로파일링 기반으로 병목을 진단하고, 코드 스플리팅·캐시 구조 재설계 등 **구조적 개선으로 재발을 방지**합니다.

### 주요 성과

#### 1) A2UI 프로토콜 기반 선언적 UI 렌더러 구현

- **결과:** Google A2UI 프로토콜을 채택, 에이전트가 전송한 JSON 스키마를2 자체 디자인 시스템 컴포넌트로 동적 렌더링하는 클라이언트 렌더러 구현
- **문제:** 에이전트가 생성하는 문서 양식이 템플릿마다 구조가 다르고, 필드 타입이 20종 이상으로 다양하여 정적 UI로는 대응 불가
- **조치:**
   - `fieldType` 기반 재귀적 렌더 트리 설계 (row, column, group 등 레이아웃 + text, select, file 등 입력 요소)
   - react-hook-form 제네릭 통합으로 타입 안전한 동적 폼 제어
   - `allowedFieldPaths` 기반 필드 경로 검증으로 잘못된 스키마 방어

#### 2) SSE 기반 실시간 문서 생성 스트리밍 파이프라인 구축

- **결과:** BE/AI의 문서 청킹·파싱 시 장시간 처리로 발생하는 timeout 응답 단절을 해소, 청크 단위 점진적 렌더링으로 사용자 경험 연속성 확보
- **문제:** 문서 생성 요청이 BE/AI 측 처리 시간에 의존하여, 일반 HTTP 요청으로는 timeout 발생 또는 완료까지 무응답 상태 지속
- **조치:**
   - axios의 ReadableStream 미지원 한계를 파악, fetch + ReadableStream 기반 SSE 스트리밍으로 전환
   - `readSSELines` AsyncGenerator 유틸 구현 — 청크 경계 버퍼링으로 불완전 메시지 처리
   - 스트리밍/일반 요청 이중 경로 설계 (`onChunk` 유무로 분기), 기존 API 호환성 유지
   - 인증(401)·Rate Limit(429) 핸들링을 fetch 경로에도 일관 적용

#### 3) 초기 렌더링 성능 개선 (Critical Path 52% 단축)

- **결과:** Critical Path 지연 시간 약 **52% 단축** (7,868ms → 3,756ms)
- **문제:** 초기 렌더링 경로에서 불필요하게 직렬화된 작업으로 인해 TTI가 지연됨
- **조치:** 초기 진입(/main) 시 즉시 필요한 리소스만 로드하도록 구조 분리, 렌더링 병목 제거
- **검증:** Chrome DevTools Performance / Lighthouse 기준 전후 비교 측정

#### 4) 서비스 워커 프리캐시 안정성 개선

- **결과:** pre-cache 단계에서 불필요한 build manifest 리소스를 제외하여 캐시 안정성 개선
- **문제:** pre-cache 대상이 과도해 캐시 신뢰성이 떨어지고 업데이트 시 변동성이 커짐
- **조치:** 캐시 대상 리소스를 재정의하고 필수 리소스 중심으로 최소화

#### 5) 프로젝트 마이그레이션 및 업그레이드 주도

- **프로젝트 초기 구성:** LinkBrain 프론트엔드 프로젝트를 zero-base에서 구축 (개발 환경, 디렉토리 구조, 린팅 설정)
- **Tailwind CSS:** v3.4.5 → v4.1.8 업그레이드 (영향 범위 점검, 점진적 마이그레이션)
- **Next.js:** v15.2.6 → v15.5.9 → v16.1.1 단계적 업그레이드 (변경 사항 검증 및 리스크 사전 점검)

#### 협업

- Linear 기반으로 2주 단위 스프린트에서 티켓/서브 티켓을 생성하고 우선순위를 관리
- Slack 개발 채널에서 신규 이슈/트렌드/기술 고민을 공유하며 논의 문화에 참여
- 백엔드 팀원들과 Spring AI 스터디를 진행하며 서버 구조와 AI 연계 흐름 이해 확장

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
