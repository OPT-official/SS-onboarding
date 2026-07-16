# 🚀 2주차 미션 — 컨벤션 · 이슈 · 머지

**목표:** 지난주 사이클을 여러 명이 동시에 돌려도 안 꼬이게 만든다.
`컨벤션 → 이슈(#N) → 브랜치/커밋/PR 연결 → conflict 해결 → squash merge`

---

## ⏱️ 당일 아젠다 (트랙리드 진행 기준, 약 90분)

| 시간 | 내용 |
|------|------|
| 00:00–00:05 | 지난주 복습, 오늘 목표 공유 (트랙리드) |
| 00:05–00:25 | **꼭지 1:** 커밋 / 브랜치 컨벤션 |
| 00:25–00:45 | **꼭지 2:** 이슈 관리 (+ 페어별 실습 이슈 생성) |
| 00:45–01:20 | **꼭지 3:** 머지 3종류 + ⚔️ conflict 페어 실습 |
| 01:20–01:30 | 이번 주 과제 안내, Q&A |

---

## 1️⃣ 컨벤션

규칙을 지키면 3개월 뒤에 **검색이 됨.** 커밋 목록만 모아도 주간 보고가 나옴.

### 커밋 — Conventional Commits

`타입: 설명` 형식. Angular 팀 가이드에서 시작해 지금은 사실상 표준임. 타입은 5개만 기억할 것.

| 타입 | 언제 | 예시 |
|------|------|------|
| `feat` | 새 기능 / 새 내용 추가 | `feat: 주간 로그 템플릿 추가` |
| `fix` | 버그 / 오류 수정 | `fix: README 깨진 링크 수정` |
| `docs` | 문서만 변경 | `docs: 온보딩 가이드 오타 수정` |
| `refactor` | 동작은 같고 구조만 개선 | `refactor: 스크립트 함수 분리` |
| `chore` | 잡일 (설정, 폴더 정리) | `chore: .gitignore 추가` |

```
❌ "수정함"  ❌ "asdf"  ❌ "최종_진짜최종"
✅ "fix: 자기소개 파일명 소문자로 수정"
```

> 💡 애매하면 일단 `chore`.

### 브랜치 — `타입/이슈번호-설명`

```
feat/3-week02-practice
fix/7-readme-typo
```

영문 소문자, 띄어쓰기는 `-`. 이슈번호가 왜 들어가는지는 꼭지 2에서 바로 나옴.

> 💡 우리 방식(main + 짧은 작업 브랜치 + PR)을 **GitHub Flow**라고 부름. 지난주에 한 게 사실 이거였음.

---

## 2️⃣ 이슈 관리

### 원리 — #번호는 레포 안의 주소

이슈를 만들면 `#1, #2...` 번호가 자동으로 붙음. 이 번호를 커밋·PR·코멘트 어디에 쓰든 GitHub이 자동으로 링크를 걸고 이슈 타임라인에 기록함.

```
커밋:     feat: 주간 로그 추가 (#3)   → 이슈 #3에 이 커밋이 자동 표시
PR 본문:  Closes #3                  → 이 PR이 merge되면 #3 자동 close ✨
```

### 흐름 — 이슈가 먼저, 작업은 그다음

```
Issue 생성(#3) → feat/3-week02-practice → 커밋 (#3) → PR "Closes #3" → merge → 이슈 자동 close
```

### 이점

- **추적성** — 커밋 → PR → 이슈로 역추적. "왜 이걸 했는지"가 이슈에 남음
- **분업** — Assignee 지정 → 누가 뭐 하는 중인지 이슈 목록에서 한눈에
- **분류** — Label(레포에 이미 정의돼 있음) 붙이면 종류별 필터링

### 🛠️ 미니 실습 — 페어별 이슈 만들기 (5분)

웹 → `Issues` 탭 → `New issue`

- 페어 A (정지나 · 박인찬): `week02 conflict 실습 — 페어 A`
- 페어 B (박세인 · 이우주): `week02 conflict 실습 — 페어 B`
- Assignees에 페어 둘 다, Label 하나 붙일 것
- **각자 이슈 번호 메모.** 아래에서 계속 `#N`으로 씀

---

## 3️⃣ 머지 + ⚔️ conflict 실습

### 3-1. merge 버튼은 3종류였음

지난주에 누른 초록 버튼, 화살표(▾)를 누르면 3개가 나옴. 히스토리 모양이 달라짐.

```
① merge commit — 작업 커밋이 전부 main에 남음 + merge 커밋 추가
main:  A───B───────M
            \     /
             c1─c2─c3        → main 로그: A B c1 c2 c3 M (지저분)

② squash — 작업 커밋을 하나로 뭉쳐서 올림
main:  A───B───S             → main 로그: A B S (깔끔)
            \
             c1─c2─c3

③ rebase — 작업 커밋을 main 뒤에 일렬로 붙임
main:  A───B───c1─c2─c3      → 다루기 까다로움
```

**우리 기본 = ② Squash and merge.** 브랜치에선 자유롭게 커밋하고, main엔 "이슈 하나 = 커밋 하나"로 쌓는 전략임.

### 3-2. ⚔️ conflict 페어 실습

두 사람이 **같은 파일 같은 줄**을 다르게 고치면 git이 "누가 맞는지 정해달라"며 멈춤. 오류가 아니라 정상 동작임. 일부러 내고 푸는 것까지 함.

페어에서 **선공 / 후공**을 정할 것. conflict는 후공에게 남.

> ⚠️ **오늘의 핵심:** 커밋했다고 끝이 아님. **push까지 해야 GitHub에 반영됨.** 지난주 "저는 했는데요?"는 전부 push 누락이었음. ✅ 표시마다 웹에서 눈으로 확인할 것.

**STEP 0 — 둘 다: main 최신화 (⭐습관)**

```bash
git checkout main
git pull
```

**STEP 1 — 둘 다: 브랜치 생성** (`N` = 페어 이슈 번호)

```bash
git checkout -b feat/N-conflict-본인이름   # 예: feat/5-conflict-jina
```

**STEP 2 — 둘 다: 같은 줄을 서로 다르게 수정**

`practice/week02/pair-a.md` (페어 B는 `pair-b.md`) 열어서 **1번째 줄**을 각자 다른 문장으로:

```
오늘의 한마디: (각자 아무 문장이나, 단 서로 다르게)
```

**STEP 3 — 둘 다: 커밋 + push**

```bash
git add practice/week02/pair-a.md
git commit -m "feat: 오늘의 한마디 작성 (#N)"
git push -u origin feat/N-conflict-본인이름
```

> ✅ 웹 → `branches`에 내 브랜치가 보이면 성공. 안 보이면 push가 안 된 것임.

**STEP 4 — 둘 다: PR 열기**

push 후 뜨는 링크 클릭 → 제목 `feat: 오늘의 한마디 — 본인이름 (#N)`, 본문에:

- 선공 → `Ref #N`
- 후공 → `Closes #N`

> 💡 `Closes`가 붙은 PR이 merge되는 순간 이슈가 닫힘. 페어 작업이 다 끝나는 후공 때 닫히게 한 것임.
> ✅ 이슈 #N 페이지를 열어보면 두 PR이 타임라인에 자동으로 걸려 있음.

**STEP 5 — 선공: Approve 받고 Squash and merge**

초록 버튼 ▾ → `Squash and merge` → confirm → 브랜치 삭제 버튼.

**STEP 6 — 후공: merge 시도 → 💥 conflict**

PR에 `This branch has conflicts that must be resolved`가 뜸. 터미널로 해결함.

```bash
git pull origin main
```

파일에 이런 마커가 생김:

```
<<<<<<< HEAD
오늘의 한마디: (후공 문장)
=======
오늘의 한마디: (선공 문장)
>>>>>>> main
```

에디터로 열어 **마커 3줄(`<<<<<<<`, `=======`, `>>>>>>>`)을 전부 지우고** 최종본을 직접 정할 것. 오늘은 두 문장 다 남기기.

```bash
git add practice/week02/pair-a.md
git commit -m "fix: conflict 해결 (#N)"
git push
```

> ✅ PR 새로고침 → conflict 경고가 사라지면 성공. **push를 안 하면 로컬에서만 해결된 상태**라 PR은 계속 빨간불임.
> 💡 VS Code로 열면 `Accept Current / Incoming / Both` 버튼으로도 해결 가능함. 원리는 방금 한 것과 동일 — 마커 지우고 최종본 정하기.

**STEP 7 — 후공: Squash and merge → 이슈 자동 close 확인**

merge 후 **다 같이 이슈 #N 열어볼 것.** `Closes #N` 덕분에 Closed 돼 있음 🎉

**STEP 8 — 둘 다: 로컬 정리**

```bash
git checkout main
git pull
git branch -d feat/N-conflict-본인이름
git push origin --delete feat/N-conflict-본인이름   # 웹에서 이미 지웠으면 에러 나도 정상
```

> ✅ 웹 `branches`에 실습 브랜치가 없고, main에 squash 커밋 2개가 쌓여 있으면 완료임.

---

## 🆘 자주 막히는 곳

| 증상 | 해결 |
|------|------|
| 로컬엔 커밋됐는데 GitHub에 없음 | **push 누락.** `git push` (첫 push면 `git push -u origin 브랜치명`) |
| 마커 지웠는데 PR이 계속 빨간불 | `add → commit → push` 세트를 안 한 것. 특히 push |
| merge 버튼에 squash가 안 보임 | 초록 버튼 오른쪽 **화살표(▾)** 클릭 |
| `Closes #N` 썼는데 이슈가 안 닫힘 | `Closes` / `Fixes` / `Resolves`만 인식됨. PR **본문**에 써야 함 (코멘트 X) |
| conflict 마커가 안 생김 | 서로 다른 줄을 고친 것. 같은 줄인지 확인 |
| 원격 브랜치 삭제에서 에러 | 웹에서 이미 삭제된 것. 무시하고 진행 |

그래도 안 되면: Discord `#dev-track` 또는 페어 찬스.

---

## 🇬🇧 English (TL;DR)

Three topics. (1) **Conventions** — Conventional Commits (`feat/fix/docs/refactor/chore`) and branches like `feat/3-short-desc`. (2) **Issues** — each issue gets `#N`; put it in branches and commits, write `Closes #N` in the PR body and merging auto-closes it. (3) **Merging** — the green button has 3 modes; our default is **Squash and merge**. In pairs, create a conflict on the same line on purpose, fix it in the terminal (`git pull origin main` → delete markers → decide the final text → `add/commit/push`), squash-merge, then watch the issue close itself. Rule of the day: **a commit isn't done until it's pushed.**
