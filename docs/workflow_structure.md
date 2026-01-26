# SNS 글쓰기 워크플로우 구조

## 1. Advanced Writing Flow 프로세스

```mermaid
flowchart TD
    Start([시작: 원본 아이디어]) --> Step0[Step 0: Draft<br/>00_draft.md]
    Step0 --> Step1[Step 1: Logic Filter<br/>01_logic_filter.md<br/>논리 구조 분석]
    Step1 --> Step2[Step 2: Insight Curator<br/>02_research_nuggets.md<br/>리서치 & 데이터 수집]
    Step2 --> Step3[Step 3: Persona Writer<br/>03_persona_draft.md<br/>페르소나 적용]
    Step3 --> Step4[Step 4: Veteran Editor<br/>04_final_article.md<br/>편집 & 포장]
    Step4 --> Step5[Step 5: Threads Generator<br/>05_threads_series.md<br/>SNS 쓰레드 생성]
    Step5 --> Step6[Step 6: Critic<br/>06_critic_report.md<br/>비평 & 검증]
    Step6 --> Decision{개선 필요?}
    Decision -->|Yes| Step7[Step 7: Refiner<br/>v2, v3 생성]
    Step7 --> Step4
    Decision -->|No| End([완료: 발행 준비])
    Step6 --> Archive[History Archive<br/>07_history_archive.md<br/>전체 작업 로그]
    
    style Step0 fill:#e1f5ff,stroke:#01579b,stroke-width:2px,color:#000
    style Step1 fill:#ffe1cc,stroke:#e65100,stroke-width:2px,color:#000
    style Step2 fill:#d4f4dd,stroke:#1b5e20,stroke-width:2px,color:#000
    style Step3 fill:#f0d4ff,stroke:#4a148c,stroke-width:2px,color:#000
    style Step4 fill:#ffd4e5,stroke:#880e4f,stroke-width:2px,color:#000
    style Step5 fill:#fff4cc,stroke:#f57f17,stroke-width:2px,color:#000
    style Step6 fill:#ffd4d4,stroke:#b71c1c,stroke-width:2px,color:#000
    style Step7 fill:#d4f4f4,stroke:#006064,stroke-width:2px,color:#000
    style Archive fill:#eeeeee,stroke:#424242,stroke-width:2px,color:#000
    style Decision fill:#ffffff,stroke:#333333,stroke-width:2px,color:#000
```

## 2. 폴더 구조

```mermaid
graph TD
    Root[📁 output/] --> Project[📁 20260126_AI_Agent_Organization/]
    
    Project --> V1[📁 v1/<br/>첫 번째 시도]
    Project --> V2[📁 v2/<br/>Draft-First + 피드백 반복]
    
    V1 --> V1_00[📄 00_draft.md]
    V1 --> V1_01[📄 01_logic_filter.md]
    V1 --> V1_02[📄 02_research_nuggets.md]
    V1 --> V1_03[📄 03_persona_draft.md]
    V1 --> V1_04[📄 04_final_article.md]
    V1 --> V1_04v2[📄 04_final_article_v2.md]
    V1 --> V1_05[📄 05_threads_series.md]
    V1 --> V1_05v2[📄 05_threads_series_v2.md]
    V1 --> V1_06[📄 06_critic_report.md]
    V1 --> V1_07[📄 07_history_archive.md]
    
    V2 --> V2_00[📄 00_draft.md<br/>⭐ + 집필 가이드]
    V2 --> V2_01[📄 01_logic_filter.md]
    V2 --> V2_02[📄 02_research_nuggets.md]
    V2 --> V2_03[📄 03_persona_draft.md]
    V2 --> V2_04[📄 04_final_article.md]
    V2 --> V2_04v2[📄 04_final_article_v2.md]
    V2 --> V2_04v3[📄 04_final_article_v3.md<br/>🎯 링크드인용]
    V2 --> V2_05[📄 05_threads_series.md]
    V2 --> V2_05v2[📄 05_threads_series_v2.md]
    V2 --> V2_06[📄 06_critic_report.md]
    V2 --> V2_07[📄 07_history_archive.md]
    
    style V2_00 fill:#fff4cc,stroke:#f57f17,stroke-width:2px,color:#000
    style V2_04v3 fill:#d4f4dd,stroke:#1b5e20,stroke-width:2px,color:#000
```

## 3. 사용자 피드백 반복 프로세스

```mermaid
flowchart LR
    Draft[초안 작성<br/>Step 3: Persona] --> Feedback[사용자 피드백<br/>n차 반복]
    Feedback --> Improve[개선 & 검증<br/>Critic + Refiner]
    Improve --> Decision{만족?}
    Decision -->|No| Draft
    Decision -->|Yes| Final[최종 버전<br/>v2, v3]
    
    style Draft fill:#e1f5ff,stroke:#01579b,stroke-width:2px,color:#000
    style Feedback fill:#ffe1cc,stroke:#e65100,stroke-width:2px,color:#000
    style Improve fill:#d4f4dd,stroke:#1b5e20,stroke-width:2px,color:#000
    style Final fill:#d4f4f4,stroke:#006064,stroke-width:2px,color:#000
    style Decision fill:#ffffff,stroke:#333333,stroke-width:2px,color:#000
```

## 4. 스킬 구조

```mermaid
graph TD
    Skill[📁 .agent/skills/advanced-writing/]
    Skill --> Main[📄 SKILL.md<br/>메인 워크플로우 정의]
    Skill --> Prompts[📁 prompts/<br/>단계별 프롬프트]
    Skill --> Tools[📁 prompts/tools/<br/>보조 도구]
    
    Prompts --> P0[step0_draft.md]
    Prompts --> P1[step1_logic_filter.md]
    Prompts --> P2[step2_research.md]
    Prompts --> P3[step3_persona.md<br/>⭐ Show, Don't Tell 규칙]
    Prompts --> P4[step4_editor.md]
    Prompts --> P5[step5_threads.md]
    Prompts --> P6[step6_critic.md]
    Prompts --> P7[step7_refiner.md]
    
    Tools --> T1[history_keeper.md<br/>작업 히스토리 기록]
    
    style P3 fill:#fff4cc,stroke:#f57f17,stroke-width:2px,color:#000
    style T1 fill:#eeeeee,stroke:#424242,stroke-width:2px,color:#000
```

## 5. 핵심 원칙

### 워크플로우 설계 원칙

1. **단계별 분리**: 각 단계는 독립적인 파일로 저장
2. **반복 가능**: Critic → Refiner → Editor 피드백 루프
3. **기록 보존**: History Archive로 전체 진화 과정 추적
4. **버전 관리**: v1, v2, v3로 점진적 개선

### 파일 명명 규칙

- `00_draft.md`: 원본
- `01~07_*.md`: 단계별 산출물
- `*_v2.md`, `*_v3.md`: 개선 버전
- `07_history_archive.md`: 전체 로그

### 폴더 분리 기준

- `v1/`: 첫 번째 접근 방식 (실험)
- `v2/`: 개선된 접근 방식 (사용자 피드백 반영)
- 각 폴더는 독립적인 완전한 워크플로우 포함
