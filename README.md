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
Reached **20+ contributors**
[![Powered by OrcaRouter](https://img.shields.io/badge/Powered_by-OrcaRouter-2563eb)](https://www.orcarouter.ai/ref/ref_210b976a004fb5022f5f)


Deployed Link: https://pypi.org/project/ai-driven-e2e/#description

Automatically repair broken Playwright E2E tests. When a UI change renames or restructures an element and a test's selector breaks, the engine diagnoses the failure, patches the broken selector/wait, verifies the new selector against the live DOM, then re-runs the test until it passes (or a retry cap is hit) and writes the fix back — as a local CLI or a CI GitHub Action that opens a patch PR.

**주요 성과**

1. **LangGraph 기반 AI 자가 치유(Self-Healing) E2E 테스트 자동화 엔진 구축**
    - 문제 : UI 변경(ID, 클래스명 변경 등) 시마다 E2E 테스트 셀렉터 단절로 인해 CI/CD 파이프라인 실패 및 수동 유지보수 공수가 과도하게 발생하는 Flakiness 문제
    - **조치:**
        - **LangGraph 4레이어 파이프라인 설계:** `Diagnoser` → `Patch Generator` → `Selector Verifier` → `Test Runner`로 이어지는 자율 피드백 루프 구축
        - **환각 방지 검증 레이어:** Live DOM과 연동해 패치된 셀렉터의 유일성(1:1 매칭)을 사전 검증하는 `Selector Verifier` 구현으로 잘못된 패치 차단
        - **가드레일 및 이중 모드:** 테스트 로직/검증문(Assertion)은 유지하는 오토 힐링(`heal`) 모드와 Source-level 피드백을 PR 주석으로 전달하는 `review` 모드 선택적 지원
    - UI 변경으로 인한 Playwright 테스트 깨짐 발생 시, 인간의 개입 없이 깨진 셀렉터/대기 조건을 자동 진단·수정하여 테스트를 통과시키는 오픈소스 라이브러리 및 GitHub Action 구현

**2. CLI–GitHub Actions 통합 및 테스트 복구 워크플로우 자동화**

- **문제:** AI 기반 테스트 복구를 실제 개발 과정에 적용하려면 로컬 실행부터 CI 실패 감지, 수정 결과 검토까지 일관된 연동 체계 필요
- **조치:**
    - **CLI 중심 실행 구조 통합:** 로컬과 CI에서 동일한 `e2e-healer` 실행 경로를 사용하도록 구성하고, 단일 테스트 및 전체 테스트 스위트의 실패 파일별 복구 지원
    - **CI 후속 처리 표준화:** 실행 결과를 `passed` / `healed` / `unhealed` / `reviewed`로 구분하고, 스키마 버전과 유형 식별자를 포함한 JSON 리포트 제공
    - **패치 PR 연동:** 복구 결과와 변경 요약을 활용한 패치 PR 생성 및 소스 코드 개선 제안을 전달하는 인라인 PR 리뷰 워크플로우 구성
- **결과:** 로컬 진단부터 CI 자동 복구·PR 검토까지 연결되는 개발 워크플로우 구축. 실제 랜딩 페이지 CTA의 ID 변경 사례에서 **기존 URL 검증문을 유지한 채 셀렉터만 수정하여 첫 복구 시도에 테스트 통과**

**3. 멀티 LLM 프로바이더 추상화 및 구조화 응답 안정성 확보**

- **문제:** 특정 LLM에 종속된 구조는 도입 환경별 모델 선택을 제한하며, 모델별 응답 형식 차이와 비정상 JSON 출력은 자동 복구 파이프라인의 실패 요인으로 작용
- **조치:**
    - **6개 LLM 백엔드 지원:** NVIDIA NIM, OpenAI, Anthropic, Ollama, DeepSeek, OrcaRouter를 공통 설정 체계로 연결하여 환경변수 기반 프로바이더·모델 전환 지원
    - **구조화 출력 처리 통합:** 프로바이더별 JSON Schema 및 Tool-use 방식을 공통 패치·리뷰 출력 스키마에 맞춰 처리
    - **응답 오류 복구:** 구조화 응답 파싱 실패 시 재시도 후 패치 생성 피드백 루프로 연결하여 후속 복구 시도 지원
    - **로컬 실행 지원:** Ollama 연동 및 선택적 의존성 분리로 외부 API 없이 동작하는 모델 실행 환경 제공
- **결과:** 동일한 복구 엔진에서 클라우드 API와 로컬 모델을 선택할 수 있는 확장 구조 확보. 기존 NVIDIA 설정과의 하위 호환성을 유지하며 모델 선택 범위 확대

**4. 변경 맥락 기반 진단 컨텍스트 구성 및 재현 가능한 검증 체계 구축**

- **문제:** 테스트 실패 로그와 소스 파일 전체를 LLM에 전달하면 불필요한 정보가 포함되며, UI 변경과 셀렉터 실패 간 관계를 명확히 파악하기 어려움
- **조치:**
    - **진단 입력 전처리:** Playwright 실패 로그와 `git diff`에서 실패 셀렉터 및 변경된 DOM 속성을 추출하여 진단 맥락 구성
    - **컨텍스트 비교 벤치마크:** 전체 파일 입력과 관련 JSX 노드 중심 입력의 프롬프트 토큰 추정치를 비교하는 CLI 명령 구현
    - **검증된 복구 이력 관리:** 로컬 복구 이력 조회·저장을 지원하고, 실행별 이력 사용 여부를 선택할 수 있는 옵션 제공
    - **재현 가능한 E2E 데모:** React·Vite 예제 앱에 실제 UI 변경 diff를 적용하여 테스트 실패 → 자동 패치 → Live DOM 검증 → 재실행 과정을 재현하도록 구성
- **결과:** 진단 컨텍스트의 토큰 사용량을 비교할 수 있는 측정 기반 마련. 버튼 ID 변경 데모에서 **수정된 셀렉터의 DOM 단일 매칭과 테스트 통과를 종단 간 검증**

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


### Side Project
SignalFlow - Kafka·Flink 기반 비정형 이벤트 처리와 LangGraph 기반 복구 에이전트를 결합하여, 장애 원인 분석부터 수정안 검증·운영자 승인까지 연결하는 플랫폼 개발

**주요 성과**

**1. LangGraph 기반 장애 이벤트 분석 및 복구 제안 워크플로우 구축**

- **문제**: 실패 이벤트가 DLQ(Dead Letter Queue)에 적재된 이후, 운영자가 원본 데이터와 로그를 직접 대조하여 원인과 수정 가능 여부를 판단해야 하는 수동 복구 구조
- **조치**:
    - LangGraph 기반으로 **오류 원인 분류 → 수정 제안 → 스키마 검증**으로 이어지는 복구 에이전트 흐름 구현
    - 오류 원인, 수정 payload, 변경 diff, 신뢰도 및 위험 사유를 구조화하여 반환하도록 분석 결과 설계
    - 필수 비즈니스 값 누락 및 안전한 복원이 불가능한 이벤트를 보류 상태로 격리
- **결과**: 개별 로그에 분산된 장애 분석 정보를 구조화하고, 운영자가 수정 근거와 위험성을 함께 검토할 수 있는 일관된 복구 절차 확보

**2. Pydantic 검증 및 Human-in-the-Loop 기반 복구 통제 설계**

- **문제**: LLM이 생성한 수정안을 검증 없이 재사용하거나 단순 재시도할 경우, 동일 오류 반복 및 잘못된 데이터 재투입 위험 존재
- **조치**:
    - LLM의 수정 제안에 **서버 측 Pydantic 이벤트 스키마 검증**을 적용하여 복구안의 유효성 확인
    - 스키마 오류 유형이면서 검증을 통과한 제안만 승인 대기 상태로 전환하도록 조건 명시
    - 검증 통과와 운영자 승인을 분리하고, 승인 이력이 있는 이벤트만 재처리 어댑터에 전달하도록 API 제어
    - 승인·보류 결정 및 처리 이력을 SQLite와 감사 로그로 기록
- **결과**: AI 제안에 대한 검증·승인·추적 체계를 구축하고, 승인된 이벤트의 재처리 흐름을 시뮬레이션으로 구현하여 자동화 과정의 운영자 통제권 확보

**3. Kafka·PyFlink 기반 실시간 이벤트 처리 및 다중 저장소 연계**

- **문제**: 비정형 이벤트를 검색에 활용하려면 데이터 형식 검증, 품질 평가, 임베딩 생성 및 관계 정보 적재를 연결하고 처리 실패 이벤트를 별도로 관리해야 하는 과제
- **조치**:
    - Protobuf 기반 이벤트 계약과 Kafka 토픽을 구성하고, PyFlink의 **역직렬화 → 데이터 품질 평가 → 임베딩** 처리 흐름 구현
    - 벡터·메타데이터를 ClickHouse에, 엔터티 관계 정보를 Neo4j에 전달하는 저장 경로 구성
    - 처리 중 발생한 오류 이벤트를 DLQ로 분리하여 복구 분석 흐름과 연계
- **결과**: 이벤트 수집부터 품질 검사·저장까지 이어지는 스트리밍 처리 기반을 마련하고, 정상 데이터 처리와 실패 이벤트 검토 경로를 분리한 아키텍처 구축

**4. Next.js·FastAPI 기반 장애 복구 검토 대시보드 구축**

- **문제**: 원본 데이터, AI 수정안, 검증 결과 및 처리 이력이 분산되어 있으면 운영자가 복구 적합성을 판단하기 어렵고 잘못된 상태에서 승인할 가능성 존재
- **조치**:
    - Next.js 기반으로 **DLQ 목록·상세, 원본/수정 payload, 변경 diff, 검증 결과, 위험 사유 및 감사 로그**를 통합한 검토 화면 구현
    - FastAPI의 분석·승인·보류·재처리 API를 연결하여 화면에서 복구 검토 절차를 수행하도록 구성
    - 분석 전·보류·재처리 완료 등 승인 불가 상태에서 버튼을 비활성화하고 사유 표시
    - fixture 3건 기반 검토 서비스와 프론트엔드 자동 데모를 구성하여 외부 스트리밍 인프라 없이 핵심 흐름 재현
- **결과**: 장애 분석 근거 확인부터 운영자 결정까지 한 화면에서 수행할 수 있는 검토 환경을 구축하고, 독립적으로 실행 가능한 시연 환경 확보

**5. 하이브리드 검색·그래프 컨텍스트 및 검색 평가 기반 구축**

- **문제**: 비정형 이벤트의 의미적 유사성, 키워드 일치 및 엔터티 관계를 함께 활용하고 검색 결과의 관련도를 검증할 수 있는 구조 필요
- **조치**:
    - ClickHouse 기반 벡터·키워드 하이브리드 검색과 리랭킹 구성 요소 구현
    - Neo4j 그래프 컨텍스트 조회를 결합하여 검색 결과에 엔터티 관계 정보 제공
    - vLLM 호환 API를 활용한 `LLMJudgeEvaluator`와 Golden Dataset 기반 GraphRAG 평가 예제 작성
- **결과**: 의미·키워드·관계 정보를 함께 활용하는 검색 기반을 마련하고, 검색 문맥의 관련도를 평가할 수 있는 검증 경로 확보

**기타 개발 및 검증**

- **테스트 구성**: pytest 기반 API·스키마 검증·에이전트 라우팅·복원력 테스트와 Docker 기반 인프라 테스트 구성
- **복구 지표 수집**: Prometheus 기반 복구 시도 횟수, 처리 시간 및 서킷 브레이커 상태 메트릭 기록
- **장애 실험 구성**: Chaos Mesh 기반 vLLM 네트워크 지연 및 Kafka Pod 종료 실험 매니페스트 작성
- **실행·배포 환경 구성**: Docker Compose 기반 개발 인프라와 검토 서비스 단독 실행을 위한 Dockerfile·배포 설정 작성

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
| **코드랩 AI Multi-Agent 서비스 실전 프로젝트**     | 2026.06 - 2026.09   |
