# Alias란?

명령을 간소화하여 다른 이름으로 사용할 수 있도록 해주는 쉘 내부 명령어이다.

```jsx
# 현재 등록되어 있는 모든 alias 출력
alias

# alias 명령어별칭 = '명령어'
alias flog='cd /log/myservice/info'

# 별칭 삭제
unalias flog
```

# alias 영구 등록하는 방법

하지만 위의 방법은 시스템을 재부팅하고 나면 alias 설정해준게 초기화된다.

- **그래서 ~(홈디렉토리) 경로에 .bashrc 파일이나 .bash_aliases에 영구 등록 해야한다!!**
  - 나는 .bash_aliases 를 만듬

```jsx
~# vim .bash_aliases
```

```jsx
alias pycharm='/root/pycharm-2022.2.3/bin/pycharm.sh'
alias gs='git status'
alias gd="git diff"
alias ga='git add'
alias gcm='git commit -m'
alias gb='git branch'
alias gco='git checkout'
alias glo="git log --oneline"
```
