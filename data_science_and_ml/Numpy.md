NumPy (**Numerical Python**) is an open source Python library used in fields of science and engineering. It’s the universal standard for working with numerical data in Python.

## The Basics
Numpy array class is called ndarray. Important attributes of ndarray are:

- ndarray.ndim := number of axes or dimention of array

- ndarray.shape := the dimention of array. Its a tuple of integers denoting size of array in each dimention.

- ndarray.size := total number of elements in array

- ndarray.dtype := object describing the type of element of array

- ndarray.itemsize := the size in byte of each element of array

- ndarray.data := the buffer containing the actual element of array

#### An Example
```python
>>> import numpy as np
>>> a = np.arange(15).reshape(3, 5)
>>> a
array([
	   [0, 1, 2, 3, 4],
	   [5, 6, 7, 8, 9],
	   [10, 11, 12, 13, 14]
])
>>> a.shape
(3, 5)
>>> a.ndim
2
>>> a.dtype.name
'int64'
>>> a.size
15
>>> type(a)
<class 'numpy.ndarray'>
```

### Array Creation
The are multiple ways to create numpy array.

- From regular python list:
```python
>>> import numpy as np
>>> a = np.array([1, 2, 3])
>>> a
array([1, 2, 3])
>>> a.dtype
dtype('int64')
>>> b = np.array([1.2, 3.4, 5.6])
>>> b
array([1.2, 3.4, 5.6])
>>> b.dtype
dtype('float64')
```

sequence of sequences >> two dimentional array
sequence of sequences of sequences >> 3 dimentional array and so on

```python
>>> c = np.array([(1, 2, 3), (4, 5, 6)])
>>> c
array([[1, 2, 3],
	   [4, 5, 6]])
```

type can be specified at creation time explicitely
```python
>>> d = np.array([[1, 2], [3, 4]], dtype=complex)
>>> d
array([[1.+0.j, 2.+0.j],
       [3.+0.j, 4.+0.j]])
```

