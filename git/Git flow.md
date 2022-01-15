# Git flow

> vscode flugin "Git Graph"

### Git Flow란

Git을 활용하여 협업하는 흐름.

branch를 활용하는 전략.

cf) 다른 전략들

- Trunk Based: 코드리뷰 생략. 빠른 배포(하루에 수십번). 난이도 높음.



![image-20220115194800073](C:\Users\USER\AppData\Roaming\Typora\typora-user-images\image-20220115194800073.png)

두 개의 큰 브랜치

- Master: 출시를 위한 기본 브랜치
- Develop: 작업을 위한 브랜치

소멸성 브랜치

- Hotfix

### Git Flow 시작하기

1. Develop 브랜치 생성
   - 배포 파이프라인 붙음(CI/CD)
2. 여러 개발자가 각자 feature 브랜치 생성해 개발
3. 

### Conflict 해결방법

같은 파일을 수정했을 경우 conflict가 발생. merge 버튼이 비활성화됨.

1. Pull 받아서 로컬에서 conflict 해결
2. Push 

### Branch basic commands

1. 브랜치 생성

   ```
   $ git branch {branch name}
   ```

2. 브랜치 이동

   ```
   $ git checkout {branch name}
   ```

   

   과거 커밋으로 이동 (타임머신 타고 이동)

   ```
   $ git checkout {commit id 4글자}
   ```

   해당 커밋 시점으로 돌아가고 head가 그 커밋을 가리킴

3. 브랜치 전환

   ```
   $ git switch {branch name}
   ```

   

4. 브랜치 생성+이동

   ```
   $ git checkout -b {branch name}
   ```

5. 브랜치 목록

   ```
   $ git branch
   ```

5. 브랜치 삭제

   ```
   $ git branch -d {branch name}
   ```

### Branch merge란

각 branch에서 작업을 한 후 합치는 것.

만약 동일한 파일을 수정한 경우, 충돌이 발생한다.

이럴 땐 반드시 직접 수정을 진행해야한다.

### Github Flow 기본원칙

1. master branch는 반드시 배포 가능한 상태여야한다.
2. feature branch는 각 기능의 의도를 알 수 있도록 작성한다.
3. Commit message는 매우 중요하며, 명확하게 작성한다.
4. Pull Request를 통해 협업을 진행한다.
5. 변경사항을 반영하고 싶다면 master branch에 병합한다.

### Github Flow Models

#### Shared Repository Model

d

#### Fork & Pull Model



- github flow에서 핵심은 Pull Request를 통합 협업