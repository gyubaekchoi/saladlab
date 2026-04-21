# GitHub 배포 가이드

준비는 완료되었습니다. 아래 명령어를 순서대로 실행하시면 됩니다.

## 현재 상태

- ✅ `index.html` + `.nojekyll` + `README.md` + `docs/` 구조 완성
- ✅ git 저장소 초기화 완료 (main 브랜치, 초기 커밋 1개)
- ⏸️ 원격 저장소 연결 및 push 필요 (아래 단계)

## 선택지 A — 새 저장소로 올리기 (빠름)

### 1. GitHub에서 새 저장소 생성
- [ ] https://github.com/new 접속
- [ ] Owner: `saladlab` (또는 본인 계정)
- [ ] Repository name: `alphareview-free-tier-wireframe` (예시)
- [ ] **Public** 선택 (Pages 무료 사용을 위해)
- [ ] README, .gitignore 추가 **안 함** (이미 있음)
- [ ] Create 클릭

### 2. 로컬에서 push
터미널을 열고 아래 명령어 실행 (경로는 그대로 복사 가능):

```bash
cd ~/Documents/freeplan/github-deploy
# 또는 Cowork 작업 폴더의 github-deploy 위치

git remote add origin https://github.com/<ORG>/<REPO-NAME>.git
git push -u origin main
```

`<ORG>`, `<REPO-NAME>` 부분만 본인이 만든 값으로 바꾸세요.

### 3. GitHub Pages 활성화
- [ ] 저장소 → **Settings** → **Pages**
- [ ] Source: **Deploy from a branch**
- [ ] Branch: **main** / **`/ (root)`**
- [ ] **Save**
- [ ] 1~2분 후 상단에 `https://<ORG>.github.io/<REPO-NAME>/` URL 표시

---

## 선택지 B — 기존 저장소의 하위 폴더로 올리기

### 1. 기존 저장소 clone
```bash
git clone https://github.com/<ORG>/<EXISTING-REPO>.git
cd <EXISTING-REPO>
```

### 2. 현재 배포 패키지를 적절한 위치에 복사
```bash
# 예: wireframes/free-tier 하위 폴더에 두고 싶다면
mkdir -p wireframes/free-tier
cp -r ~/Documents/freeplan/github-deploy/* wireframes/free-tier/
cp ~/Documents/freeplan/github-deploy/.nojekyll wireframes/free-tier/
```

### 3. 커밋 + push
```bash
git add wireframes/free-tier
git commit -m "feat: 알파리뷰 무료 버전 와이어프레임 추가"
git push
```

### 4. Pages가 이미 활성화된 저장소라면
- 기존 Pages URL 뒤에 `/wireframes/free-tier/` 붙이면 바로 접근 가능
- 예: `https://<ORG>.github.io/<EXISTING-REPO>/wireframes/free-tier/`

---

## 공유 링크 예시

배포 완료 후 팀에 공유하실 때:

```
알파리뷰 무료 버전 와이어프레임 v0.1
→ https://<ORG>.github.io/<REPO>/

상단 시스템 탭으로 화면별로 볼 수 있습니다.
01. 온보딩
02. 리뷰 목록
03. LNB + 띠배너
04. 넛지 모달 3종
```

---

## 제가 직접 못 하는 이유

현재 작업 환경에 GitHub 인증(gh CLI 또는 credential helper)이 연결되어 있지 않아 원격 저장소로 push할 수 없습니다. Cowork의 GitHub 커넥터 연동 또는 터미널에서 직접 실행이 필요합니다.

커넥터 연동을 원하시면 말씀해 주세요. 검색해서 안내해 드리겠습니다.
