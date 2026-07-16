# 🌿 Git 워크플로우 치트시트

이 프로젝트(그리고 SS- 레포들)에서 쓰는 규칙. **이 한 장만 기억하면 됩니다.**

---

## 브랜치 이름 — `타입/이슈번호-설명`

```
feat/12-login-button   새 기능      (이슈 #12)
fix/7-readme-typo      수정         (이슈 #7)
docs/9-onboarding      문서만       (이슈 #9)

experiment/뭐뭐         실험(막써도 됨, 이슈 없어도 OK)
intro/이름              자기소개 (1주차 온보딩 예외 — 이슈번호 없음)
```

- 영문 소문자, 띄어쓰기는 `-`
- 타입 = 아래 커밋 타입과 동일 (`feat`·`fix`·`docs`·`refactor`·`chore`)
- 이슈번호를 넣으면 브랜치만 봐도 "왜 만든 브랜치"인지 추적됨

## 커밋 메시지 — Conventional Commits

`타입: 설명` 형식. **타입 5개만** 기억.

```
feat      새 기능 / 새 내용 추가
fix       버그 / 오류 수정
docs      문서만 변경
refactor  동작은 같고 구조만 개선
chore     잡일 (설정, 폴더 정리)

예)
feat: pre-commit hook 예시 추가
fix: README 깨진 링크 수정
```

❌ `수정`, `업데이트`, `asdf` — 나중에 아무도 못 알아봄
> 💡 애매하면 일단 `chore`. 배경 설명 → [`sessions/week02/mission.md`](sessions/week02/mission.md)

## PR 규칙 (전 레포 공통)

- `main` 브랜치 직접 push 금지 (protected) → 무조건 PR
- 최소 리뷰 1명 승인 필요
- (그 외 브랜치는 리뷰 없이 승인 가능)
- 이슈 연결: PR 본문에 `closes #12`
- merge 방식: **Squash and merge**

## 브랜치 생성~commit~push 명령어 

```bash
1] 초반 세팅
git checkout main[여기에 브랜치 이름]  #해당 브랜치로 *이동*
git pull                             # 시작 전: 최신화 =>이게 제일 중요함!@!@! 이거 안땡기고 푸시하면 엉킨다

2] 브랜치 생성과 이동
(브랜치명은 예시임. 본인이 알아서 작성)
git branch intro/star               #'intro/star'라는 브랜치를 생성.
git checkout intro/star             # 생성된 브랜치로 이동

3] 깃에 업로드(브랜치 내에서 폴더/파일 변화가 있을 때)
git add .                            #1 "현재 폴더와 그 하위 폴더에서 변경된 모든 파일을 바구니에 담겠다 #2 CLI에서 . (점 하나)는 '현재 내가 위치한 폴더 전체'를 지칭 #3 add를 통해 수정된 코드가 '작업공간' -> '스테이징' 영역으로 이동
git commit -m "feat: 뭐뭐~"           #1 메시지와 함께 저장 #2 '-m' 은 메시지를 입력하겠다는 뜻. 협업에서는 커밋 컨벤션에따라 꼭 메시지 입력해줘야함  #3 '스테이징' 영역 -> 메시지와 함께 로컬 레포(클론된 그거 맞음)에 저장됨
git push        # 깃헙에 올리기 #'로컬 레포' -> '깃헙 레포' 이

4] 브랜치 삭제(브랜치 작업이 merge되면 삭제해주는게 일반적인 개발 rule)
(보통 PR이 합쳐지고(merge) 나서 다 쓴 브랜치를 청소할 때 사용. PR 머지와 이슈관리는 추후 설명)

git branch -d intro/star           # merge 후 정리
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
