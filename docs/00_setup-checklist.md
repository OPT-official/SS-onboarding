# ✅ 트랙리드 초기 세팅 체크리스트

**정별 전용. 토요일 전 완료.** 파일 push는 됐다는 전제로, GitHub 웹 UI에서만 되는 것들.
**⚠️ 아래 2~4번은 3개 레포(onboarding / Harness-private / Harness-communal) 모두 적용.**

---

## 1. 라벨 생성

**gh CLI (권장)** — 각 레포 폴더에서 실행:

```bash
gh label create weekly-task      --color "0E8A16" --description "주간 과제"
gh label create feedback-request --color "FBCA04" --description "피드백 필요"
gh label create skill-share      --color "5319E7" --description "팁/발견 공유"
gh label create bug              --color "D73A4A" --description "동작 안 함"
gh label create question         --color "D876E3" --description "질문"
gh label create docs             --color "0075CA" --description "문서"
gh label create harness          --color "1D76DB" --description "하네스 관련"
gh label create good-first-task  --color "7057FF" --description "입문용 작업"
gh label create blocked          --color "B60205" --description "막혀있음"
gh label create in-progress      --color "C2E0C6" --description "작업 중"
```

웹 UI로 하려면: `Issues → Labels → New label`, 색상은 `.github/labels.yml` 참고.

## 2. Milestone 생성

`Issues → Milestones → New milestone` (SS-onboarding에만 있어도 시작 가능)

- `Week 0-1: GitHub 기초` / `Week 2: Claude Code 기본`
- `Week 3-4: 개인 하네스` / `Week 5+: 공동 하네스`

날짜는 실제 토요일 일정 기준으로.

## 3. main 브랜치 protection

`Settings → Branches → Add branch ruleset` (또는 protection rule)

- Pattern: `main`
- ✅ Require a pull request before merging → approvals: **1**
- ✅ Require conversation resolution before merging
- ⬜ status checks (CI 없음 — 나중에)

💡 초기 파일 push는 protection 켜기 **전에.**

## 4. 팀 권한

`Org Settings → Teams` → `dev-track` 팀 생성:

- 멤버: 정별(maintainer), 정지나, 박세인, 박인찬
- 3개 레포 모두 `Write` 권한 부여

## 5. 첫 이슈 발행 (SS-onboarding)

- 제목: `[Week 0] 자기소개 PR 올리기 — 토요일 실습`
- 라벨: `weekly-task`, `good-first-task` / Milestone: Week 0-1
- Assignees: 3명 / 본문: `docs/01_saturday-mission.md` 링크

## 6. CODEOWNERS 아이디 채우기 (SS-Harness-private)

`.github/CODEOWNERS`의 placeholder를 실제 GitHub 아이디로 교체.

---

끝났으면 → [`03_ops-playbook.md`](03_ops-playbook.md) 로 이동. 주간 운영은 거기서.
