# Lee Dongwook

## 👋 안녕하세요! 프로덕트 엔지니어 이동욱입니다.

[![Resume Badge](https://img.shields.io/badge/notion-D3D3D3?style=flat&logo=notion&logoColor=white)](https://zigzag-citrus-12b.notion.site/cd0f3792573b4f45bfb94e4493be1adf)
[![LinkedIn Badge](http://img.shields.io/badge/-LinkedIn-0072b1?style=flat&logo=linkedin&link=https://www.linkedin.com/in/dong-wook-lee-1095112a0/)](https://www.linkedin.com/in/dong-wook-lee-1095112a0/)
[![Velog Badge](http://img.shields.io/badge/-Velog-20c997?style=flat&logo=velog&logoColor=white&link=https://velog.io/@dlehddnr99/)](https://velog.io/@dlehddnr99/)
[![LinkBrain](http://img.shields.io/badge/LinkBrain-8000FF?style=flat&logo=null&logoColor=white&link=https://linkbrain.kr)](https://linkbrain.kr/)

### 문제를 발견하고 기술적으로 해결하는 과정을 꾸준히 지속하고자 합니다.
프로젝트를 수행하며 발생한 문제들을 해결하고, 더 나은 사용자 경험 제공과 성능 향상을 목표로 새로운 기술을 적용해보며 학습을 꾸준히 합니다.   

동료 피드백을 수용하여 부족한 부분을 지속적으로 개선하고자 노력합니다.


## Work Experience
|   회사명    |    직급     |  기간  | 
|--------|---------|---------|
| **(주) FutureWorkLab** | 사원 | 2024.10 - |
| **(주) EXEM** | 인턴 | 2023.07 - 2023.12 |


## Main Projects

### FutureWorkLab Corp - LinkBrain (Currently 'll switching as Axflow(tentative name)) (Worked as an Front Develop + Sub Backend Develop)

#### Intro
- LinkBrain is an AI-Powered knowledge management and collaboration platform that supports multi-platform environments, including web / mobile / Chrome Extensions (currently developing).. etc.
- Implemented based on React, Next.js, Supabase, Tanstack Query, Zustand on Frontend and FastAPI, LangChain, LangGraph, Postgresql, Alembic on Backend and AI.
- primarily responsible for core front-end functions related to web apps, Chrome extension and document agents.


#### Migration & Project Architecture
- **Established initial frontend project configuration for LinkBrain** defining the development environment and foundational architecture.
- **Upgraded Tailwind CSS from v3.4.5 to v4.1.8**, conducting impact analysis on existing styles and executing a progressive migration.
- **Executed phased upgrades of Next.js**, verifying breaking changes and API updates at each stage.
- **Maintained service stability** by proactively evaluating functional changes and potential risks associated with major framework updates.

#### Initial Rendering Performance Optimization
- **Reduced Critical Path latency by approximately 52%**(7,868ms → 3,756ms) by eliminating unnecessary serialized tasks in the initial rendering path.
- **Resolved rendering bottlenecks**, by decoupling the resource loading structure to ensure only essential assets are loaded upon entering
- **Enhanced UX** by optimizing the client-side rendering path independently of server response fluctuations.
- **Improved cache stability** by excluding redundant build manifest resources from the Service Worker pre-cache stage.

#### Collaboration & Communication
- **Managed tasks autonomously** within a 2-week Agile sprint cycle using Linear, creating and tracking granular tickets and sub-tickets.
- **Fostered a collaborative engineering culture** by sharing new issues, development trends, and technical challenges via Slack.
- **Expanded cross-functional knowledge** by participating in a Spring AI study with backend engineers to understand server architecture and AI integration flows.

#### ETC
- Modified Nginx-based **Reverse Proxy + Cache Strategy** to resolve static chunk caching issues in Safari and mobile environments.
- Configured Next.js standalone + PM2/Node server in EC2 deployment environment.
- Configured **temporary EC2 / NCP deployment environment** to resolve Chrome Inspect and Android device debugging limitations.
- Performed Pair Programming using tmux + Gemini CLI + SSH Environment based on ncp gpu server.

## Tech Stack
[![JavaScript](https://img.shields.io/badge/JavaScript-%23F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) [![TypeScript](https://img.shields.io/badge/TypeScript-%233178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
![Python](https://img.shields.io/badge/Python-%233178C6?style=flat&logo=python&logoColor=white)
[![React](https://img.shields.io/badge/React-%2361DAFB?style=flat&logo=react&logoColor=white)](https://reactjs.org/) [![React Native](https://img.shields.io/badge/React_Native-%2361DAFB?style=flat&logo=react&logoColor=white)](https://reactnative.dev/) [![Expo](https://img.shields.io/badge/Expo-000020?style=flat&logo=expo&logoColor=white)](https://expo.dev/) [![NextJS](https://img.shields.io/badge/Next.js-%23000000?style=flat&logo=next.js&logoColor=white)](https://nextjs.org/) [![Redux](https://img.shields.io/badge/Redux-%23764ABC?style=flat&logo=redux&logoColor=white)](https://redux.js.org/) [![Zustand](https://img.shields.io/badge/Zustand-%23000000?style=flat&logo=zustand&logoColor=white)](https://github.com/pmndrs/zustand)
 [![React Query](https://img.shields.io/badge/React_Query-%2385d0d3?style=flat&logo=react-query&logoColor=white)](https://react-query.tanstack.com/) [![express](https://img.shields.io/badge/express-green?style=flat&logo=express&logoColor=white)](https://www.npmjs.com/package/express) [![Node.js](https://img.shields.io/badge/Node.js-43853D?style=flat&logo=node.js&logoColor=white)](https://nodejs.org/) ![FastAPI](https://img.shields.io/badge/FastAPI-%233178C6?style=flat&logo=fastapi&logoColor=white) [![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat&logo=prisma&logoColor=white)](https://www.prisma.io/) ![MongoDB Badge](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=MongoDB&logoColor=white) ![PostgreSQL Badge](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=PostgreSQL&logoColor=white)
![Styled Components Badge](https://img.shields.io/badge/styled%20components-DB7093?style=flat-square&logo=styled-components&logoColor=white) [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-%231a202c?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/) 
[![Storybook](https://img.shields.io/badge/Storybook-%23FF4785?style=flat&logo=storybook&logoColor=white)](https://storybook.js.org/) [![Playwright](https://img.shields.io/badge/Playwright-%231099FF?style=flat&logo=playwright&logoColor=white)](https://playwright.dev/)
[![GitHub](https://img.shields.io/badge/GitHub_Action-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/) [![Docker](https://img.shields.io/badge/Docker-%232496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=Vercel&logoColor=white) ![Amazon AWS](https://img.shields.io/badge/Amazon%20AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)



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

