# git credential manager

### 상황

싸피에서 준 오디세이 노트북으로 컴퓨터를 바꿨다.

프로젝트 수행을 위해 깃랩에서 리포 clone을 받으려고 하는데 git credential manager 창이 따로 뜨면서 깃랩 아이디랑 비번을 입력하도록 했다.

근데 다이렉트 아이디 비번을 몰라서 헤멨음.. 

아이디는 메일주소 포함이었고

비번도 메일주소 포함 S이메일@naver.com6 였다 ㅎㅎ

### 이유

새로운 노트북이기 때문에 gitlab 계정 초기 로그인이 필요한 것

### 해결

git credential manager 창에서 올바른 아이디, 비번으로 한번 로그인 하면 된다.



### 상황2

깃랩 비밀번호를 변경했다.

다시 `fatal: Authentication failed for 'https://lab.ssafy.com/s06-webmobile1-sub1/S06P11A503.git/'` 라고 뜸

### 이유

비밀번호를 바꿨는데 로컬은 바꾸기 전 비밀번호를 갖고 있기 때문

### 해결

1. git 계정정보를 지운다

```
git config --local --unset credential.helper // 현재 레파지토리에서만 삭제
git config --global --unset credential.helper // 현재 계정만 삭제
git config --system --unset credential.helper // 시스템의 모든 사용자와 저장소 계정정보 삭제
```

2. git credential manager 재로그인