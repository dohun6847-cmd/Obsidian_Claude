# 10. Literature — 운영 가이드

## 목적

**원천 자료(책, 글, 영상, 강의 등)에서 추출한 노트**를 보관합니다.  
저자의 아이디어를 내 말로 요약하되, 아직 나의 해석이나 비판은 최소화합니다.

> **구별 기준**: "이것은 저자가 말한 것인가, 내가 생각한 것인가?"  
> 저자의 생각 → Literature / 나의 생각 → Permanent

## 어떤 노트가 들어가는가

| 원천 유형 | 예시 |
|----------|------|
| 책 | `LIT_인간의품격_데이비드브룩스.md` |
| 아티클/블로그 | `LIT_제텔카스텐방법론_산스.md` |
| 강의/영상 | `LIT_딥러닝강의_앤드류응.md` |
| 팟캐스트 | `LIT_Huberman-수면과회복.md` |
| 논문 | `LIT_AttentionIsAllYouNeed.md` |

## 파일 이름 규칙

```
LIT_제목_저자.md
```

## 필수 Frontmatter

```yaml
---
type: literature
status: active
created: YYYY-MM-DD
updated: YYYY-MM-DD
source: "책 제목 / URL / 강의명"
author: "저자명"
tags: [literature, 주제태그]
---
```

## 노트 구조 권장

```markdown
## 핵심 주장
(이 자료의 중심 논지 1-2문장)

## 주요 내용
(챕터별 또는 주제별 요약)

## 인상적인 구절
> "인용문" (p.xx)

## 나의 반응 (선택)
(짧은 메모 — 발전시킬 생각은 Permanent Note로)

## 연결된 Permanent Notes
- [[노트 제목]]
```

## 작업 규칙

1. **출처당 하나의 노트** — 같은 책에 대한 노트는 하나로 통합
2. **저자의 언어 존중** — 내 해석보다 원문에 충실하게
3. **Permanent으로 발전** — 흥미로운 개념은 `20. Permanent/`에 별도 노트로 정제
4. **링크 추가** — 작성 후 관련 Permanent Note와 연결

## Dataview 쿼리 예시

```dataview
TABLE author, source, created
FROM "5. Zettelkasten/10. Literature"
WHERE type = "literature"
SORT created DESC
```
