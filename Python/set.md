# set

- 수학에서의 집합과 같은 자료형
- 순서가 없다.
- 원소가 중복되지 않는다.
- `{}`



## :icecream: 차집합, 교집합, 합집합

### 연산자

- 차집합 : `-`
  - a - b
- 교집합 : `&`
  - a & b
- 합집합 : `|`
  - a | b
- 대칭차집합(합집합-교집합) : `^`
  - a ^ b



### 함수

- **union**() - **합집합**을 만들어 리턴
- **update**() - 합집합을 만들어 원본 데이터를 갱신(수정)
- **difference**() - **차집합**을 만들어 리턴
- **difference_update**() - 차집합을 만들어 원본 데이터를 갱신
- **intersection**() - **교집합**을 만들어 리턴 
- **intersection_update**() - 교집합을 만들어 원본 데이터를 갱신
- **symmetric_difference**() - **대칭차**를 만들어 리턴
- **symmetric_difference_update**() - 대칭차를 만들어 원본 데이터를 갱신

> 그냥 함수는 값을 리턴하는 반면 뒤에 **update가 붙은 함수는 원본 데이터를 변경**한다.



## 원소 삽입/삭제

- add(값) : 새로운 값 추가
  - a.add(10)
- remove(값): 값을 삭제 (값이 없으면 에러메시지 출력)
  - a.remove(10)

- discard(값) : 전달받은 값을 **삭제** (없을 때 그냥 무시)
  - a.discard(10)

- pop() - **임의의 값을 리턴**하고 삭제
- clear() - 집한에 있는 **모든 값을 삭제**
- copy() - 집합을 **복제**하여 리턴



## is~ 함수

True 또는 False를 리턴한다.

- **isdisjoint**() - 두 집합이 공통 원소를 갖지 않는가?

  - ```
    {1, 2, 3}.isdisjoint({5, 6})
    >> True
    {1, 2, 3}.isdisjoint({3, 4, 5, 6})
    >> False
    ```

- **issubset**() - 부분집합(subset)인가?

  - ```
    {1, 2}.issubset({1, 2, 3, 4})
    >> True
    ```

- **issuperset**() - 확대집합(superset)인가?

  - ```
    {1, 2, 3, 4}.issubset({1, 2})
    >> True
    ```

