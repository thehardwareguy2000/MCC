```python
print('enter A data:')
Ad=int(input())
if Ad>0:
    Bipolar_Ad=+1
else:
    Bipolar_Ad=-1

```

    enter A data:
    1
    


```python
print('enter B data:')
Bd=int(input())
if Bd>0:
    Bipolar_Bd=+1
else:
    Bipolar_Bd=-1
```

    enter B data:
    0
    


```python
A= [ int(x) for x in input().split()] 
import numpy as np
A_chip_code = np.array(A)
print(type(A_chip_code))
A_chip_code[np.isclose(A_chip_code, 0)] = -1
print(A_chip_code)
```

    0 0 1 1 0 0 1 1
    <class 'numpy.ndarray'>
    [-1 -1  1  1 -1 -1  1  1]
    


```python
B= [ int(x) for x in input().split()] 
import numpy as np
B_chip_code = np.array(B)
B_chip_code[np.isclose(B_chip_code, 0)] = -1
print(B_chip_code)
```

    0 1 1 0 0 1 1 0
    [-1  1  1 -1 -1  1  1 -1]
    


```python
As=[x*Bipolar_Ad for x in A_chip_code]
print(As)
```

    [-1, -1, 1, 1, -1, -1, 1, 1]
    


```python
Bs=[x*Bipolar_Bd for x in B_chip_code]
print(Bs)
```

    [1, -1, -1, 1, 1, -1, -1, 1]
    


```python
from operator import add 
Cs = list(map(add, As, Bs)) 
print(Cs)
```

    [0, -2, 0, 2, 0, -2, 0, 2]
    


```python
from operator import mul 
AF= list(map(mul,Cs,A_chip_code))
print(AF)
sum_A=sum(AF)
print(sum_A)
if sum_A > 0:
    A_transmitted=1
else:
    A_transmitted=0
print(A_transmitted)
```

    [0, 2, 0, 2, 0, 2, 0, 2]
    8
    1
    


```python
from operator import mul 
BF= list(map(mul,Cs,B_chip_code))
print(BF)
sum_B=sum(BF)
print(sum_B)
if sum_B > 0:
    B_transmitted=1
else:
    B_transmitted=0
print(B_transmitted)
```

    [0, -2, 0, -2, 0, -2, 0, -2]
    -8
    0
    


```python

```
