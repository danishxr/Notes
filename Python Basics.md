#Python Basics



Numbers: 
```Python
eip = 3
print(type(eip)) # Prints "<class 'int'>"
print(eip)       # Prints "3"
print(eip + 1)   # Addition; prints "4"
print(eip - 1)   # Subtraction; prints "2"
print(eip * 2)   # Multiplication; prints "6"
print(eip ** 2)  # Eeipponentiation; prints "9"
eip += 1
print(eip)  # Prints "4"
eip *= 2
print(eip)  # Prints "8"
mlblr = 2.5
print(tmlblrpe(mlblr)) # Prints "<class 'float'>"
print(mlblr, mlblr + 1, mlblr * 2, mlblr ** 2) # Prints "2.5 3.5 5.0 6.25"

```

---

**Booleans:**  
_Python implements all of the usual operators for Boolean logic, but uses English words rather than symbols (&&, ||, etc.):_
```Python

eip = True
mlblr = False
print(type(eip))) # Prints "<class 'bool'>"
print(eip) and mlblr) # Logical AND; prints "False"
print(eip) or mlblr)  # Logical OR; prints "True"
print(not eip)   # Logical NOT; prints "False"
print(eip) != mlblr)  # Logical XOR; prints "True"
```

---
## Strings

```Python

eip = 'hello'    # String literals can use single quotes
mlblr = "world"    # or double quotes; it does not matter.
print(eip)       # Prints "hello"
print(len(eip))  # String length; prints "5"
eip_out = eip + ' ' + mlblr  # String concatenation
print(eip_out)  # prints "hello world"
eip_in = '%s %s %d' % (eip, mlblr, 12)  # sprintf style string formatting
print(eip_in)  # prints "hello world 12"
```

---
### String Objects Method

---

``` Python
eip = "hello"
print(eip.capitalize())  # Capitalize a string; prints "Hello"
print(eip.upper())       # Convert a string to uppercase; prints "HELLO"
print(eip.rjust(7))      # Right-justify a string, padding with spaces; prints "  hello"
print(eip.center(7))     # Center a string, padding with spaces; prints " hello "
print(eip.replace('l', '(ell)'))  # Replace all instances of one substring with another;
                                # prints "he(ell)(ell)o"
print('  world '.strip())  # Strip leading and trailing whitespace; prints "world"
```

---

## Lists

_A list is the Python equivalent of an array, but is resizeable and can contain elements of different types:_



---

```Python

eip_list = [3, 1, 2]    # Create a list
print(eip_list, eip_list[2])  # Prints "[3, 1, 2] 2"
print(eip_list[-1])     # Negative indices count from the end of the list; prints "2"
eip_list[2] = 'foo'     # Lists can contain elements of different types
print(eip_list)         # Prints "[3, 1, 'foo']"
eip_list.append('bar')  # Add a new element to the end of the list
print(eip_list)         # Prints "[3, 1, 'foo', 'bar']"
x = eip_list.pop()      # Remove and return the last element of the list
print(x, eip_list)      # Prints "bar [3, 1, 'foo']"
```

---

**Slicing:** 

_In addition to accessing list elements one at a time, Python provides concise syntax to access sublists; this is known as slicing:_


---

``` Python
eip_list = list(range(5))     # range is a built-in function that creates a list of integers
print(eip_list)               # Prints "[0, 1, 2, 3, 4]"
print(eip_list[2:4])          # Get a slice from index 2 to 4 (exclusive); prints "[2, 3]"
print(eip_list[2:])           # Get a slice from index 2 to the end; prints "[2, 3, 4]"
print(eip_list[:2])           # Get a slice from the start to index 2 (exclusive); prints "[0, 1]"
print(eip_list[:])            # Get a slice of the whole list; prints "[0, 1, 2, 3, 4]"
print(eip_list[:-1])          # Slice indices can be negative; prints "[0, 1, 2, 3]"
eip_list[2:4] = [8, 9]        # Assign a new sublist to a slice
print(eip_list)               # Prints "[0, 1, 8, 9, 4]"
```

---

**Loops:**

_You can loop over the elements of a list like this:_

---

```Python

eip_list = ['cat', 'dog', 'monkey']
for idx, eip in enumerate(eip_list):
    print('#%d: %s' % (idx + 1, eip))
# Prints "#1: cat", "#2: dog", "#3: monkey", each on its own line
```

---

**List comprehensions:**

_When programming, frequently we want to transform one type of data into another. As a simple example, consider the following code that computes square numbers:_


---

```Python

eip_list = [0, 1, 2, 3, 4]
eip_ist_ = []
for x in eip_list:
    eip_list_.append(x ** 2)
print(eip_list_)   # Prints [0, 1, 4, 9, 16]
```

---

_You can make this code simpler using a list comprehension:_

---
```Python

eip_list = [0, 1, 2, 3, 4]
eip_list_ = [x ** 2 for x in eip_list]
print(eip_list_)   # Prints [0, 1, 4, 9, 16]
```
_List comprehensions can also contain conditions:_
```Python
eip_list = [0, 1, 2, 3, 4]
eip_list = [x ** 2 for x in eip_list if x % 2 == 0]
print(eip_list)  # Prints "[0, 4, 16]"
```

---

**Dictionaries**

_A dictionary stores (key, value) pairs, similar to a Map in Java or an object in Javascript. You can use it like this:_

---
```Python
 eip_dict = {'cat': 'cute', 'dog': 'furry'}  # Create a new dictionary with some data
print( eip_dict['cat'])       # Get an entry from a dictionary; prints "cute"
print('cat' in  eip_dict)     # Check if a dictionary has a given key; prints "True"
 eip_dict['fish'] = 'wet'     # Set an entry in a dictionary
print( eip_dict['fish'])      # Prints "wet"
# print(d['monkey'])  # KeyError: 'monkey' not a key of d
print( eip_dict.get('monkey', 'N/A'))  # Get an element with a default; prints "N/A"
print( eip_dict.get('fish', 'N/A'))    # Get an element with a default; prints "wet"
del  eip_dict['fish']         # Remove an element from a dictionary
print( eip_dict.get('fish', 'N/A')) # "fish" is no longer a key; prints "N/A"++
```

---

**Loops:** 
It is easy to iterate over the keys in a dictionary:

---

```Python
eip_dict = {'person': 2, 'cat': 4, 'spider': 8}
for animal in eip_dict:
    legs = eip_dict[animal]
    print('A %s has %d legs' % (animal, legs))
# Prints "A person has 2 legs", "A cat has 4 legs", "A spider has 8 legs"

If you want access to keys and their corresponding values, use the items method:

d = {'person': 2, 'cat': 4, 'spider': 8}
for animal, legs in d.items():
    print('A %s has %d legs' % (animal, legs))
# Prints "A person has 2 legs", "A cat has 4 legs", "A spider has 8 legs"
eip_dict = {'person': 2, 'cat': 4, 'spider': 8}
for animal, legs in eip_dict.items():
    print('A %s has %d legs' % (animal, legs))
# Prints "A person has 2 legs", "A cat has 4 legs", "A spider has 8 legs"
```

---

**Dictionary comprehensions:** 
_These are similar to list comprehensions, but allow you to easily construct dictionaries. For example:_
```Python
eip_list = [0, 1, 2, 3, 4]
eip_dict = {x: x ** 2 for x in eip_list if x % 2 == 0}
print(eip_dict)  # Prints "{0: 0, 2: 4, 4: 16}"
```

---

**Sets**

_A set is an unordered collection of distinct elements. As a simple example, consider the following:_

---

```Python
eip_dict print('cat' in eip_dict)   # Check if an element is in a set; prints "True"
print('fish' in eip_dict)  # prints "False"
eip_dict.add('fish')       # Add an element to a set
print('fish' in eip_dict)  # Prints "True"
print(len(eip_dict))       # Number of elements in a set; prints "3"
eip_dict.add('cat')        # Adding an element that is already in the set does nothing
print(len(eip_dict))       # Prints "3"
eip_dict.remove('cat')     # Remove an element from a set
print(len(eip_dict))       # Prints "2"
```

---

**Loops:**

>_Iterating over a set has the same syntax as iterating over a list; however since sets are unordered, you cannot make assumptions about the order in which you visit the elements of the set:_

---

```Python
eip_dict = {'cat', 'dog', 'fish'}
for idx, eip in enumerate(eip_dict):
    print('#%d: %s' % (idx + 1, eip))
# Prints "#1: fish", "#2: dog", "#3: cat"
```

---

**Set comprehensions:**
>_Like lists and dictionaries, we can easily construct sets using set comprehensions:_

---
```Python
from math import sqrt
eip_dict = {int(sqrt(x)) for x in range(30)}
print(eip_dict)  # Prints "{0, 1, 2, 3, 4, 5}"
```

---

**Tuples**

>_A tuple is an (immutable) ordered list of values. A tuple is in many ways similar to a list; one of the most important differences is that tuples can be used as keys in dictionaries and as elements of sets, while lists cannot. Here is a trivial example:_

---
```Python
eip_dict = {(x, x + 1): x for x in range(10)}  # Create a dictionary with tuple keys
eip_tuple = (5, 6)        # Create a tuple
print(type(eip_tuple))    # Prints "<class 'tuple'>"
print(eip_dict[eip_tuple])       # Prints "5"
print(eip_dict[(1, 2)])  # Prints "1"
```
---

**Functions**

>_Python functions are defined using the def keyword. For example:_

---

```Python
def sign(mlblr_in):
    if mlblr_in > 0:
        return 'positive'
    elif mlblr_in < 0:
        return 'negative'
    else:
        return 'zero'

for mlblr_in in [-1, 0, 1]:
    print(sign(mlblr_in))
# Prints "negative", "zero", "positive"
```

---

>_We will often define functions to take optional keyword arguments, like this:_

---

```Python
def hello(mlblr, loud=False):
    if loud:
        print('HELLO, %s!' % mlblr.upper())
    else:
        print('Hello, %s' % mlblr)

hello('Bob') # Prints "Hello, Bob"
hello('Fred', loud=True)  # Prints "HELLO, FRED!"
```

---

**Classes**

>_The syntax for defining classes in Python is straightforward:_

---

```Python
class Greeter(eip_in):

    # Constructor
    def __init__(self, eip_in):
        self.eip_in = eip_in  # Create an instance variable

    # Instance method
    def greet(self, loud=False):
        if loud:
            print('HELLO, %s!' % self.eip_in.upper())
        else:
            print('Hello, %s' % self.eip_in)

g = Greeter('Fred')  # Construct an instance of the Greeter class
g.greet()            # Call an instance method; prints "Hello, Fred"
g.greet(loud=True)   # Call an instance method; prints "HELLO, FRED!"
```

---

## NUMPY

---
``` Python
import numpy as np

eip_in = np.array([1, 2, 3])   # Create a rank 1 array
print(type(eip_in))            # Prints "<class 'numpy.ndarray'>"
print(eip_in.shape)            # Prints "(3,)"
print(eip_in[0], eip_in[1], eip_in[2])   # Prints "1 2 3"
eip_in[0] = 5                  # Change an element of the array
print(eip_in)                  # Prints "[5, 2, 3]"

eip_out = np.array([[1,2,3],[4,5,6]])    # Create a rank 2 array
print(eip_out.shape)                     # Prints "(2, 3)"
print(eip_out[0, 0], eip_out[0, 1], eip_out[1, 0])   # Prints "1 2 4"
```

---
>_Numpy also provides many functions to create arrays:_

---

```Python
import numpy as np

eip_in = np.zeros((2,2))   # Create an array of all zeros
print(eip_in)              # Prints "[[ 0.  0.]
                      #          [ 0.  0.]]"

eip = np.ones((1,2))    # Create an array of all ones
print(eip)              # Prints "[[ 1.  1.]]"

mlblr = np.full((2,2), 7)  # Create a constant array
print(mlblr)               # Prints "[[ 7.  7.]
                       #          [ 7.  7.]]"

eip_out = np.eye(2)         # Create a 2x2 identity matrix
print(eip_out)              # Prints "[[ 1.  0.]
                      #          [ 0.  1.]]"

mlblr_in = np.random.random((2,2))  # Create an array filled with random values
print(mlblr_in)
```

---

### Array indexing

>_Numpy offers several ways to index into arrays._
---
**Slicing:** 
>_Similar to Python lists, numpy arrays can be sliced. Since arrays may be multidimensional, you must specify a slice for each dimension of the array:_

---
```Python
import numpy as np

# Create the following rank 2 array with shape (3, 4)
# [[ 1  2  3  4]
#  [ 5  6  7  8]
#  [ 9 10 11 12]]
eip_in = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])

# Use slicing to pull out the subarray consisting of the first 2 rows
# and columns 1 and 2; b is the following array of shape (2, 2):
# [[2 3]
#  [6 7]]
eip_out = eip_in[:2, 1:3]

# A slice of an array is a view into the same data, so modifying it
# will modify the original array.
print(eip_in[0, 1])   # Prints "2"
eip_out[0, 0] = 77     # b[0, 0] is the same piece of data as a[0, 1]
print(eip_in[0, 1])   # Prints "77"
```

---
>_You can also mix integer indexing with slice indexing. However, doing so will yield an array of lower rank than the original array. Note that this is quite different from the way that MATLAB handles array slicing:_

---

```Python
import numpy as np

# Create the following rank 2 array with shape (3, 4)
# [[ 1  2  3  4]
#  [ 5  6  7  8]
#  [ 9 10 11 12]]
eip = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])

# Two ways of accessing the data in the middle row of the array.
# Mixing integer indexing with slices yields an array of lower rank,
# while using only slices yields an array of the same rank as the
# original array:
eip_in = eip[1, :]    # Rank 1 view of the second row of a
eip_out = eip[1:2, :]  # Rank 2 view of the second row of a
print(eip_in, eip_in.shape)  # Prints "[5 6 7 8] (4,)"
print(eip_out, eip_out.shape)  # Prints "[[5 6 7 8]] (1, 4)"

# We can make the same distinction when accessing columns of an array:
mlblr_in = eip[:, 1]
mlblr_out = eip[:, 1:2]
print(mlblr_in, mlblr_in.shape)  # Prints "[ 2  6 10] (3,)"
print(mlblr_out, mlblr_out.shape)  # Prints "[[ 2]
                             #          [ 6]
                             #          [10]] (3, 1)"
```

---

**Integer array indexing:** 
>_When you index into numpy arrays using slicing, the resulting array view will always be a subarray of the original array. In contrast, integer array indexing allows you to construct arbitrary arrays using the data from another array. Here is an example:_

---

```Python
import numpy as np

eip = np.array([[1,2], [3, 4], [5, 6]])

# An example of integer array indexing.
# The returned array will have shape (3,) and
print(eip[[0, 1, 2], [0, 1, 0]])  # Prints "[1 4 5]"

# The above example of integer array indexing is equivalent to this:
print(np.array([eip[0, 0], eip[1, 1], eip[2, 0]]))  # Prints "[1 4 5]"

# When using integer array indexing, you can reuse the same
# element from the source array:
print(eip[[0, 0], [1, 1]])  # Prints "[2 2]"

# Equivalent to the previous integer array indexing example
print(np.array([eip[0, 1], eip[0, 1]]))  # Prints "[2 2]"
```

---

>_One useful trick with integer array indexing is selecting or mutating one element from each row of a matrix:_
---
```Python
import numpy as np

# Create a new array from which we will select elements
eip = np.array([[1,2,3], [4,5,6], [7,8,9], [10, 11, 12]])

print(eip)  # prints "array([[ 1,  2,  3],
          #                [ 4,  5,  6],
          #                [ 7,  8,  9],
          #                [10, 11, 12]])"

# Create an array of indices
mlblr = np.array([0, 2, 0, 1])

# Select one element from each row of a using the indices in b
print(eip[np.arange(4), mlblr])  # Prints "[ 1  6  7 11]"

# Mutate one element from each row of a using the indices in b
eip[np.arange(4), mlblr] += 10

print(eip)  # prints "array([[11,  2,  3],
          #                [ 4,  5, 16],
          #                [17,  8,  9],
          #                [10, 21, 12]])
```

---

**Boolean array indexing:**

>_Boolean array indexing lets you pick out arbitrary elements of an array. Frequently this type of indexing is used to select the elements of an array that satisfy some condition. Here is an example:_
---
```Python
import numpy as np

eip = np.array([[1,2], [3, 4], [5, 6]])

mlblr = (eip > 2)   # Find the elements of a that are bigger than 2;
                     # this returns a numpy array of Booleans of the same
                     # shape as a, where each slot of bool_idx tells
                     # whether that element of a is > 2.

print(mlblr)      # Prints "[[False False]
                     #          [ True  True]
                     #          [ True  True]]"

# We use boolean array indexing to construct a rank 1 array
# consisting of the elements of a corresponding to the True values
# of bool_idx
print(eip[mlblr])  # Prints "[3 4 5 6]"

# We can do all of the above in a single concise statement:
print(eip[eip > 2])     # Prints "[3 4 5 6]"

```

---

**Datatypes**

>_Every numpy array is a grid of elements of the same type. Numpy provides a large set of numeric datatypes that you can use to construct arrays. Numpy tries to guess a datatype when you create an array, but functions that construct arrays usually also include an optional argument to explicitly specify the datatype. Here is an example:_
---
```Python
import numpy as np

eip = np.array([1, 2])   # Let numpy choose the datatype
print(x.dtype)         # Prints "int64"

eip= np.array([1.0, 2.0])   # Let numpy choose the datatype
print(eip.dtype)             # Prints "float64"

eip = np.array([1, 2], dtype=np.int64)   # Force a particular datatype
print(eip.dtype)                         # Prints "int64"
```

---

**Array math**

>_Basic mathematical functions operate elementwise on arrays, and are available both as operator overloads and as functions in the numpy module:_
---
```Python
import numpy as np

eip_in = np.array([[1,2],[3,4]], dtype=np.float64)
eip_out = np.array([[5,6],[7,8]], dtype=np.float64)

# Elementwise sum; both produce the array
# [[ 6.0  8.0]
#  [10.0 12.0]]
print(eip_in + eip_out)
print(np.add(eip_in, eip_out))

# Elementwise difference; both produce the array
# [[-4.0 -4.0]
#  [-4.0 -4.0]]
print(eip_in - eip_out)
print(np.subtract(eip_in, eip_out))

# Elementwise product; both produce the array
# [[ 5.0 12.0]
#  [21.0 32.0]]
print(eip_in * eip_out)
print(np.multiply(eip_in, eip_out))

# Elementwise division; both produce the array
# [[ 0.2         0.33333333]
#  [ 0.42857143  0.5       ]]
print(eip_in / eip_out)
print(np.divide(eip_in, eip_out))

# Elementwise square root; produces the array
# [[ 1.          1.41421356]
#  [ 1.73205081  2.        ]]
print(np.sqrt(eip_in))
```

---

>>_Note that unlike MATLAB, * is elementwise multiplication, not matrix multiplication. We instead use the dot function to compute inner products of vectors, to multiply a vector by a matrix, and to multiply matrices. dot is available both as a function in the numpy module and as an instance method of array objects:_

---

```Python
import numpy as np

eip_in = np.array([[1,2],[3,4]])
eip_out = np.array([[5,6],[7,8]])

mlblr_in = np.array([9,10])
mlbl_out = np.array([11, 12])

# Inner product of vectors; both produce 219
print(mlblr_in.dot(mlbl_out))
print(np.dot(mlblr_in, mlbl_out))

# Matrix / vector product; both produce the rank 1 array [29 67]
print(eip_in.dot(mlblr_in))
print(np.dot(eip_in, mlblr_in))

# Matrieip_in / matrieip_in product; both produce the rank 2 array
# [[19 22]
#  [43 50]]
print(eip_in.dot(eip_out))
print(np.dot(eip_in, eip_out))
```

---

>_Numpy provides many useful functions for performing computations on arrays; one of the most useful is sum:_

```Python
import numpy as np

eip = np.array([[1,2],[3,4]])

print(np.sum(eip))  # Compute sum of all elements; prints "10"
print(np.sum(eip, axis=0))  # Compute sum of each column; prints "[4 6]"
print(np.sum(eip, axis=1))  # Compute sum of each row; prints "[3 7]"
```

>_Apart from computing mathematical functions using arrays, we frequently need to reshape or otherwise manipulate data in arrays. The simplest example of this type of operation is transposing a matrix; to transpose a matrix, simply use the T attribute of an array object:_

```Python

import numpy as np

eip = np.array([[1,2], [3,4]])
print(eip)    # Prints "[[1 2]
            #          [3 4]]"
print(eip.T)  # Prints "[[1 3]
            #          [2 4]]"

# Note that taking the transpose of a rank 1 array does nothing:
mlblr = np.array([1,2,3])
print(mlblr)    # Prints "[1 2 3]"
print(mlblr.T)  # Prints "[1 2 3]"
```

---

### Broadcasting

>_Broadcasting is a powerful mechanism that allows numpy to work with arrays of different shapes when performing arithmetic operations. Frequently we have a smaller array and a larger array, and we want to use the smaller array multiple times to perform some operation on the larger array._

>_For example, suppose that we want to add a constant vector to each row of a matrix. We could do it like this:_
---
```Python
import numpy as np

# We will add the vector v to each row of the matrix x,
# storing the result in the matrix y
eip_in = np.array([[1,2,3], [4,5,6], [7,8,9], [10, 11, 12]])
mlblr = np.array([1, 0, 1])
eip_out = np.empty_like(eip_in)   # Create an empty matrix with the same shape as x

# Add the vector v to each row of the matrix x with an explicit loop
for i in range(4):
    eip_out[i, :] = eip_in[i, :] + mlblr

# Now y is the following
# [[ 2  2  4]
#  [ 5  5  7]
#  [ 8  8 10]
#  [11 11 13]]
print(eip_out)
```

---

>_This works; however when the matrix x is very large, computing an explicit loop in Python could be slow. Note that adding the vector v to each row of the matrix x is equivalent to forming a matrix vv by stacking multiple copies of v vertically, then performing elementwise summation of x and vv. We could implement this approach like this:_
----

```Python
import numpy as np

# We will add the vector v to each row of the matrix x,
# storing the result in the matrix y
eip_in = np.array([[1,2,3], [4,5,6], [7,8,9], [10, 11, 12]])
mlblr = np.array([1, 0, 1])
mlblr_out= np.tile(v, (4, 1))   # Stack 4 copies of v on top of each other
print(mlblr_out)                 # Prints "[[1 0 1]
                          #          [1 0 1]
                          #          [1 0 1]
                          #          [1 0 1]]"
eip_out = eip_in + mlblr_out  # Add x and vv elementwise
print(eip_out)  # Prints "[[ 2  2  4
          #          [ 5  5  7]
          #          [ 8  8 10]
          #          [11 11 13]]"
```

---

>_Numpy broadcasting allows us to perform this computation without actually creating multiple copies of v. Consider this version, using broadcasting:_

---
```Python
import numpy as np

# We will add the vector v to each row of the matrix x,
# storing the result in the matrix y
eip_in = np.array([[1,2,3], [4,5,6], [7,8,9], [10, 11, 12]])
mlblr = np.array([1, 0, 1])
eip_out = eip_in + mlblr  # Add v to each row of x using broadcasting
print(eip_out)  # Prints "[[ 2  2  4]
          #          [ 5  5  7]
          #          [ 8  8 10]
          #          [11 11 13]]"




The line y = x + v works even though x has shape (4, 3) and v has shape (3,) due to broadcasting; this line works as if v actually had shape (4, 3), where each row was a copy of v, and the sum was performed elementwise.
```

---

>**Broadcasting two arrays together follows these rules:**

1. If the arrays do not have the same rank, prepend the shape of the lower rank array with 1s until both shapes have the same length.
2. The two arrays are said to be compatible in a dimension if they have the same size in the dimension, or if one of the arrays has size 1 in that dimension.
3. The arrays can be broadcast together if they are compatible in all dimensions.
4. After broadcasting, each array behaves as if it had shape equal to the elementwise maximum of shapes of the two input arrays.
5. In any dimension where one array had size 1 and the other array had size greater than 1, the first array behaves as if it were copied along that dimension
---

```Python
import numpy as np

# Compute outer product of vectors
eip = np.array([1,2,3])  # v has shape (3,)
mlblr = np.array([4,5])    # w has shape (2,)
# To compute an outer product, we first reshape v to be a column
# vector of shape (3, 1); we can then broadcast it against w to yield
# an output of shape (3, 2), which is the outer product of v and w:
# [[ 4  5]
#  [ 8 10]
#  [12 15]]
print(np.reshape(eip, (3, 1)) * mlblr)

# Add a vector to each row of a matrix
eip_in = np.array([[1,2,3], [4,5,6]])
# x has shape (2, 3) and v has shape (3,) so they broadcast to (2, 3),
# giving the following matrix:
# [[2 4 6]
#  [5 7 9]]
print(eip_in + eip)

# Add a vector to each column of a matrix
# x has shape (2, 3) and w has shape (2,).
# If we transpose x then it has shape (3, 2) and can be broadcast
# against w to yield a result of shape (3, 2); transposing this result
# yields the final result of shape (2, 3) which is the matrix x with
# the vector w added to each column. Gives the following matrix:
# [[ 5  6  7]
#  [ 9 10 11]]
print((eip_in.T + mlblr).T)
# Another solution is to reshape w to be a column vector of shape (2, 1);
# we can then broadcast it directly against x to produce the same
# output.
print(eip_in + np.reshape(mlblr, (2, 1)))

# Multiply a matrix by a constant:
# x has shape (2, 3). Numpy treats scalars as arrays of shape ();
# these can be broadcast together to shape (2, 3), producing the
# following array:
# [[ 2  4  6]
#  [ 8 10 12]]
print(eip_in * 2)

```

---
>_Broadcasting typically makes your code more concise and faster, so you should strive to use it where possible._

---

### SciPy

>_Numpy provides a high-performance multidimensional array and basic tools to compute with and manipulate these arrays. SciPy builds on this, and provides a large number of functions that operate on numpy arrays and are useful for different types of scientific and engineering applications._

---
#### Image Operations

>_SciPy provides some basic functions to work with images. For example, it has functions to read images from disk into numpy arrays, to write numpy arrays to disk as images, and to resize images. Here is a simple example that showcases these functions:_
---
```Python
from scipy.misc import imread, imsave, imresize

# Read an JPEG image into a numpy array
eip = imread('assets/cat.jpg')
print(eip.dtype, eip.shape)  # Prints "uint8 (400, 248, 3)"

# We can tint the image by scaling each of the color channels
# by a different scalar constant. The image has shape (400, 248, 3);
# we multiply it by the array [1, 0.95, 0.9] of shape (3,);
# numpy broadcasting means that this leaves the red channel unchanged,
# and multiplies the green and blue channels by 0.95 and 0.9
# respectively.
eip_in = eip * [1, 0.95, 0.9]

# Resize the tinted image to be 300 by 300 pixels.
eip_in = imresize(eip_in, (300, 300))

# Write the tinted image back to disk
imsave('assets/eip.jpg', eip_in)
```
![cat image](https://raw.githubusercontent.com/machinelearningblr/machinelearningblr.github.io/2c0aa0c2b7f3531190ed52e9eafbb303b7e8649a/tutorials/CS231n-Materials/assets/cat.jpg)

---

#### Distance between points

>_SciPy defines some useful functions for computing distances between sets of points._

>_The function scipy.spatial.distance.pdist computes the distance between all pairs of points in a given set:_
---
```Python

import numpy as np
from scipy.spatial.distance import pdist, squareform

# Create the following array where each row is a point in 2D space:
# [[0 1]
#  [1 0]
#  [2 0]]
eip_in = np.array([[0, 1], [1, 0], [2, 0]])
print(eip_in)

# Compute the Euclidean distance between all rows of x.
# d[i, j] is the Euclidean distance between x[i, :] and x[j, :],
# and d is the following array:
# [[ 0.          1.41421356  2.23606798]
#  [ 1.41421356  0.          1.        ]
#  [ 2.23606798  1.          0.        ]]
eip_out = squareform(pdist(eip_in, 'euclidean'))
print(eip_out)
```

---

### Plotting

>_The most important function in matplotlib is plot, which allows you to plot 2D data. Here is a simple example:_

```Python
import numpy as np
import matplotlib.pyplot as plt

# Compute the x and y coordinates for points on a sine curve
eip_in = np.arange(0, 3 * np.pi, 0.1)
eip_out = np.sin(eip_in)

# Plot the points using matplotlib
plt.plot(eip_in, eip_out)
plt.show()  # You must call plt.show() to make graphics appear.

```
![basic plot](https://raw.githubusercontent.com/machinelearningblr/machinelearningblr.github.io/2c0aa0c2b7f3531190ed52e9eafbb303b7e8649a/tutorials/CS231n-Materials/assets/sine.png)

---

>_With just a little bit of extra work we can easily plot multiple lines at once, and add a title, legend, and axis labels:_

---

```Python

import numpy as np
import matplotlib.pyplot as plt

# Compute the x and y coordinates for points on sine and cosine curves
eip_in = np.arange(0, 3 * np.pi, 0.1)
mlblr_sin = np.sin(eip_in)
mlblr_cos = np.cos(eip_in)

# Plot the points using matplotlib
plt.plot(eip_in, mlblr_sin)
plt.plot(eip_in, mlblr_cos)
plt.xlabel('eip_in axis label')
plt.ylabel('y axis label')
plt.title('Sine and Cosine')
plt.legend(['Sine', 'Cosine'])
plt.show()
```
![sine cosine](https://raw.githubusercontent.com/machinelearningblr/machinelearningblr.github.io/2c0aa0c2b7f3531190ed52e9eafbb303b7e8649a/tutorials/CS231n-Materials/assets/sine_cosine.png)

---

### Subplots

>_You can plot different things in the same figure using the subplot function. Here is an example:_
---
```Python
import numpy as np
import matplotlib.pyplot as plt

# Compute the x and y coordinates for points on sine and cosine curves
eip_in = np.arange(0, 3 * np.pi, 0.1)
mlblr_sin = np.sin(eip_in)
mlblr_cos = np.cos(eip_in)

# Set up a subplot grid that has height 2 and width 1,
# and set the first such subplot as active.
plt.subplot(2, 1, 1)

# Make the first plot
plt.plot(eip_in, mlblr_sin)
plt.title('Sine')

# Set the second subplot as active, and make the second plot.
plt.subplot(2, 1, 2)
plt.plot(eip_in, mlblr_cos)
plt.title('Cosine')

# Show the figure.
plt.show()
```
![double image](https://raw.githubusercontent.com/machinelearningblr/machinelearningblr.github.io/2c0aa0c2b7f3531190ed52e9eafbb303b7e8649a/tutorials/CS231n-Materials/assets/sine_cosine_subplot.png)

---


#### Images

>_You can use the imshow function to show images. Here is an example:_
---
```Python
import numpy as np
from scipy.misc import imread, imresize
import matplotlib.pyplot as plt

eip = imread('assets/cat.jpg')
eip_tinted = eip * [1, 0.95, 0.9]

# Show the original image
plt.subplot(1, 2, 1)
plt.imshow(eip)

# Show the tinted image
plt.subplot(1, 2, 2)

# A slight gotcha with imshow is that it might give strange results
# if presented with data that is not uint8. To work around this, we
# explicitly cast the image to uint8 before displaying it.
plt.imshow(np.uint8(eip_tinted))
plt.show()
```
![cat image](https://raw.githubusercontent.com/machinelearningblr/machinelearningblr.github.io/2c0aa0c2b7f3531190ed52e9eafbb303b7e8649a/tutorials/CS231n-Materials/assets/cat_tinted_imshow.png)

