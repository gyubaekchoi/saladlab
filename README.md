# 알파리뷰 무료 버전 — 화면 설계 패키지

알파리뷰(B2B SaaS)의 **무료 버전 도입 및 유료 전환 넛지** 화면 설계 패키지입니다.

## Live Preview
GitHub Pages 활성화 후 접근 가능합니다.

```
https://<organization>.github.io/<repository-name>/
```

## 구성

| 파일 | 설명 |
|---|---|
| [`index.html`](./index.html) | 흑백 와이어프레임 (4개 화면 탭 전환) |
| [`docs/screen-spec.md`](./docs/screen-spec.md) | 화면별 상세 설계서 (레이아웃·컴포넌트·상태) |
| [`docs/prd.md`](./docs/prd.md) | Phase 1.5 PRD |

## 와이어프레임 화면 목록

1. **온보딩** — 카드 미등록 상태에서도 설치 완료가 가능한 4-step 플로우
2. **리뷰 목록** — 할당량 인디케이터 + 핵심 2지표 현황
3. **LNB + 띠배너** — 자물쇠 노출 최소화 원칙의 메뉴 구조
4. **넛지 모달 3종** — 기능 설명 / 사용량 제한 / 무료 체험 제안

## 설계 원칙

1. 복잡함을 덜어내고 본질에 집중한다 — 한 화면의 유료화 메시지는 1순위 1개만 강조
2. 망설일 순간을 주지 않는다 — 결정 지점에서 다음 행동을 기본값으로 제시
3. 헷갈리게 하지 않는다 — 유료 전환 유도 패턴은 3가지 이하로 통일

## 로컬 미리보기

```bash
# 저장소 루트에서
python3 -m http.server 8000
# 또는
npx serve
```

브라우저에서 `http://localhost:8000` 접속.

## GitHub Pages 활성화 방법

1. 저장소 → **Settings** → **Pages**
2. Source: `Deploy from a branch`
3. Branch: `main` (또는 배포할 브랜치) / `/ (root)` 또는 `/docs` 선택
4. Save 후 1~2분 내 URL 발급

---

**담당** 규백 (Product Design)
**최종 수정** 2026-04-21
