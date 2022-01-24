# Vue 시작하기

## 설치

1. Node.js 설치되어있어야함

## Node.js

- 자바스크립트를 브라우저가 아닌 환경에서도 구동할 수 있도록 하는 자바스크립트 런타임 환경
  - 브라우저를 벗어날 수 없던 자바스크립트 언어의 태생적 한계를 해결
  - 즉, 단순히 브라우저만 조작할 수 있던 자바스크립트를 SSR 아키텍처에서도 사용할 수 있도록 함

## NPM (Node Package Manage)

- 자바스크립트 언어를 위한 패키지 관리자. Node.js의 기본 패키지 관리자.
  - Python엔 pip, Node.js엔 NPM!
  - pip와 마찬가지로 다양한 의존성 패키지를 관리

### 공식문서 설치방법

1. 페이지에 [CDN package](https://v3.ko.vuejs.org/guide/installation.html#cdn)로 import하기
2. [npm](https://v3.ko.vuejs.org/guide/installation.html#npm) 사용하여 import하기
3. 공식 [CLI](https://v3.ko.vuejs.org/guide/installation.html#cli)를 사용



## Vue CLI

- Vue.js 개발을 위한 표준 도구(standard tool)
- 프로젝트의 구성을 도와주는 역할을 하며, Vue 개발 생태계에서 표준 tool 기준을 목표로 함
- 확장 플러그인, GUI, ES2015 구성 요소 제공 등 다양한 tool 제공

- 설치

  ```
  $ npm install -g @vue/cli
  ```

- 버전 확인

  ```
  $ vue --version
  ```

  이미 설치되어 있었음.

## Vue CLI로 Vue 프로젝트 생성

> ※ git bash 가 아닌 vscode terminal로 진행 (버전 선택 때문)

- 프로젝트 생성

  ```
  $ vue create {project-name}
  ```

- Vue 버전 선택

  방향키로 > 를 움직이고 enter

  Vue3로 생성

- 프로젝트 생성 성공

  ![image-20220125000035538](C:\Users\USER\AppData\Roaming\Typora\typora-user-images\image-20220125000035538.png)

- 폴더로 이동

  ```
  $ cd my-first-app
  ```

- Run

  ```
  $ npm run serve
  ```

## 이것 저것 설치

- ```
  $ npm i lodash
  ```

- ```
  $ npm i axios
  ```

### 플러그인

- ```
  $ vue add router
  ```

- ```
  $ vue add vuex
  ```

  