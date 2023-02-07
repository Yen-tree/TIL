# 🎅 원격 저장소에 push한 commit 되돌리기

- 상황

RvR 미션으로 작성한 코드를 4개의 메인 브랜치에 반영하기 위해 각각 PR을 올리려고 했음.

> **4개의 메인 브랜치**
>
> 1. Branch name : master (정규 버전)
> 2. Branch name : RTG-2931-NOT_DUT (ONU 텔넷 관련 사용하지 않는 버전)
> 3. Branch name : NOT-ATTEN (감쇄기 사용하지 않는 버전)
> 4. Branch name : NOT-DUT-ATTEN (ONU 텔넷 관련 + 감쇄기 사용하지 않는 버전)

**각 브랜치에서 새로운 브랜치를 따서**, 거기에 수정사항을 반영한 후 메인브랜치에 merge하기 위한 PR을 올리려고 했음.

근데 **각 브랜치에서 새로운 브랜치를 따서** 를 까먹고 NOT-ATTEN(메인브랜치)에서 수정사항 반영하고 push를 해버림..

그 결과 PR 없이 원격 저장소 NOT-ATTEN 브랜치에 수정사항이 반영되어버림.

- 해야 하는 것

원격 저장소 NOT-ATTEN 브랜치를 push 전 상태로 되돌려야함!

- 방법

git reset --hard 4f0cc60f456(돌아가고싶은 커밋) **→ --hard 옵션은 변경 사항을 아예 삭제함.**

git push -f **→ 원격 저장소에 강제로 push**
