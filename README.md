# MATLABReshapeLikeNumpy
Reshape arrays row-wisely like python.

RESHAPE(A, new_size)
## Usage:
A is an array

new_size is an array represents the shape of the new n-dimensional matrix. [new_size_1, new_size_2, ..., new_size_n]
The shape have to be compatable.

It will return the reshaped array. Computation time is propotion to the dimensions of the array.

## Examples
In MATLAB
```
>> a = 1:6;
>> 
>> b = RESHAPE(a, [2,3])

b =

     1     2     3
     4     5     6

>> b = RESHAPE(a, [2,1,3])

b(:,:,1) =

     1
     4


b(:,:,2) =

     2
     5


b(:,:,3) =

     3
     6

>> b = RESHAPE(a, [2,3,1])

b =

     1     2     3
     4     5     6

>> a = RESHAPE(b, [1, 6])

a =

     1     2     3     4     5     6

>> 
```

The array reshapes like in matlab as it is in python, except the indices or matlab start with 1 while indices of python start with 0.
```
>>> import numpy as np
>>> a = np.linspace(1, 6, 6)
>>> b = a.reshape(2,3)
>>> b
array([[1., 2., 3.],
       [4., 5., 6.]])
>>> b = a.reshape(2,1,3)
>>> b
array([[[1., 2., 3.]],

       [[4., 5., 6.]]])
>>> b[:,:,1]
array([[2.],
       [5.]])
>>> b[:,:,0]
array([[1.],
       [4.]])
>>> b[:,:,2]
array([[3.],
       [6.]])
>>> b = a.reshape(2,3,1)
>>> b
array([[[1.],
        [2.],
        [3.]],

       [[4.],
        [5.],
        [6.]]])
>>> b[:,:,0]
array([[1., 2., 3.],
       [4., 5., 6.]])
>>> a = b.reshape(1, 6)
>>> a
array([[1., 2., 3., 4., 5., 6.]])

```
