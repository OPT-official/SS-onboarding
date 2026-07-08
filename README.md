# SS-onboarding

**OPT 2026 Summer Season — 개발 트랙 온보딩 레포**
_OPT 2026 Summer Season — Dev Track Onboarding Repo_

---

## 🇰🇷 한국어

이 레포는 OPT 개발 트랙 학회원들이 **GitHub 협업 기본 사이클**(clone → branch → commit → push → PR → review → merge)을 실제로 몸에 익히기 위한 **연습장(sandbox)** 입니다.

여기서는 부담 없이 실수해도 됩니다. 실제 산출물은 `SS-harness-lab`, 최종 공동 하네스는 `SS-harness` 레포에서 다룹니다.

### 트랙 구성원

| 역할 | 이름 |
|------|------|
| 트랙 리드 (학회장) | 정별 |
| 멤버 | 정지나 |
| 멤버 | 박세인 |
| 멤버 | 박인찬 |

### 첫 미션 (토요일 왕십리 모임)

1. 이 레포를 로컬에 clone
2. 본인 이름으로 브랜치 생성 (`intro/이름`)
3. `members_intro/이름.md` 파일 작성 (템플릿은 `members_intro/TEMPLATE.md`)
4. commit → push → Pull Request 열기
5. 트랙리드 리뷰 후 merge

자세한 절차는 [`docs/saturday-mission.md`](docs/saturday-mission.md) 참고.

### 폴더 구조

```
SS-onboarding/
├── .github/              # 이슈/PR 템플릿, 라벨 정의
├── docs/                 # 워크플로우 가이드, 미션 문서
└── members_intro/        # 각자 자기소개 (토요일 실습)
```

### 주간 운영 원칙

- 매주 과제는 **Issue**로 발행됩니다 (`weekly-task` 라벨 + milestone)
- 산출물은 **Pull Request**로 제출하고, 이슈 번호를 연결하세요 (`closes #12`)
- 피드백은 **PR 리뷰 코멘트**로 주고받습니다
- main 브랜치는 protected — 반드시 PR을 통해서만 merge 가능

### 관련 레포

- `SS-onboarding` (이 레포) — 온보딩 & 실습 샌드박스
- `SS-harness-lab` — 개인 하네스 산출물 (4~5주차)
- `SS-harness` — 학회 공동 하네스 최종 산출물 (8월~)

---

## 🇬🇧 English

This repository is a **sandbox** for OPT Dev Track members to practice the **core GitHub collaboration cycle** (clone → branch → commit → push → PR → review → merge) hands-on.

Feel free to make mistakes here. Real deliverables live in `SS-harness-lab`, and the final shared harness in `SS-harness`.

### Track Members

| Role | Name |
|------|------|
| Track Lead (President) | Byeol Jung |
| Member | Jina Jung |
| Member | Sein Park |
| Member | Inchan Park |

### First Mission (Saturday meetup — Wangsimni)

1. Clone this repo locally
2. Create a branch under your name (`intro/yourname`)
3. Write `members_intro/yourname.md` (see `members_intro/TEMPLATE.md`)
4. Commit → push → open a Pull Request
5. Track lead reviews, then merges

See [`docs/saturday-mission.md`](docs/saturday-mission.md) for the full walkthrough.

### Folder Structure

```
SS-onboarding/
├── .github/              # Issue/PR templates, label definitions
├── docs/                 # Workflow guides, mission docs
└── members_intro/        # Self-introductions (Saturday practice)
```

### Weekly Operations

- Weekly tasks are issued as **Issues** (`weekly-task` label + milestone)
- Submit deliverables via **Pull Request**, linking the issue (`closes #12`)
- Feedback happens through **PR review comments**
- `main` is protected — merges only via PR

### Related Repositories

- `SS-onboarding` (this repo) — Onboarding & practice sandbox
- `SS-harness-lab` — Individual harness deliverables (weeks 4–5)
- `SS-harness` — Final shared harness (August onward)
