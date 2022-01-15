# Git Commit Convention

- 협업 시 Commit Message Convention을 정해두면 서로 간의 코드 리뷰에 도움이 되고, 자신의 이전 로그를 살펴보는 것에도 도움이 된다.

### 1. Commit Message Structure

크게 **제목, 본문, 꼬리말** 세 가지 파트로 나누고, 각 파트는 빈줄을 두어서 구분한다.

```
type: subject  # 제목

body  # 본문

footer  # 꼬리말
```

### 2. Commit Type 타입

``` 
type: subject
```

- 타입은 영어, 첫 문자 대문자로.

- : 뒤에만 space있음

| 타입 이름        | 설명                                                         |
| ---------------- | ------------------------------------------------------------ |
| Feat             | 새로운 기능 추가                                             |
| Fix              | 버그 수정                                                    |
| !HOTFIX          | 급하게 치명적인 버그를 고쳐야하는 경우                       |
| !BREAKING CHANGE | 커다란 API 변경의 경우                                       |
| Design           | CSS 등 사용자 UI 디자인 변경                                 |
| Style            | 코드 포맷 변경, 세미콜론 누락, 코드 수정이 없는 경우 (오타 수정, 탭 사이즈 변경, 변수명 변경 등) |
| Refactor         | 리팩토링                                                     |
| Comment          | 필요한 주석 추가 및 변경                                     |
| Docs             | 문서 수정                                                    |
| Test             | 테스트 코드, 리팩토링 테스트 코드 추가                       |
| Chore            | 빌드 업무 수정, 패키지 매니저 수정                           |
| Rename           | 파일 혹은 폴더명을 수정하거나 옮기는 작업만인 경우           |
| Remove           | 파일을 삭제하는 작업만 수행한 경우                           |

### 3. Subject 제목

코드 변경 사항에 대한 짧은 요약

1. 동사 원형으로 시작(첫 글자 대문자)
   - Fix ~
   - Add ~
   - Change ~
2. 50자 이내로 작성
3. 마지막에 특수문자 삽입 X (! ? . 등)

### 4. Body 본문

- 선택사항. 부연설명이 필요할 때 작성.

1. 한 줄 당 72자 이내로 작성
2. 최대한 상세히
3. 무엇을 변경했는지 or 왜 변경했는지 (어떻게x)

### 5. Footer 꼬리말

- 선택사항
- footer는 작성 안해도 될듯



## 좋은 커밋 메시지를 작성하기 위한 규칙

- 동명사보다 명사를 사용한다.
- 꼭 필요한 경우가 아니라면 관사(a, an, the)는 사용하지 않는다.
- 부정문 `Dont't`를 사용한다.



##### 출처

[협업을-위한-기본적인-git-커밋컨벤션-설정하기](https://overcome-the-limits.tistory.com/entry/%ED%98%91%EC%97%85-%ED%98%91%EC%97%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B8%B0%EB%B3%B8%EC%A0%81%EC%9D%B8-git-%EC%BB%A4%EB%B0%8B%EC%BB%A8%EB%B2%A4%EC%85%98-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)

https://doublesprogramming.tistory.com/256

https://blog.ull.im/engineering/2019/03/10/logs-on-git.html