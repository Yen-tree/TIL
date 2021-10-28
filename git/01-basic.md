# git basic

## H2. 내용

 Git이란? 버전관리

**git이란?**

**what** (분산) 버전 관리 시스템 distributed version ~

코드의 히스토리

why| 버전관리: 과거의 버전으로 돌아갈 필요가 있을 것 같아서. -> 용량의 문제

깃의 기능 -> 변경사항만 남기자

> git이 있다면,

차이가 무엇이고 수정 이유를 log로 남길 수 있다.



CLI (Command Line Interface)

GUI (Graphical User Interface)

|      |            CLI             |                          GUI                           |
| ---- | :------------------------: | :----------------------------------------------------: |
| 장점 |        자유도 높음         | 1. 쓰기 쉬움<br />2. 안전장치 있음 ex) 삭제하면 휴지통 |
| 단점 | 불편하고 배워야 쓸 수 있음 |                   잠금이 있는 점(?)                    |



단축키

| 단축키   | 기능                  |
| -------- | --------------------- |
| ctrl + l | 페이지 위로 쭉 올리기 |
| ctrl + c | 취소                  |
|          |                       |



```
$ git remote add origin <URL>
$ git init

# 촬영에 비유
$ git add .  						 #1.촬영 준비
$ git commit -m '<COMMOT MESSAGE>'	 #2.촬영 with메시지
$ git push origin master			 #3.업로드

# 상태 점검
$ git log
$ git status
```

add . 촬영준비 / commit  -m git 촬영 / push 업로드

```
$ mkdir <폴더명> 	:폴더 생성
$ cd <폴더명>  : 폴더 접근
$ cd .. : 폴더 나오기(상위 폴더로 감)


$ ls : 폴더 내 항목들 보기
```





TIL 참고

https://github.com/cheese10yun/TIL