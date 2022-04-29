# Pandas

```python
import pandas as pd  # 주로 pd로 줄여 부름
```

### loc



```python
pdata.loc[0]        #행 데이터를 가져온다.
```



```python
pdata.loc[2:3]      # ※주의: 3미만이 아니라 3까지 가져옴!
```



```python
pdata.loc[2:3, 'VIP']   #2~3까지 행 중 VIP컬럼 데이터를 가져온다.
```



```python
pdata.loc[0:3,['일매출','VIP']] #0~3까지 행에서 일매출과 vip데이터를 가져온다.
```



```python
pdata.loc[:,'매장위치':'VIP']   #매장 위치 컬럼부터 VIP컬럼까지 모든 행의 데이터를 가져온다.
```



### 통합

1. concat

   ```
   pd.concat([df1,df2], ignore_index=True)
   ```

   



### groupby

```python
df
Out[88]: 
     A      B         C         D
0  foo    one  1.346061 -1.577585
1  bar    one  1.511763  0.396823
2  foo    two  1.627081 -0.105381
3  bar  three -0.990582 -0.532532
4  foo    two -0.441652  1.453749
5  bar    two  1.211526  1.208843
6  foo    one  0.268520 -0.080952
7  foo  three  0.024580 -0.264610
```



```python
df.groupby("A").sum()
Out[89]: 
            C         D
A                      
bar  1.732707  1.073134
foo  2.824590 -0.574779
```



여러 개의 기준으로 정렬할 때

```python
df.groupby(["A", "B"]).sum()
Out[90]: 
                  C         D
A   B                        
bar one    1.511763  0.396823
    three -0.990582 -0.532532
    two    1.211526  1.208843
foo one    1.614581 -1.658537
    three  0.024580 -0.264610
    two    1.185429  1.348368
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```



```python
import numpy as np  # 주로 np로 줄여 부름
```

