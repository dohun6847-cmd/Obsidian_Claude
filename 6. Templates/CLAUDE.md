# 6. Templates — 운영 가이드

## 목적

**일관된 노트 구조**를 보장하는 템플릿 파일을 보관합니다.  
모든 노트 타입에는 대응하는 템플릿이 존재합니다.

> **규칙**: 이 폴더에는 템플릿만 있습니다. 실제 노트는 절대 여기에 작성하지 않습니다.

## 템플릿 목록

| 파일명 | 용도 | 생성 위치 |
|--------|------|----------|
| `TPL_Project.md` | 프로젝트 허브 노트 | `1. Projects/` |
| `TPL_Area.md` | 영역 허브 노트 | `2. Areas/` |
| `TPL_Resource.md` | 참고 자료 노트 | `3. Resources/` |
| `TPL_Literature.md` | 문헌 노트 | `5. Zettelkasten/10. Literature/` |
| `TPL_Permanent.md` | 영구 노트 | `5. Zettelkasten/20. Permanent/` |
| `TPL_Daily.md` | 일일 노트 | (Daily Notes 플러그인) |

## Templater 사용법

Templater 플러그인이 활성화되어 있습니다. 동적 값을 사용합니다:

```
<% tp.date.now("YYYY-MM-DD") %>     → 오늘 날짜
<% tp.file.title %>                  → 현재 파일 이름
<% tp.system.prompt("제목:") %>      → 사용자 입력 받기
```

## 템플릿 호출 방법

1. 새 노트 생성
2. 명령어 팔레트 (`Ctrl+P`) → "Templater: Open Insert Template Modal"
3. 적절한 템플릿 선택

## 작업 규칙

1. **템플릿만 보관** — 실제 내용 노트 금지
2. **버전 유지** — 템플릿 변경 시 파일 상단에 변경 내역 주석 추가
3. **Frontmatter 포함** — 모든 템플릿은 완전한 Frontmatter를 포함
4. **Dataview 호환** — 모든 Frontmatter 필드는 Dataview 쿼리와 호환되게 설계
