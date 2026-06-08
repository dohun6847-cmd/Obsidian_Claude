# 2. Areas — 운영 가이드

## 목적

마감일 없이 **지속적으로 유지해야 하는 책임 영역**을 관리합니다.  
"언제 끝나는가?"가 아니라, "어떤 기준을 유지하는가?"로 정의됩니다.

> **PARA 정의**: Area = 시간이 지나도 유지되어야 하는 기준과 책임

## 어떤 노트가 들어가는가

| 영역 예시 | 설명 |
|----------|------|
| 건강 | 운동 루틴, 식단 원칙, 의료 기록 |
| 재무 | 예산 원칙, 투자 전략, 자산 현황 |
| 직무 역량 | 학습 계획, 기술 스택, 성과 기록 |
| 관계 | 중요한 사람들, 커뮤니케이션 원칙 |
| 창작 | 글쓰기, 사이드 프로젝트 기준 |

### 포함 기준
- 끝나지 않고 지속적으로 관리되어야 하는가?
- 달성 목표가 아닌, 유지할 **기준(standard)**이 있는가?

### 제외 기준
- 마감일이 있다 → `1. Projects/`로
- 단순 참고 자료 → `3. Resources/`로

## 폴더 구조

```
2. Areas/
├── 건강/
│   ├── 00_건강_Hub.md
│   └── 운동-루틴.md
├── 재무/
│   └── 00_재무_Hub.md
└── 직무역량/
    └── 00_직무역량_Hub.md
```

## 허브 노트 필수 Frontmatter

```yaml
---
type: area
status: active             # active | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [area]
---
```

## 작업 규칙

1. **기준 문서화** — 이 영역에서 "잘 하고 있다"는 기준을 명시적으로 기록
2. **정기 리뷰** — 월 1회 허브 노트 검토, `updated` 날짜 갱신
3. **프로젝트와 연결** — 영역에서 파생된 구체적 작업은 `1. Projects/`에 프로젝트로 생성
4. **지식은 ZK로** — 깨달음과 통찰은 `5. Zettelkasten/20. Permanent/`에 정제

## Dataview 쿼리 예시

```dataview
TABLE updated, status
FROM "2. Areas"
WHERE type = "area" AND status = "active"
SORT updated ASC
```
