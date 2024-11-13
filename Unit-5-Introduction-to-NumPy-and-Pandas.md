# Unit 5: Introduction to NumPy and Pandas

1. [Arrays: Creating a multidimensional array](#arrays-creating-a-multidimensional-array)
2. [NumPy numerical types – Data type objects, Character codes](#52-numpy-numerical-types--data-type-objects-character-codes)
3. [One-dimensional slicing and indexing](#53-one-dimensional-slicing-and-indexing)
4. [Manipulating array shapes: Stacking arrays, Splitting NumPy arrays](#54-manipulating-array-shapes-stacking-arrays-splitting-numpy-arrays)
5. [Creating array views and copies](#55-creating-array-views-and-copies)
6. [Indexing NumPy arrays with Booleans](#56-indexing-numpy-arrays-with-booleans)

## Arrays: Creating a multidimensional array

* NumPy arrays are efficient multi-dimensional arrays used for numerical and scientific computing.
* Creating Arrays:
    - Use np.array() for basic array creation.
    - Use specialized functions like np.zeros(), np.ones(), np.arange(), and np.eye() for different array structures.

``` python
import numpy as np

# Basic array
array = np.array([[0, 1, 2], [2, 3, 4]])
print(array)
# Output: [[0 1 2]
#          [2 3 4]]

array = np.arange(0, 10, 2)
# [0, 2, 4, 6, 8]

array = np.random.randint(0, 10, (3,3))
# [[6 4 3]
# [1 5 6]
# [9 8 5]]

# Zero array
zero_array = np.zeros((2, 3))
print(zero_array)
# Output: [[0. 0. 0.]
#          [0. 0. 0.]]

# Identity matrix
identity_matrix = np.eye(3)
print(identity_matrix)
# Output: [[1. 0. 0.]
#          [0. 1. 0.]
#          [0. 0. 1.]]
```

## 5.2 NumPy Numerical Types – Data Type Objects, Character Codes

### Data Types (Dtypes) in NumPy
- NumPy provides various dtypes like int8, float32, and complex64 to support precise memory management.
- Character Codes: Character shortcuts for data types include:
    - b for boolean, i for signed integer, f for floating-point, c for complex, and S for string.
- Creating Arrays with Specific Dtypes: Use the dtype parameter when defining an array.

```python
# Integer array with 32-bit signed integers
arr_int = np.array([1, 2, 3], dtype=np.int32)
print(arr_int.dtype)  # Output: int32

# Floating-point array with 16-bit precision
arr_float = np.array([1.0, 2.5, 3.8], dtype="float16")
print(arr_float)
# Output: [1.  2.5 3.8]

# Complex numbers
arr_complex = np.array([1, 2, 3], dtype="complex")
print(arr_complex)
# Output: [1.+0.j 2.+0.j 3.+0.j]
```

### Dtype Objects & Attributes
- Dtype Objects: Created using numpy.dtype, specifying types with character codes or type names.
- Attributes:
    - dtype.name: Name of the dtype.
    - dtype.type: Type of dtype (e.g., np.int32).
    - dtype.itemsize: Size of each element in bytes.

```python
arr = np.array([1, 2, 3], dtype=np.int32)
print(arr.dtype.name)     # Output: int32
print(arr.dtype.type)     # Output: <class 'numpy.int32'>
print(arr.dtype.itemsize) # Output: 4 (bytes for int32)
```

## 5.3 One-dimensional Slicing and Indexing

### Slicing and Indexing
- Indexing: Access elements using indices (arr[index]).
- Slicing: Access a range of elements with start:stop:step format.
- Example: arr[1:4] retrieves elements from index 1 to 3.

```python
arr = np.arange(10)  # Array: [0 1 2 3 4 5 6 7 8 9]

# Accessing elements
print(arr[5])       # Output: 5
print(arr[2:6])     # Output: [2 3 4 5]

# Assigning values with slicing
arr[5:8] = 12
print(arr)          # Output: [0 1 2 3 4 12 12 12 8 9]
```

## 5.4 Manipulating Array Shapes: Stacking Arrays, Splitting NumPy Arrays

### Array Shape Manipulation
- Reshape: Changes array shape without modifying data.
python

- Stacking Arrays
    - Vertical Stack: np.vstack((array1, array2)) stacks arrays vertically.
    - Horizontal Stack: np.hstack((array1, array2)) stacks arrays horizontally.
- Splitting Arrays
    - Splitting: Divides an array into sub-arrays using np.split(array, sections).

```python
reshaped_arr1 = arr1.reshape(2, 5)  # Reshapes arr1 to a 2x5 array

arr1 = np.array([1, 2])
arr2 = np.array([3, 4])

# Vertical and horizontal stacking
print(np.vstack((arr1, arr2)))
# Output: [[1 2]
#          [3 4]]

print(np.hstack((arr1, arr2)))
# Output: [1 2 3 4]

# Splitting
arr_split = np.array([1, 2, 3, 4, 5, 6])
print(np.split(arr_split, 3))
# Output: [array([1, 2]), array([3, 4]), array([5, 6])]
```

## 5.5 Creating Array Views and Copies

### Array Views
- View: A shallow copy of an array; changes to the view reflect in the original.

### Array Copies
- Copy: A deep copy; changes do not affect the original array

```python
original_array = np.array([10, 20, 30])

# Creating a view
view_array = original_array.view()
view_array[0] = 100
print(original_array)  # Output: [100 20 30]

# Creating a copy
copy_array = original_array.copy()
copy_array[1] = 200
print(original_array)  # Output: [100 20 30]
```

## 5.6 Indexing NumPy Arrays with Booleans

### Boolean Indexing
- Use boolean arrays as indices to filter elements based on conditions.
- Example Use Case: Filtering values that satisfy certain conditions.

```python
arr = np.array([10, 20, 30, 40, 50])

# Boolean indexing for values > 25
bool_index = arr > 25
print(bool_index)          # Output: [False False  True  True  True]

filtered_array = arr[bool_index]
print(filtered_array)       # Output: [30 40 50]
```

## Important Programs

```python
import numpy as np
 
# 1. Create numpy arrays using:
# Using arange
arr1 = np.arange(10)  # Creates an array with values from 0 to 9
print("Array using arange:\n", arr1)
 
# Using linspace
arr2 = np.linspace(0, 1, 5)  # Creates an array with 5 evenly spaced values between 0 and 1
print("\nArray using linspace:\n", arr2)
 
# Using a list
arr3 = np.array([1, 2, 3, 4, 5])  # Creates an array from a list
print("\nArray using a list:\n", arr3)
 
# 2. On created arrays, perform:
# Reshaping
reshaped_arr1 = arr1.reshape(2, 5)  # Reshapes arr1 to a 2x5 array
print("\nReshaped array:\n", reshaped_arr1)
 
# Indexing & Slicing
sliced_arr3 = arr3[1:4]  # Slices arr3 from index 1 to 3
print("\nSliced array:\n", sliced_arr3)
 
# Broadcasting
broadcasted_arr = arr3 + 10  # Adds 10 to each element in arr3
print("\nBroadcasted array:\n", broadcasted_arr)
 
# Mathematical operations
sum_arr1 = np.sum(arr1)  # Sums all elements in arr1
product_arr2 = np.prod(arr2)  # Calculates the product of all elements in arr2
print("\nSum of elements in arr1:", sum_arr1)
print("Product of elements in arr2:", product_arr2)
```
