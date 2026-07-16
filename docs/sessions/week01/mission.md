# 🎯 토요일 첫 미션 — 자기소개 PR 올리기

**목표:** GitHub 협업 한 사이클을 직접 돌려본다.
`clone → branch → commit → push → PR → review → merge`

---

## ⏱️ 당일 아젠다 (트랙리드 진행 기준, 약 90분)

| 시간 | 내용 |
|------|------|
| 00:00–00:10 | 레포 구조 소개, 오늘 목표 공유 (트랙리드) |
| 00:10–00:20 | 사전 준비 체크 (git 설치, org 초대 수락 확인) |
| 00:20–01:00 | **실습:** 아래 절차 각자 진행 (트랙리드는 돌아다니며 도움) |
| 01:00–01:20 | PR 리뷰 라이브 시연 → 전원 merge |
| 01:20–01:30 | 다음 주 과제 안내 (Issue 같이 보기), Q&A |

---

## ✅ 사전 준비 (모임 전에 각자)

- [ ] GitHub 계정 + `OPT-official` org 초대 수락
- [ ] git 설치 확인: 터미널에 `git --version`
- [ ] VS Code(또는 선호 에디터) 설치

---

## 📝 실습 절차

### 1. clone — 레포 내려받기

```bash
git clone https://github.com/OPT-official/SS-onboarding.git
cd SS-onboarding
```

### 2. branch — 내 작업 공간 만들기

```bash
git checkout -b intro/본인이름   # 예: intro/jina
```

> 💡 **왜 브랜치?** main을 직접 건드리지 않고 안전하게 작업하기 위해서.
> 이 레포의 main은 protected라 애초에 직접 push가 막혀 있음.

### 3. 자기소개 파일 작성

```bash
cp members_intro/TEMPLATE.md members_intro/본인이름.md
```

에디터로 열어서 내용 채우기. (파일명은 영문 소문자: `jina.md`)

### 4. commit & push — 저장하고 올리기

```bash
git add members_intro/본인이름.md
git commit -m "자기소개: 본인이름"
git push -u origin intro/본인이름
```

### 5. PR 열기

push 후 터미널에 뜨는 링크 클릭, 또는 GitHub 웹에서
`Compare & pull request` → 템플릿 채우고 `Create pull request`

### 6. review & merge

- 트랙리드가 코멘트 → 수정 필요하면 로컬에서 고치고 다시 `add → commit → push` (PR에 자동 반영됨)
- Approve 후 **Squash and merge** → 브랜치 삭제 버튼 클릭

### 7. 로컬 정리

```bash
git checkout main
git pull
git branch -d intro/본인이름
```

### 8. 원격 브랜치 삭제

```bash
git push origin --delete intro/본인이름
```

**🎉 끝! 방금 한 이 사이클이 앞으로 매주 반복할 흐름입니다.**

---

## 🆘 자주 막히는 곳

| 증상 | 해결 |
|------|------|
| `Permission denied (403)` | org 초대 수락했는지 확인. 로컬 git 계정이 본인 계정인지 확인 (`git config user.name`) |
| push했는데 PR 버튼 안 보임 | 레포 페이지 새로고침, 또는 `Pull requests` 탭 → `New pull request` |
| 다른 사람 파일을 건드림 | `git checkout main -- 파일경로` 로 되돌리기 |
| 커밋 메시지 오타 | (push 전이면) `git commit --amend -m "새 메시지"` |

그래도 안 되면: Discord `#dev-track` 또는 옆사람 찬스.

---

## 🇬🇧 English (TL;DR)

Clone → `git checkout -b intro/yourname` → copy `members_intro/TEMPLATE.md`
to `members_intro/yourname.md` and fill it in → add/commit/push → open PR →
address review → squash-merge → delete branch → `git checkout main && git pull`.
This exact cycle repeats every week.
