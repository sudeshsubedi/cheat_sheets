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

- from functions zeros, ones, empty. zeros makes array of zeros, ones make array of 1 and empty makes array of random value. By default the type is float64 but can be changed explicitely.
```python
>>> a = np.zeros((2, 3))
>>> a
array([[0., 0., 0.],
	   [0., 0., 0.]])
>>> b = np.ones((3, 4), dtype='int64')
>>> b
array([[1, 1, 1, 1],
	   [1, 1, 1, 1],
	   [1, 1, 1, 1]])
>>> c = np.empty((2, 3))
array([[3.73603959e-262, 6.02658058e-154, 6.55490914e-260],
       [5.30498948e-313, 3.14673309e-307, 1.00000000e+000]])
```

- create sequence of numbers with arange function
```python
>>> a = np.arange(10, 30, 5) # (start, end, step)
>>> a
array([10, 15, 20, 25])
>>> b = np.arange(0, 2, 0.4)
>>> b
array([0., 0.4, 0.8, 1.2, 1.6])
```

- use linspace to create array with fixed numbers as it takes number of element as argument
```python
>>> a = linspace(0, 2, 9)
>>> a
array([0.  , 0.25, 0.5 , 0.75, 1.  , 1.25, 1.5 , 1.75, 2.  ])
>>> x = np.linspace(0, 2 * pi, 100)
>>> f = np.sin(x)
```


### Basic operations

- Arithmetic operations are applied elementwise.
```python
>>> a = np.arange(9).reshape(3, 3)
>>> a
array([[0, 1, 2],
	   [3, 4, 5],
	   [6, 7, 8]])
>>> a = a + 2
>>> a
array([[2, 3, 4],
	   [5, 6, 7],
	   [8, 9, 10]])
>>> b = np.array([10, 25, 45, 35])
>>> print(b > 35)
array([False, False, True, False])
```

- \* operator on matrix is elementwise multiplication. For matrix multiplication dot function is used.
```python
>>> A = np.array([[1, 1], [0, 1]])
>>> B = np.array([[2, 0], [3, 4]])
>>> print(A*B)
array([[2, 0],
	   [0, 4]])
>>> print(A.dot(B))
array([[5, 4],
	   [3, 4]])
```

- find the sum, minimum and maximum with methods like sum, min, max
```python
>>> A = np.array([[5, 15], [20, 10]])
>>> print(A.sum())
50
>>> print(A.min())
5
>>> print(A.max())
20
```

- use axis parameter to apply method to different dimentions
```python
>>> b = np.arange(15).reshape(3, 5)
>>> b
array([[0, 1, 2, 3, 4],
	   [5, 6, 7, 8, 9],
	   [10, 11, 12, 13, 14]])
>>> b.sum(axis=0) # sum of each column
array([15, 18, 21, 24, 27])
>>> b.min(axis=1) # min of each row
array([0, 5, 10])
>>> b.cumsum(axis=1) # cummulative sum of each row
array([[0, 1, 3, 6, 10],
	   [5, 11, 18, 26, 37],
	   [10, 21, 33, 46, 50]])
```

### Universal Functions
