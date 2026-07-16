# 📑 docs 인덱스

문서를 **성격별로** 나눠 뒀습니다. "이거 내가 볼 건가?"부터 확인하세요.

```
docs/
├── git-cheatsheet.md      상시 참고 · 전원
├── sessions/              주차별 세션 자료 (미션·과제)
│   ├── week01/
│   │   ├── mission.md     토요일 실습 절차 (clone→PR→merge)
│   │   └── homework.pdf   1주차 과제
│   └── week02/
│       └── mission.md     컨벤션·이슈·conflict 실습
└── lead/                  트랙리드(정별) 전용
    ├── setup-checklist.md  레포 초기 세팅 (라벨·milestone·protection)
    └── ops-playbook.md     주간 운영 대본
```

## 뭘 언제 보나

| 문서 | 대상 | 성격 | 언제 |
|------|------|------|------|
| [`git-cheatsheet.md`](git-cheatsheet.md) | 전원 | 상시 참고 | 브랜치/커밋/PR 규칙 헷갈릴 때 |
| [`sessions/week01/mission.md`](sessions/week01/mission.md) | 멤버 | 주차 자료 | 1주차(자기소개 PR 실습) |
| [`sessions/week01/homework.pdf`](sessions/week01/homework.pdf) | 멤버 | 주차 과제 | 1주차 과제 |
| [`sessions/week02/mission.md`](sessions/week02/mission.md) | 멤버 | 주차 자료 | 2주차(컨벤션·이슈·conflict) |
| [`lead/setup-checklist.md`](lead/setup-checklist.md) | 리드 | 운영 | 레포 만들 때 1회 |
| [`lead/ops-playbook.md`](lead/ops-playbook.md) | 리드 | 운영 | 매주 반복 |

> 💡 주차가 늘면 `sessions/weekNN/`을 추가하세요. 번호 prefix 대신 폴더로 나누면 충돌이 없습니다.
> 📌 `sessions/`(리드가 만든 **세션 자료**)와 최상위 `weekly-logs/`(멤버 각자의 **주간 로그**)는 다릅니다.
