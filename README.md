# Pandas-and-NumPy

## NumPy is a Python package. It stands for 'Numerical Python'. It is a library consisting of multidimensional array objects and a collection of routines for processing of array.
* The most important object defined in NumPy is an N-dimensional array type called ndarray. It describes the collection of items of the same type. Items in the collection can be accessed using a zero-based index.
* Every item in an ndarray takes the same size of block in the memory. Each element in ndarray is an object of data-type object also called as dtype.

## **Why Numpy**
Numpy data structures perform better in:
* Memory - Numpy data structures take up less space
* Performance - they have a need for speed and are faster than lists
* Functionality - SciPy and NumPy have optimized functions such as linear algebra operations built in.
## **Numpy Attributes**
* ndarray.shape -- This returns a tuple consisting of array dimensions and can be used to resize the array.
* ndarray.ndim -- This returns the number of array dimensions.
* ndarray.size -- This returns the total number of elements in the array.
* ndarray.dtype -- This returns the data type of the array.
* ndarray.astype -- This changes the data type of an array.
-------------------------------------------------------------------------------------------------------------------------------------------
#### **Array from numerical ranges :**

*np.arange(x)* -- is used to create a range of n values -->  Parameters for the function : np.arange(start, stop, step, dtype)

#### **Array from random numbers :** 

*np.random.random((x,y))* -- to get an array with random input elements of desired shape --> Parameters for the function : np.full(shape)

#### **Creating ndarray with existing data**
* List to Ndarray -- *np.asarray(list)* -------> list = [1,2,3] \n array = np.asarray(list) 
* Tuple to Ndarray -- *np.asarray(tuple)* -------> tuple = (1,2,3) \n array = np.asarray(tuple)

## Indexing and Slicing Arrays
Contents of ndarray object can be accessed and modified by indexing or slicing.

Slicing means retrieving elements from one index to another index. We have to pass the starting and ending point in the index. Slicing includes the starting index but excludes the ending index.

---------**1-D array slicing**-----------

a = np.arange(10)

a[5]

----------**2-D array slicing**-------------

a = np.array([[1,2,3],[4,5,6]])

print(a[1,2])

-----------**Slicing 3-D Arrays**------------

a = np.array([[[1,2],[3,4],[5,6]],
             [[7,8],[9,10],[11,12]],
             [[13,14],[15,16],[17,18]]])

print(a[0:2,1:,1:])



## **Array Manipulation**
* np.transpose(array) - To transpose array
* np.reshape(array,shape) - To Change shape of an array
* np.resize(array,shape) - To return new array with shape
* np.flatten(array) - To flatten the array
* np.insert(arr, obj, values, axis) - To Insert items to an array
* np.append(arr, values, axis) - To append items to an array
* np.delete(arr, obj, axis) - To delete items from an array
* np.unique(arr, return_index, return_inverse, return_counts) - To get unique items from an array

## **Basic Operations and Functions** 
* np.add() - Adding two arrays
* np.subtract() - Subtracting two arrays
* np.multiply() - Multiplying two arrays
* np.divide() - Dividing two arrays
* np.sum() - Sum of items in an array
* np.min() - Minimum of items in an array
* np.max() - Minimum of items in an array
* np.mean() - Mean of items in an array
* np.sort() - Sorting an array

## **Broadcasting**
**Broadcasting allows these types of binary operations to be performed on arrays of different sizes**

Broadcasting in NumPy follows a strict set of rules to determine the interaction between the two arrays:
* Rule 1: If the two arrays differ in their number of dimensions, the shape of the one with fewer dimensions is padded with ones on its leading (left) side.
* Rule 2: If the shape of the two arrays does not match in any dimension, the array with shape equal to 1 in that dimension is stretched to match the other shape.
* Rule 3: If in any dimension the sizes disagree and neither is equal to 1, an error is raised.
