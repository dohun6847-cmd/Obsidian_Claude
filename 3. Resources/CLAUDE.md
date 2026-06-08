# 3. Resources — 운영 가이드

## 목적

특정 **주제나 관심사**에 대한 참고 자료를 모아두는 공간입니다.  
프로젝트나 영역에 속하지 않지만, 언젠가 유용할 정보들의 저장소입니다.

> **PARA 정의**: Resource = 미래에 유용할 수 있는 주제별 참고 자료

## 어떤 노트가 들어가는가

| 종류 | 예시 |
|------|------|
| 주제별 컬렉션 | 프로그래밍 언어 레퍼런스, 디자인 패턴 |
| 북마크/링크 모음 | 유용한 도구 목록, 읽을거리 |
| 체크리스트 | 여행 준비물, 발표 체크리스트 |
| How-to 가이드 | 자주 쓰는 CLI 명령어, 설정 방법 |
| 영감 자료 | 글쓰기 참고, 디자인 레퍼런스 |

### 포함 기준
- 특정 프로젝트/영역에 귀속되지 않는 범용 자료인가?
- 주제(topic)로 분류할 수 있는가?

### 제외 기준
- 나의 통찰과 해석이 담긴 경우 → `5. Zettelkasten/20. Permanent/`로
- 원천 자료에서 추출한 노트 → `5. Zettelkasten/10. Literature/`로
- 특정 프로젝트 전용 자료 → `1. Projects/해당프로젝트/`로

## 폴더 구조

```
3. Resources/
├── 프로그래밍/
│   ├── Python-레퍼런스.md
│   └── Git-치트시트.md
├── 생산성/
│   └── 시간관리-도구목록.md
└── 디자인/
    └── 색상-팔레트.md
```

## 노트 Frontmatter

```yaml
---
type: resource
status: active             # active | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [resource, 주제태그]
---
```

## 작업 규칙

1. **주제별 폴더로 분류** — 시간 기준이 아닌 주제 기준으로 구성
2. **링크 > 복사** — 외부 자료는 링크로 참조, 내용 복사 지양
3. **ZK와 구별** — 자료 수집은 Resources, 나만의 해석은 ZK Permanent
4. **정기 정리** — 분기 1회 오래된 자료 Archive 또는 삭제 검토

## Dataview 쿼리 예시

```dataview
TABLE tags, updated
FROM "3. Resources"
WHERE type = "resource"
SORT updated DESC
```
