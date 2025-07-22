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

*np.random.random((x,y))* --> to get an array with random input elements of desired shape --> Parameters for the function : np.full(shape)

#### **Creating ndarray with existing data**
* List to Ndarray -- *np.asarray(list)*

         list = [1,2,3]
         array = np.asarray(list)
  
* Tuple to Ndarray -- *np.asarray(tuple)*

         tuple = (1,2,3)
          array = np.asarray(tuple)

## Indexing and Slicing Arrays
Contents of ndarray object can be accessed and modified by indexing or slicing.

Slicing means retrieving elements from one index to another index. We have to pass the starting and ending point in the index. Slicing includes the starting index but excludes the ending index.

**1-D array slicing**

       a = np.arange(10)
       a[5]

**2-D array slicing**

      a = np.array([[1,2,3],[4,5,6]])
          print(a[1,2])
          
        --> 6

**Slicing 3-D Arrays**

            a = np.array([[[1,2],[3,4],[5,6]],
                        [[7,8],[9,10],[11,12]],
                        [[13,14],[15,16],[17,18]]])

                print(a[0:2,1:,1:])
                
              --> 2 layers only, 2nd row values and 2 column values
              [[[ 4]
               [ 6]]
               [[10]
               [12]]]



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

------------------------------------------------------------------------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------------------------------------------------------------------------


## **PANDAS**

Pandas is a Python package providing fast, flexible, and expressive data structures designed to make working with structured (tabular, multidimensional, potentially heterogeneous) and time series data both easy and intuitive. It aims to be the fundamental high-level building block for doing practical, real world data analysis in Python.

**Few things that Pandas does well:**

* Robust I/O tools for loading data from flat files (CSV and delimited), Excel files, databases, and saving / loading data from the ultrafast HDF5 format
* Easy handling of missing data (represented as NaN) in floating point as well as non-floating point data
* Size mutability: Columns can be inserted and deleted from DataFrame and higher dimensional objects
* Automatic and explicit data alignment: objects can be explicitly aligned to a set of labels, or the user can simply ignore the labels and let Series, DataFrame, etc. automatically align the data for you in computations
* Powerful, flexible groupby functionality to perform split-apply-combine operations on data sets, for both aggregating and transforming data
* Make it easy to convert ragged, differently-indexed data in other Python and NumPy data structures into DataFrame objects
* Intelligent label-based slicing, fancy indexing, and subsetting of large data sets
* Intuitive merging and joining data sets
* Flexible reshaping and pivoting of data sets
* Hierarchical labeling of axes (possible to have multiple labels per tick)
* Time series-specific functionality: date range generation and frequency conversion, moving window statistics, moving window linear regressions, date shifting and lagging, etc.


**Pandas Cheatsheet: https://assets.datacamp.com/blog_assets/PandasPythonForDataScience.pdf**

**PANDAS DATAFRAMES**

There are two central concepts which you should know about for understanding pandas dataframes:
**Series** : A series is essentially a column
**Data Frame** : A DataFrame is a two-dimensional data structure, i.e., data is aligned in a tabular fashion in rows and columns. 
Pandas DataFrame consists of three principal components, the data, rows, and columns.


## **Methods and attributes in Pandas**

* pd.index - used to find the indices of the dataframe
* pd.head() - Prints the first n rows of the dataframe. By default it prints the first 5 rows.
* pd.tail() - Prints the last n rows of the dataframe. By default it prints the last 5 rows.
* pd.columns - Prints the list of columns in a dataframe.
* pd.info() - Prints the basic information about our dataframe.
* pd.rename() - Rename the columns of the dataframe.
* pd.shape() - Prints the rows and columns in the dataframe
* pd.describe() - This method gives the overall descriptive summary of the dataframe. This works only for numerical columns.

#### **Indexing and Slicing**

* *iloc* gets rows (or columns) at particular positions in the index (so it only takes integers)-----> index-based locating.

         Let us get a subset which consists of first 8 rows and first 4 columns
         df.iloc[:9,:4]
  
* *loc* gets rows (or columns) with particular labels from the index ------> label based locating.


          Let us subset our dataframe in which we want to have first 8 rows identified with their rows labels and some named columns
          df.loc[50:60,['budget','genres','runtime']]




**Creating another new column by subtracting/adding two existing columns**

    df['movie_profit'] = df['revenue'] - df['budget']

**Removing columns from the dataframe** 
  
    df.drop(['id'], axis = 1, inplace=True)

**Dropping multiple columns at once**

    df.drop(['half_runtime','poster_path'],axis=1,inplace=True)

## **Some Basic Operations in Pandas**

* df.columns - Prints all the columns in the dataset
* df.sum() - Finds the sum of values in a column.

        df['runtime'].sum()
  
* df.set_index() - Reset the index with our required input attribute

          # Replacing the index values with the id column
           df.set_index('id', inplace=True)
       
* df.unique() - Finds the list of unique values in a column

        list(df['original_language'].unique())
* df.nunique() - Counts the number of unique values in a column

        df.original_language.nunique()
* df.value_counts() - Gives the count of each category of a variable ---> df['languages'].value_counts(): will give the count of each language in the dataframe.

        df['original_language'].value_counts()
  
* df.isnull() - Returns a series of booleans if a column value contains nulls.
  
        df['homepage'].isnull()
  
* df.fillna() - Lets fill the missing values with a value.

        df['homepage'].fillna('Not Present',inplace = True)
  
* df.min() - finds the minimum value in a column
* df.max() - finds the maximum value in a column

         print(f" The shortest movie length is {df['runtime'].min()}")
         print(f" The largest movie length is {df['runtime'].max()}")
  
* df.apply() - applies a function to every row in dataframe.

      # Suppose we want to convert the column network to uppercase

         def to_uppercase(column):
           return column.upper()

         df['Capitalized_title'] = df['title'].apply(to_uppercase)

  
* Another way to use apply() involves the use of lambda() function.
* A lambda() function is a small anonymous function. A lambda() function can take any number of arguments, but can only have one expression.

       # lambda function - Row wise operation
          def revised_profit(revenue, budget):
               if revenue > 0:
                  new_profit = revenue - budget
               else:
                  new_profit = np.nan
               return new_profit

      df['new_profit'] = df.apply(lambda x: revised_profit(x['revenue'], x['budget']),axis=1)
  
* df.sort_values() - sorts the values in the column in ascending or decending order.

        df.sort_values(['status','new_profit'], ascending=[False,True]).head()

----------------------------------------------------------------------------------------------------------------------------------  
* datetime.strptime() -- means string parser, this will convert a string format to datetime.
* datetime.strftime() -- means string formatter, this will format a datetime object to string format.

      df['new_release_date']=df['release_date'].apply(lambda x : datetime.strptime(x,'%m/%d/%y'))

**Some operations we can do on datetime**

            from datetime import timedelta
            print(date.today())
            print(date.today() - timedelta(days=1))
            print(datetime.now() + timedelta(hours=5.5))
            print(datetime.now() + timedelta(seconds=60))

 **Difference in two datetime**
 
          time_delta=df['new_release_date'][0]-df['new_release_date'][5]
          time_delta

  




