# 1. Projects — 운영 가이드

## 목적

마감일이 있는, 명확한 완료 시점이 존재하는 프로젝트를 관리합니다.  
"언제 끝나는가?"라는 질문에 답할 수 있어야 이 폴더에 속합니다.

> **PARA 정의**: Project = 명확한 목표 + 마감일이 있는 일련의 작업

## 어떤 노트가 들어가는가

| 노트 종류 | 예시 |
|----------|------|
| 프로젝트 허브 노트 | `00_프로젝트명_Hub.md` |
| 회의록 | `2025-10-15_킥오프-회의.md` |
| 작업 목록 | `Tasks.md` |
| 산출물 초안 | `보고서-초안.md` |

### 포함 기준
- 마감일(due date)이 존재하는가?
- 완료 상태를 판단할 수 있는가?
- 현재 활발히 진행 중인가?

### 제외 기준
- 마감일 없이 지속되는 것 → `2. Areas/`로
- 참고용 자료 → `3. Resources/`로
- 완료된 프로젝트 → `4. Archive/`로

## 폴더 구조

```
1. Projects/
├── 프로젝트A/
│   ├── 00_프로젝트A_Hub.md   ← 허브 노트 (필수)
│   ├── 회의록/
│   └── 산출물/
└── 프로젝트B/
    └── 00_프로젝트B_Hub.md
```

## 허브 노트 필수 Frontmatter

```yaml
---
type: project
status: in-progress        # todo | in-progress | completed | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
due: YYYY-MM-DD            # 마감일 (필수)
tags: [project]
---
```

## 작업 규칙

1. **프로젝트당 하나의 허브 노트** — 모든 관련 노트의 진입점
2. **완료 시 즉시 Archive** — `4. Archive/`로 이동, 링크는 유지
3. **지식은 ZK로 이동** — 프로젝트에서 얻은 통찰은 `5. Zettelkasten/20. Permanent/`에 Permanent Note로 정제
4. **복사 금지** — ZK 노트 내용은 `[[링크]]`로 참조

## Dataview 쿼리 예시

```dataview
TABLE due, status
FROM "1. Projects"
WHERE type = "project" AND status != "archived"
SORT due ASC
```
