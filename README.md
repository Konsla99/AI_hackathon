# 실무 과제 실행 키트

이 README는 준비·사용 안내다. 실전 AGENTS나 작업 프롬프트에 통째로 복사하지 않는다. 실전에서 읽을 지침은 [AGENTS.md](AGENTS.md)와 연결된 guides다.

## 시작하기

1. 기존 프로젝트 구조·제출 문서를 먼저 확인한 뒤 필요한 템플릿만 실제 경로에 채운다.


## 작업 흐름

| 순서 | 작업 | 결과 |
|---|---|---|
| 1 | 요구사항 파악 | 요구 ID와 관찰 가능한 완료 조건 |
| 2 | 엣지케이스·예외처리 | 데이터 검사 결과, 경계 사례, 처리 정책 |
| 3 | 설계·분담 | 모듈/OOP 책임, 알고리즘, UI, 계약, 파일 소유권 |
| 4 | 검증 준비 | 사용자 테스트 시트와 AI 검토표 초안 |
| 5 | 병렬 구현·통합 | 기능 코드, 핵심 주석, 기능 폴더 README |
| 6 | 사용자·AI 동시 검증 | UI 실제 결과, 코드 검토·결함 목록 |
| 7 | 수정·재확인 | 결함별 수정 및 관련 검사 결과 |
| 8 | 선택 개선·최종 제출 | 필수 완료 후 UX/추가 기능, 최종 재현법 |

진행 기준과 각 단계의 입력·출력은 [workflow.md](workflow.md)에 있다. MVP는 작은 핵심 흐름을 먼저 실행하는 중간 단계이며, 남은 필수조건은 계속 완료한다.

## 키트 구성

| 문서 | 사용 시점 |
|---|---|
| [요구사항·엣지케이스](guides/requirements-and-edge-cases.md) | 원문 분석, 데이터 전수검사, 예외 정책 결정 |
| [설계·병렬 작업](guides/design-and-parallel-work.md) | 모듈·클래스·계약과 작업 하달, 통합 |
| [프로젝트 구조](guides/project-structure.md) | 코드·문서·설정의 배치와 세분화 |
| [문서화·주석](guides/documentation.md) | 기능 README, 핵심 주석, 설명/구현 일치 |
| [검증](guides/verification.md) | 사용자 UI 확인과 AI 검토의 동시 진행 |

템플릿은 [요구사항](templates/requirements.md), [엣지케이스](templates/edge-cases.md), [설계·하달](templates/design.md), [사용자 테스트](templates/user-test-sheet.md), [AI 검토](templates/ai-review.md), [기능 README](templates/feature-README.md), [인계](templates/handoff.md)를 제공한다. 기존 제출 양식이 있으면 내용을 그 양식에 통합한다.

## 실제 작업공간 배치 예시

```text
실제 작업공간/
├─ src/
│  ├─ features/
│  │  └─ <기능>/
│  │     ├─ 구현 파일들
│  │     └─ README.md
│  └─ shared/
├─ docs/
│  ├─ analysis/
│  │  ├─ requirements.md
│  │  ├─ edge-cases.md
│  │  └─ design.md
│  └─ verification/
│     ├─ user-test-sheet.md
│     └─ ai-review.md
├─ README.md
└─ 프로젝트 설정 파일들
```

예시를 고정 규칙으로 강제하지 않는다. 기존 프레임워크의 진입점·라우팅·모듈 구조를 유지하고, API/UI/도메인 계층이나 하위 기능은 필요할 때 세분화한다. 자세한 기준은 프로젝트 구조 guide를 따른다.

## 시작 지시

```text
작업 루트는 <실제 경로>, 키트 경로는 <실제 키트/retest 경로>다.
키트의 AGENTS.md와 workflow.md를 읽고 실제 과제 README·요구사항·제출 지침을 기준으로 작업해라.
종료 시각은 <시각>, 남은 시간은 <분>이다.

요구사항 → 데이터/엣지케이스와 예외 정책 → 설계/모듈 계약/분담
→ 사용자 테스트 시트와 AI 검토표 초안 → 구현/통합 → 동시 검증 → 수정/재확인 순서로 진행해라.
독립 기능은 지원되는 서브에이전트/멀티에이전트에 파일 소유권과 계약을 정해 하달해라.
기능별 코드와 README를 함께 작성하고, 핵심 로직의 이유와 제약은 주석으로 설명해라.
기존 구조·제출 양식을 우선하고, 코드나 문서를 루트에 일괄 생성하지 마라.

짧은 수동 워크플로우를 선택한다. 전체 Superpowers/Matt Pocock 절차를 자동 적용하지 말고,
반복 설계 승인·중복 계획·매 작업 다중 리뷰·무관한 전체 검사·새 대형 테스트 환경 구축은 생략해라.
기존 빠른 빌드/타입 검사와 핵심 동작 확인은 유지해라.
사용자 UI 테스트 중에는 코드 버전을 고정하고 AI는 읽기 중심으로 검토해라.
검증 완료를 꾸며 쓰지 말고 사용자 확인 대기·코드 검토만·실행 확인을 구분해라.
필수 완료와 결함 수정을 우선하고, 추가 기능은 시간·범위 여유를 확인해 제안해라.
```

## 준비.

추가 스킬을 준비할 때는 [Superpowers 원문](https://github.com/openai/plugins/tree/main/plugins/superpowers), [Matt Pocock 원문](https://github.com/mattpocock/skills)을 확인한다. 외부 연동·설치·업데이트가 필요한 도구는 최신 시험 규칙과 실제 환경에서 확인한다.
