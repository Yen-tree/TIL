# lambda

- (공식문서) lambda 키워드를 사용해서 작고 이름없는 함수를 만들 수 있다.

- 표현식 내에서 사용할 수 있는 최소 함수 정의
- 함수를 한 줄로 만들 수 있다!

```
lambda 매개변수 : 표현식
```

#### 예시1

##### 일반함수

```python
>>> def hap(x, y):
...   return x + y
...
>>> hap(10, 20)
30
```

##### -> lambda 함수

```python
>>> (lambda x,y: x + y)(10, 20)
30
```

#### 예시2

```python
>>> list(map(lambda x: x ** 2, range(5)))
[0, 1, 4, 9, 16]
```

#### 예시3 - sort

```python
>>> pairs = [(1, 'one'), (2, 'two'), (3, 'three'), (4, 'four')]
>>> pairs.sort(key=lambda pair: pair[1])
>>> pairs
[(4, 'four'), (1, 'one'), (3, 'three'), (2, 'two')]
```

