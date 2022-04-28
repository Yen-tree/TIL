## 🧲 const, let, var 비교

> #### 요약
>
> - var 보다는 let 과 const 를 사용
> - 변경하지 않는 값(상수)이라면 let 보다는 const 를 사용하는 것이 안전

> #### 참고) 코드블록 & 블록 레벨 스코프
>
> 함수, if, for, while, try/catch 등

### var

- 문제점: 함수 코드 블록만 지역 스코프로 인정함
  - 따라서 오로지 함수 코드 블록만을 지역 스코프로 인정하는 `var` 대신, 블록 레벨 스코프를 지원하는 `const`와 `let`을 사용하는 것을 권장

### let

- 변수 재할당 가능 (중복 선언은 let, const 모두 불가)

```javascript
let name = 'kmj'
console.log(name) // output: kmj

let name = 'howdy' // 재할당 불가 output: Uncaught SyntaxError: Identifier 'name' has already been declared

name = 'howdy'
console.log(name) // output: howdy
```



### const

- 반드시 선언과 초기화를 동시에 해야한다.
- let과 달리 변수 재할당 불가능

```javascript
// 원시값의 재할당
const name = 'kmj'
name = 'howdy' // output: Uncaught TypeError: Assignment to constant variable.

// 객체의 재할당
const name = {
  eng: 'kmj',
}
name.eng = 'howdy'

console.log(name) // output: { eng: "howdy" }
```





