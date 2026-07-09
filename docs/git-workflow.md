# 🌿 Git 워크플로우 치트시트

이 프로젝트(그리고 SS-Harness 레포들)에서 쓰는 규칙. **이 한 장만 기억하면 됩니다.**

---

## 브랜치 이름

```
intro/이름        자기소개 (온보딩)

feat/뭐뭐         새로운 기능
fix/뭐뭐          수정
docs/뭐뭐         문서만
debug/뭐뭐        디버깅

experiment/뭐뭐   실험(막써도 됨)
```

## 커밋 메시지

한 줄로, 뭘 했는지 보이게. 형식보다 **명확함**이 우선.

```
예시)
intro: 정지나 자기소개 최초 생성
feat: pre-commit hook 예시 추가
fix: README 깨진 링크 수정
```

❌ `수정`, `업데이트`, `asdf` — 나중에 아무도 못 알아봄

## PR 규칙 (전 레포 공통)

- `main` 브랜치 직접 push 금지 (protected) → 무조건 PR
- 최소 리뷰 1명 승인 필요
- (그 외 브랜치는 리뷰 없이 승인 가능)
- 이슈 연결: PR 본문에 `closes #12`
- merge 방식: **Squash and merge**

## 매일 쓰는 명령어 6개

```bash
git checkout main &&         # 시작 전: 최신화 =>이게 제일 중요함!@!@!
git pull
git checkout -b feat/my-work         # 브랜치 생성+이동

git add .                            # 변경사항 담기
git commit -m "feat: 뭐뭐"           # 저장
git push -u origin feat/my-work      # 올리기 (첫 push만 -u)
git branch -d feat/my-work           # merge 후 정리
```

## 충돌(conflict) 났을 때

```bash
git checkout main && git pull        # main 최신화
git checkout feat/my-work
git rebase main                      # 내 브랜치에 main 반영
# → 충돌 파일 열어서 <<<< ==== >>>> 부분 정리 후:
git add . && git rebase --continue
git push --force-with-lease          # --force 말고 이걸로
```

## 급할 때 이것만

| 하고 싶은 것 | 명령어 |
|---|---|
| 지금 무슨 상태지? | `git status` |
| 뭘 바꿨더라? | `git diff` |
| 방금 커밋 취소 (변경은 유지) | `git reset --soft HEAD~1` |
| 이 파일만 원래대로 | `git checkout -- 파일명` |
| 히스토리 보기 | `git log --oneline -10` |

---

## 🇬🇧 English (TL;DR)

Branches: `intro/`, `feat/`, `fix/`, `docs/`, `experiment/`. One-line clear
commit messages. `main` is protected — PR only, 1 approval, squash-merge,
link issues with `closes #N`. On conflicts: rebase onto main, resolve,
`--force-with-lease`.
