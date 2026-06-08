# 20. Permanent — 운영 가이드

## 목적

**나만의 영구 지식 단위**를 보관합니다. Literature Note나 Inbox 메모에서 발전시킨, 내 언어로 쓴 나의 통찰입니다.  
이 노트들이 ZK의 핵심이자 지식 발전소의 최종 산출물입니다.

> **테스트**: "이 노트는 특정 프로젝트가 끝나도 여전히 가치 있는가?"  
> Yes → Permanent Note가 맞습니다.

## Permanent Note의 특징

| 특징 | 설명 |
|------|------|
| 원자성 | 하나의 노트 = 하나의 아이디어/주장 |
| 고유성 | 완전히 내 언어로 작성 (복붙 금지) |
| 연결성 | 최소 2개 기존 노트와 `[[링크]]` 연결 |
| 시간 독립성 | 언제 읽어도 의미가 통함 |
| 제목의 명확성 | 제목만 봐도 주장이 이해됨 |

## 파일 이름 규칙

제목은 **명사구** 또는 **주장 문장** 형태:

```
좋은 예: 연결이 많을수록 아이디어는 강해진다.md
좋은 예: 스트레스와 성장의 역설.md
나쁜 예: 메모1.md
나쁜 예: 생각들.md
```

## 필수 Frontmatter

```yaml
---
type: permanent
status: active
created: YYYY-MM-DD
updated: YYYY-MM-DD
source: "[[10. Literature/LIT_원천자료]]"   # 영감을 준 Literature Note
related:                                     # 연결된 Permanent Notes (최소 2개)
  - "[[연결노트1]]"
  - "[[연결노트2]]"
tags: [permanent, 주제태그]
---
```

## 노트 구조 권장

```markdown
(첫 문단: 이 노트의 핵심 주장을 1-3문장으로)

## 본론
(아이디어 전개, 논거, 예시)

## 연결
- [[관련노트1]] — 이 노트와 어떻게 연결되는지
- [[관련노트2]] — 어떤 맥락에서 연결되는지

## 출처
- [[LIT_원천자료]] 
```

## 작업 규칙

1. **최소 2개 연결** — 새 노트 생성 시 기존 노트와 반드시 연결
2. **고아 방지** — 링크 없는 노트는 존재 이유가 없음
3. **완전한 문장으로** — "메모" 수준이 아닌 "글" 수준으로 작성
4. **발전 허용** — 시간이 지나면서 내용 보완 가능, `updated` 갱신
5. **분할 허용** — 한 노트가 너무 커지면 두 개의 원자적 노트로 분리

## 고아 노트 탐지

```dataview
TABLE length(file.inlinks) as "들어오는 링크", length(file.outlinks) as "나가는 링크"
FROM "5. Zettelkasten/20. Permanent"
WHERE type = "permanent"
WHERE length(file.inlinks) = 0 OR length(file.outlinks) < 2
SORT file.ctime ASC
```
