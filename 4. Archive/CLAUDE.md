# 4. Archive — 운영 가이드

## 목적

**완료되거나 비활성화된 항목**을 보존하는 공간입니다.  
삭제하지 않고 보관함으로써 링크 무결성을 유지하고, 나중에 참조할 수 있게 합니다.

> **원칙**: 지우지 말고, 보관하라. 과거의 작업은 미래의 맥락이 된다.

## 어떤 노트가 들어가는가

| 출처 | 이동 시점 |
|------|----------|
| `1. Projects/` | 프로젝트 완료 또는 중단 시 |
| `2. Areas/` | 더 이상 책임지지 않는 영역 |
| `3. Resources/` | 더 이상 관련 없거나 오래된 자료 |
| 임시 실험 노트 | 더 이상 발전시키지 않을 초안 |

## 폴더 구조

```
4. Archive/
├── Projects/
│   └── 2025-웹사이트리뉴얼/   ← 완료된 프로젝트 그대로 이동
├── Areas/
│   └── 2024-부업/
└── Resources/
    └── 구버전-도구목록.md
```

원래 폴더 구조를 유지하여 이동합니다.

## 노트 Frontmatter (이동 시 업데이트)

```yaml
---
type: project              # 원래 type 유지
status: archived           # ← 반드시 archived로 변경
created: YYYY-MM-DD        # 원래 생성일 유지
updated: YYYY-MM-DD        # 보관 처리일로 업데이트
archived_at: YYYY-MM-DD    # 보관일 추가
tags: [archived]           # archived 태그 추가
---
```

## 작업 규칙

1. **구조 보존** — 원래 폴더 구조 그대로 Archive 하위로 이동
2. **링크 수정 금지** — 기존 `[[링크]]`를 수정하지 않음 (Obsidian이 자동 처리)
3. **status → archived** — Frontmatter의 status를 `archived`로 변경
4. **삭제 금지** — Archive에서도 삭제는 신중하게, 주기적 검토 후 결정
5. **ZK는 보관 안 함** — `5. Zettelkasten/`의 Permanent Note는 영구 보존, Archive 대상 아님

## 보관 체크리스트

```
[ ] status를 archived로 변경
[ ] archived_at 날짜 추가
[ ] 허브 노트에 완료 요약 작성
[ ] 핵심 학습을 ZK Permanent Note로 정제
[ ] 4. Archive/ 하위 적절한 위치로 이동
```

## Dataview 쿼리 예시

```dataview
TABLE type, archived_at
FROM "4. Archive"
WHERE status = "archived"
SORT archived_at DESC
LIMIT 20
```
