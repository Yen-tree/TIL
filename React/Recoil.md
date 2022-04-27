# Recoil

- 페이스북에서 만든 상태관리 라이브러리. context API 기반으로, React스러움을 유지할 수 있음.
- **비동기 처리** 기반으로 작성되어있음
- **동시성 모드** 지원

![img](https://velog.velcdn.com/images%2Fiamjoo%2Fpost%2F165ec2d3-6989-4aee-bf12-ee755ef091a6%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-03-19%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2012.05.49.png)



- **Redux, Mobx**와 비교
  - Recoil -> React 라이브러리
  - Redux, Mobx -> 외부 라이브러리
    - store가 외부요인 취급됨. 그래서 React 내부 스케줄러에 접근할 수 없다 -> **동시성 모드 활용이 어려움**
    - 기본적인 store 구성을 위해 많은 보일러 플레이트와 장황한 코드를 작성해야함
    - 또한 비동기 데이터 처리 또는 계산된 값 캐시 등을 해결하기 위해 또 다른 라이브러리를 사용해야 한다 (redux thunk, redux saga등)



## 주요 개념

>Recoil을 사용하면 *atoms* (공유 상태)에서 *selectors* (순수 함수)를 거쳐 React 컴포넌트로 내려가는 data-flow graph를 만들 수 있다.

### Atoms

- 컴포넌트가 구독할 수 있는 상태(state)의 단위
- atom이 업데이트되면 각각의 구독된 컴포넌트는 새로운 값을 반영하여 다시 렌더링 된다.
-  `atom`함수를 사용해 생성

- atom을 생성하려면 고유한 키 값 & 디폴트 값을 설정해야함

### selector

- **Selector**는 atoms나 다른 selectors를 입력으로 받아들이는 순수 함수(pure function)다.

-  Selectors는 atoms 상태값을 동기 또는 비동기 방식을 통해 변환한다.
- 상위의 atoms 또는 selectors가 업데이트되면 하위의 selector 함수도 다시 실행됨
- 컴포넌트들은 selectors를 atoms처럼 구독할 수 있으며 selectors가 변경되면 컴포넌트들도 다시 렌더링된다.



**useRecoilState** : atom의 값을 구독하여 업데이트할 수 있는 hook. `useState`와 동일한 방식으로 사용할 수 있다.

**useRecoilValue** : setter 함수 없이 atom의 값을 반환만 한다.

**useSetRecoilState** : setter 함수만 반환한다.