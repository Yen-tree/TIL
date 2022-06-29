# Request 시 데이터 전달 방법

## 1. Query Parameter

```
/users?id=123  # 아이디가 123인 사용자를 가져온다.
```

## 2. Path Variable

```
/users/123  # 아이디가 123인 사용자를 가져온다.
```

경로를 변수로서 사용



## 3. body에 data로 전달(get은 body로 전달X)





## 그럼 Path Variable과 Query Parameter를 각각 언제 사용해야 하는가?

만약 어떤 **resource를 식별**하고 싶으면 **Path Variable**을 사용하고,
**정렬이나 필터링**을 한다면 **Query Parameter**를 사용하는 것이 Best Practice이다.

```
/users  # 사용자 목록을 가져온다.
/users?occupation=programer  # 프로그래머인 사용자 목록을 가져온다.
/users/123  # 아이디가 123인 사용자를 가져온다.
```





## 제안

communityId는 Path Variable로, 나머지는 Query Parameter로 하면 어떨까?





#### 참고

https://ryan-han.com/post/translated/pathvariable_queryparam/