# ✅ 트랙리드 세팅 체크리스트 / Track Lead Setup Checklist

**대상:** 정별 (트랙리드) — 토요일 모임 전 완료
**For:** Byeol (track lead) — complete before Saturday meetup

이 레포 파일들은 push로 끝나지만, GitHub 웹 UI에서만 되는 것들이 몇 개 남아있습니다.
The repo files are handled by `push`, but a few things must be set up in the GitHub web UI.

---

## 1. 파일 push 하기 / Push these files

```bash
# 로컬에 clone 안 되어 있으면
git clone https://github.com/OPT-official/SS-onboarding.git
cd SS-onboarding

# 이 zip 파일 내용을 여기에 풀기 (이미 있는 파일은 덮어씀)
# unzip ~/Downloads/SS-onboarding-setup.zip -d .

git add .
git commit -m "chore: initial repo setup (templates, docs, structure)"
git push origin main
```

`main`이 이미 protected면 첫 push는 예외 처리하거나, protection을 나중에 켜세요.

---

## 2. 라벨 만들기 / Create labels

**옵션 A. gh CLI로 (권장)**
```bash
# gh CLI 설치되어 있고 auth 된 상태에서
gh label create weekly-task     --color "0E8A16" --description "매주 트랙리드가 발행하는 과제"
gh label create feedback-request --color "FBCA04" --description "리뷰나 의견이 필요함"
gh label create skill-share      --color "5319E7" --description "팀에 유용한 팁/발견 공유"
gh label create bug              --color "D73A4A" --description "예상대로 동작하지 않음"
gh label create question         --color "D876E3" --description "질문"
gh label create docs             --color "0075CA" --description "문서 관련"
gh label create harness          --color "1D76DB" --description "Claude Code 하네스 관련"
gh label create good-first-task  --color "7057FF" --description "처음 시작하기 좋은 작업"
gh label create blocked          --color "B60205" --description "다른 것에 막혀있음"
gh label create in-progress      --color "C2E0C6" --description "작업 중"
```

**옵션 B. 웹 UI에서**
`Issues` → `Labels` → `New label` — `.github/labels.yml` 파일 보고 하나씩 만들기.

---

## 3. Milestone 만들기 / Create milestones

`Issues` → `Milestones` → `New milestone`

- `Week 1: GitHub 기초` (due: 다음 토요일)
- `Week 2: Claude Code 기본` 
- `Week 3: 공동 GitHub 구축`
- `Week 4-5: 개인 하네스 산출물`
- `Week 6+: 학회 공동 하네스`

날짜는 실제 일정에 맞춰 조정.

---

## 4. main 브랜치 protection / Branch protection

`Settings` → `Branches` → `Add rule` (또는 `Branch protection rules`)

- Branch name pattern: `main`
- ☑️ **Require a pull request before merging**
  - Required approvals: `1`
  - ☑️ Dismiss stale approvals when new commits are pushed
- ☑️ **Require conversation resolution before merging**
- ☐ Require status checks (아직 CI 없음 — 나중에 켜기)
- ☐ Do not allow bypassing (트랙리드는 예외 두고 싶으면 끄기)

💡 첫 push는 protection 켜기 **전에** 하는 게 편함.

---

## 5. 팀 권한 확인 / Team permissions

`OPT-official` org의 `Settings` → `Teams` 에서 개발 트랙 팀 만들고 이 레포에 `Write` 권한 부여.

- Team: `dev-track`
- Repo `SS-onboarding` access: `Write`
- Members: 정별(maintain), 정지나, 박세인, 박인찬

---

## 6. Discussions 켜기 (선택) / Enable Discussions (optional)

`Settings` → `General` → `Features` → ☑️ `Discussions`

주간 회고, 자유 질문, 아이디어 공유에 좋음.

---

## 7. 초기 이슈 하나 발행 / Post the first issue

토요일 실습용 트래킹 이슈:

**제목:** `[Week 0] 자기소개 PR 올리기 — 토요일 실습`
**라벨:** `weekly-task`, `good-first-task`
**Milestone:** `Week 1: GitHub 기초`
**Assignees:** 정지나, 박세인, 박인찬
**본문:** `docs/saturday-mission.md` 참고

---

## 8. 다음 레포도 미리? / Bootstrap sibling repos?

`SS-harness-lab`, `SS-harness` 도 지금 만들어둘지 결정.
당장 안 만들어도 되지만, org 안에서 나란히 보이면 학회원들이 그림 잡기 쉬움.
빈 레포에 README 한 장만 넣어두는 것도 방법.
