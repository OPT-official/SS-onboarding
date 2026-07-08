# 🎯 토요일 첫 미션 / Saturday First Mission

**목표 / Goal:** GitHub 협업 한 사이클을 직접 굴려보기
**Goal:** Run through one full GitHub collaboration cycle hands-on

`clone` → `branch` → `commit` → `push` → `Pull Request` → `review` → `merge`

---

## 🇰🇷 한국어 절차

### 0. 사전 준비

- [ ] GitHub 계정 있음
- [ ] `OPT-official` org 초대 수락함
- [ ] 로컬에 git 설치됨 (`git --version` 확인)
- [ ] VS Code(또는 원하는 에디터) 준비
- [ ] (선택) `gh` CLI 설치 — 있으면 편함

### 1. 이 레포 clone

```bash
git clone https://github.com/OPT-official/SS-onboarding.git
cd SS-onboarding
```

### 2. 본인 브랜치 만들기

```bash
git checkout -b intro/본인이름
# 예: git checkout -b intro/byeol
```

### 3. 자기소개 파일 만들기

`members_intro/TEMPLATE.md` 를 복사해서 `members_intro/본인이름.md` 로 저장하고 내용 채우기.

```bash
cp members_intro/TEMPLATE.md members_intro/byeol.md
# 그리고 에디터로 열어서 편집
```

### 4. commit & push

```bash
git add members_intro/본인이름.md
git commit -m "자기소개: 본인이름"
git push -u origin intro/본인이름
```

### 5. Pull Request 열기

- 터미널에 뜨는 링크를 열거나
- GitHub 웹에서 `Compare & pull request` 버튼 클릭
- PR 템플릿 채우기 (이슈 있으면 `closes #N`)

### 6. 리뷰 & merge

- 트랙리드가 코멘트 남기면 반영
- Approve 받으면 `Squash and merge`
- 브랜치는 merge 후 삭제 (버튼으로)

### 7. 로컬 정리

```bash
git checkout main
git pull
git branch -d intro/본인이름
```

---

## 🇬🇧 English

### 0. Prerequisites

- [ ] GitHub account
- [ ] Accepted invitation to `OPT-official` org
- [ ] Git installed locally (`git --version`)
- [ ] VS Code (or your editor of choice) ready
- [ ] (Optional) `gh` CLI installed — makes life easier

### 1. Clone this repo

```bash
git clone https://github.com/OPT-official/SS-onboarding.git
cd SS-onboarding
```

### 2. Create your branch

```bash
git checkout -b intro/yourname
```

### 3. Write your intro file

Copy `members_intro/TEMPLATE.md` to `members_intro/yourname.md` and fill it in.

```bash
cp members_intro/TEMPLATE.md members_intro/yourname.md
```

### 4. Commit & push

```bash
git add members_intro/yourname.md
git commit -m "intro: yourname"
git push -u origin intro/yourname
```

### 5. Open a Pull Request

- Click the link that appears in the terminal, or
- Go to GitHub → `Compare & pull request`
- Fill in the PR template

### 6. Review & merge

- Address review comments from the track lead
- Once approved, `Squash and merge`
- Delete the branch after merging

### 7. Clean up locally

```bash
git checkout main
git pull
git branch -d intro/yourname
```

---

## 🆘 막히면 / If stuck

- Discord `#dev-track` 채널에 물어보기
- 이슈로 `bug-or-question` 템플릿 사용
- 옆사람한테 물어보기 (같이 있잖아)
