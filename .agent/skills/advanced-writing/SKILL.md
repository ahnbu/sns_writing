---
name: Advanced Writing Flow
description: 7-step advanced writing workflow (Logic Filter -> Insight Curator -> Persona Writer -> Veteran Editor -> Threads Generator -> Critic -> Refiner) for high-quality content creation.
---

# Advanced Writing Flow

이 스킬은 고품질의 임팩트 있는 글을 작성하기 위한 **5단계 프로세스**를 지원합니다. 논리적 진단부터 리서치 큐레이션, 페르소나 집필, 최종 편집, 그리고 소셜 미디어 확산 전략까지 연결됩니다.

## Workflow Overview

### 📋 Step 0. [원문 기록] The Original Draft

- **목표:** 사용자가 입력한 초안 원본을 보존합니다.
- **Action:** 시작 시 사용자의 입력을 `00_draft.md`로 저장합니다.

### 📋 Step 1. [진단 및 해체] The Logic Filter

- **목표:** 초안의 '기름기'를 제거하고 구조적 뼈대를 잡습니다.
- **Prompt:** `prompts/step1_logic.md`

### 📋 Step 2. [탐색 및 큐레이션] The Insight Curator

- **목표:** Perplexity MCP를 사용하여 현재 시점(**2026년**)에 맞는 **3가지 황금 조각(3 Golden Nuggets)**을 리서치합니다.
- **Prompt:** `prompts/step2_research.md`

### 📋 Step 3. [집필 및 스타일링] The Persona Writer

- **목표:** 뼈대와 리서치 자료를 바탕으로 페르소나를 입혀 초고를 완성합니다.
- **Prompt:** `prompts/step3_persona.md`

### 📋 Step 4. [편집 및 포장] The Veteran Editor

- **목표:** 모바일 가독성을 극대화하고 제목을 다듬습니다.
- **Prompt:** `prompts/step4_editor.md`

### 📋 Step 5. [확산 및 바이럴] The Threads Generator

- **목표:** 2026년 알고리즘에 최적화된 고몰입형 쓰레드 시리즈를 생성합니다.
- **Prompt:** `prompts/step5_threads.md`

### 📋 Step 6. [냉철한 검증] The Critic

- **목표:** '최종 원고(Step 4)'를 객관적으로 평가하고 약점을 찾아냅니다. (On-Demand 도구 `/critic`을 정규 과정으로 통합)
- **Prompt:** `prompts/step6_critic.md`

### 📋 Step 7. [최종 개선] The Refiner

- **목표:** Critic의 피드백을 반영하여 원고와 쓰레드 시리즈를 완벽하게 다듬어 재발행합니다.
- **Prompt:** `prompts/step7_refine.md`

### 📜 Step 8. [역화 기록] The History Keeper

- **목표:** 각 단계별 발전 과정, 피복 반영 내역, 주요 Pivot 포인트를 요약하여 기록 보관소(Archive)를 생성합니다.
- **Prompt:** `prompts/tools/history_keeper.md`

## ⚡ Execution Protocol (즉시 실행 원칙) - CRITICAL

에이전트는 사용자가 특정 단계의 진행을 승인하거나 명령하는 즉시, **추가적인 대화나 확인 절차 없이 즉시 도구(Tool)를 사용하여 결과 파일을 생성해야 합니다.**

## Output Management (자동 저장 규칙)

1. **Directory:** `output/{YYYYMMDD}_{Keyword}/`
2. **File Naming & Order:**
   - `00_draft.md`: 원본 초안
   - `01_logic_filter.md`: Step 1 결과
   - `02_research_nuggets.md`: Step 2 결과
   - `03_persona_draft.md`: Step 3 결과
   - `04_final_article.md`: Step 4 결과
   - `05_threads_series.md`: Step 5 결과
   - `06_critic_report.md`: Step 6 결과
   - `04_final_article_v2.md`: Step 7 결과 (수정본)
   - `05_threads_series_v2.md`: Step 7 결과 (수정본)
   - `07_history_archive.md`: Step 8 결과 (전체 히스토리 요약)

## How to Use

1. **Step 1:** 초안 입력 (자동으로 00, 01 수행)
2. **Step 2:** 리서치 수행
3. **Step 3:** 초고 집필
4. **Step 4:** 편집 및 최종 원고 완성
5. **Step 5:** 쓰레드 바이럴 게시물 생성
6. **Step 6:** Critic 검증
7. **Step 7:** 피드백 반영 및 v2 발행
8. **Step 8:** 히스토리 아카이브 기록

## 🛠️ On-Demand Tools (수시 호출 도구)

정해진 흐름(Flow) 외에, 사용자가 필요할 때 언제든 호출하여 글의 퀄리티를 점검하고 깊이를 더할 수 있는 특수 명령어입니다.

### 🛑 `/critic` (객관적 검증)

- **기능:** 아이디어 단계에서 논리적 허점과 레드 플래그를 찾아내어 '헛심 쓰기'를 방지합니다.
- **Prompt:** `prompts/tools/cmd_critic.md`

### 💡 `/insight` (본질 탐구)

- **기능:** 뻔한 주제를 구조적 모순이나 날카로운 통찰로 비틀어, 글의 '엣지'를 만듭니다.
- **Prompt:** `prompts/tools/cmd_insight.md`

### 🧐 `/editor` (편집장 멘토링)

- **기능:** 글을 고쳐주는 게 아니라, '평가'하고 '조언'합니다. 필자의 성장을 돕는 피드백을 제공합니다.
- **Prompt:** `prompts/tools/cmd_editor.md`
