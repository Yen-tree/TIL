# Numpy

### methods

- nonzero() : 요소들 중 0이 아닌 값들의 index 들을 반환해 주는 함수
  - 이차원배열에선 행 인덱스 벡터, 열 인덱스 벡터 -> 2개의 벡터 형태로 리턴

- zip(): 동일한 개수로 이루어진 자료형을 묶어주는 역할





### Simple Array Operations

a, b : 행렬(array)

- Element-wise operations : 같은 위치의 원소끼리 연산 (행렬곱X)
  - a + b, a-b, a*b, a/b

- Transpose
  - a.transpose() **or** a.T

- Inverse matrix
  - np.linalg.inv(a)
- Matrix multiplication (행렬곱)
  - a @ b



- reshape : 기존 데이터는 유지하고 차원과 형상을 바꿔줌