# 🌿 Git 워크플로우 / Git Workflow

이 프로젝트에서 사용하는 브랜치/커밋/PR 규칙입니다.
Branch, commit, and PR conventions used in this project.

---

## 🇰🇷 한국어

### 브랜치 네이밍

| 접두사 | 용도 | 예시 |
|--------|------|------|
| `intro/` | 자기소개 (온보딩용) | `intro/byeol` |
| `feat/` | 새 기능/컨텐츠 추가 | `feat/hook-example` |
| `fix/` | 버그 수정 | `fix/broken-link` |
| `docs/` | 문서만 수정 | `docs/update-readme` |
| `chore/` | 설정/자잘한 변경 | `chore/update-gitignore` |
| `experiment/` | 실험용 | `experiment/mcp-test` |

### 커밋 메시지

간단하게 씁니다. 형식은 자유롭지만 다음이 좋은 예시:

```
자기소개: 정별
feat: settings.json 예시 추가
fix: README 링크 오타
docs: 토요일 미션 절차 보완
```

한 커밋에 여러 개 섞지 말고, 논리 단위로 나누는 걸 지향합니다.

### PR 규칙

- **main 브랜치는 보호되어 있음** — PR 없이 직접 push 불가
- 최소 1명 리뷰 필요 (트랙리드)
- PR 제목은 커밋 메시지 스타일과 동일하게
- PR 본문에 관련 이슈 링크 (`closes #12`)
- Merge 방식: **Squash and merge** (히스토리 깔끔)

### 자주 쓰는 명령어

```bash
# 최신 main 받아오기
git checkout main && git pull

# 브랜치 생성 + 이동
git checkout -b feat/my-feature

# 변경사항 스테이징 + 커밋
git add .
git commit -m "feat: 뭐뭐 추가"

# 원격에 push (첫 push는 -u)
git push -u origin feat/my-feature

# 원격에서 로컬로 브랜치 정리
git fetch --prune
git branch -d feat/merged-feature
```

### 충돌(conflict) 났을 때

```bash
git checkout main
git pull
git checkout feat/my-feature
git rebase main
# 충돌 파일 열어서 해결 후
git add .
git rebase --continue
git push --force-with-lease
```

`--force-with-lease` 는 안전한 force push. 그냥 `--force` 는 피할 것.

---

## 🇬🇧 English

### Branch Naming

| Prefix | Use | Example |
|--------|-----|---------|
| `intro/` | Self-introduction (onboarding) | `intro/byeol` |
| `feat/` | New feature/content | `feat/hook-example` |
| `fix/` | Bug fix | `fix/broken-link` |
| `docs/` | Docs only | `docs/update-readme` |
| `chore/` | Config/misc | `chore/update-gitignore` |
| `experiment/` | Experimental | `experiment/mcp-test` |

### Commit Messages

Keep them simple. Format is flexible; good examples:

```
intro: byeol
feat: add settings.json example
fix: broken link in README
docs: expand Saturday mission steps
```

Split by logical unit — don't cram unrelated changes into one commit.

### PR Rules

- **`main` is protected** — no direct pushes
- At least 1 review required (track lead)
- PR title follows commit message style
- Link related issue in the PR body (`closes #12`)
- Merge strategy: **Squash and merge**

### Handling Conflicts

```bash
git checkout main
git pull
git checkout feat/my-feature
git rebase main
# resolve conflicts, then
git add .
git rebase --continue
git push --force-with-lease
```

Prefer `--force-with-lease` over `--force`.
