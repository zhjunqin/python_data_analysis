### Numpy中的矩阵相乘

> 参考:
>
> [http://blog.csdn.net/cqk0100/article/details/76221749](http://blog.csdn.net/cqk0100/article/details/76221749)

Numpy中的矩阵乘法分为两大情况，使用`numpy.array`和使用`numpy.matrix`. Numpy确实重载了`*`操作符，可以直接对array或者matrix对象进行乘法运算，但是在不同对象上，其意义是有区别的。

### numpy array {#对于array对象}

`*或np.multiply`[https://docs.scipy.org/doc/numpy/reference/generated/numpy.multiply.html](https://docs.scipy.org/doc/numpy/reference/generated/numpy.multiply.html)

代表的是矩阵或向量每个元素相乘。

```
import numpy as np
a=np.array([[1,2],[3,4]])
b=np.array([[4,3],[2,1]])

>>> a*b
array([[4, 6],
       [6, 4]])
>>> np.multiply(a,b)
array([[4, 6],
       [6, 4]])

a=np.array([1,2,3,4])
b=np.array([2,0,1,2])
>>> a*b
array([2, 0, 3, 8])
```

`np.dot`[https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html](https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html)

当两个变量都是矩阵时，表示的是矩阵相乘，

当两个变量都是向量时，表示的是向量内积，

当两个变量一个是向量，一个是矩阵时，表示的是矩阵向量相乘

```
a=np.array([[1,2],[3,4]])
b=np.array([[4,3,1],[2,1,0]])
>>> np.dot(a,b)
array([[ 8,  5,  1],
       [20, 13,  3]])

a=np.array([1,2,3,4])
b=np.array([2,0,1,2])
>>> np.dot(a,b)
13

a=np.array([[1,2],[3,4]])
b=np.array([3, 0]).T
>>> np.dot(a,b)
array([3, 9])
```

`np.inner`[https://docs.scipy.org/doc/numpy/reference/generated/numpy.inner.html](https://docs.scipy.org/doc/numpy/reference/generated/numpy.inner.html)

两个向量的内积

如果是向量和矩阵，则最后一维

```
a=np.array([1,2,3,4])
b=np.array([2,0,1,2])
>>> np.inner(a,b)
13

>>> a=np.array([[1,2],[3,4]])
>>> b=np.array([2,0])
>>> np.inner(a,b)
array([2, 6])
>>> np.inner(a.T,b)
array([2, 4])
>>> np.inner(a,b.T)
array([2, 6])
>>> np.inner(b,a)
array([2, 6])
>>> np.inner(b,a.T)
array([2, 4])
```

### numpy matrix {#对于array对象}

矩阵相乘是用`*`，矩阵每个元素相乘用`mutiply`

```
>>> a=np.mat([[1,2],[3,4]])
>>> type(a)
<class 'numpy.matrixlib.defmatrix.matrix'>
>>> b=np.mat([[4,3,1],[2,1,0]])
>>> a*b
matrix([[ 8,  5,  1],
        [20, 13,  3]])

>>> np.multiply(a,b)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: operands could not be broadcast together with shapes (2,2) (2,3) 

>>> b=np.array([[4,3],[2,1]])
>>> np.multiply(a,b)
matrix([[4, 6],
        [6, 4]])
        
>>> b=np.mat([[4,3],[2,1]])
>>> np.multiply(a,b)
matrix([[4, 6],
        [6, 4]])

```



