## Explain the purpose and basic functionality of the Pandas library. What are some common operations that can be performed on data using Pandas, and how do they contribute to data analysis and manipulation?
Pandas is an open source Python package that is most widely used for data science/data analysis and machine learning tasks. It is built on top of another package named Numpy, which provides support for multi-dimensional arrays.

The most important and basic Pandas functions in Python and methods that are essential for every Data Analyst and Data Scientist to know.
1. read_csv()
This is one of the most crucial pandas methods in Python. read_csv() function helps read a comma-separated values (csv) file into a Pandas DataFrame. All you need to do is mention the path of the file you want it to read. It can also read files separated by delimiters other than comma, like | or tab. More details here.
```python
import pandas

df = pandas.read_csv("data.csv")
print(df)
```
2. head()
head(n) is used to return the first n rows of a dataset. By default, df.head() will return the first 5 rows of the DataFrame. If you want more/less number of rows, you can specify n as an integer.

data_1.head(6)

```python
import pandas as pd
info = pd.DataFrame({'language':['C', 'C++', 'Python', 'Java','PHP']})  
info.head()  
info.head(3) 
# output 
#      language
#0        C
#1       C++
#2       Python
```
3. df.describe()
The df.describe() method in pandas is used to generate summary statistics of various features of a DataFrame. It returns a new DataFrame that contains the count, mean, standard deviation, minimum, 25th percentile, median, 75th percentile, and maximum of each numerical column in the original DataFrame.

```python
print(df.describe())
```

## What are the primary data structures in Pandas, and how do they differ in terms of use cases?
Pandas  provides various data structures and operations for manipulating numerical data and time series. It offers a tool for cleaning and processes your data. It is the most popular Python library that is used for data analysis. In this article, We are going to learn about Pandas Data structure.

It supports two data structures:

1. Series
2. Dataframe

Series:
Pandas is a one-dimensional labeled array and capable of holding data of any type (integer, string, float, python objects, etc.)

Syntax: 
```python
pandas.Series(data=None, index=None, dtype=None, name=None, copy=False, fastpath=False)
```

Parameters:
* data: array- Contains data stored in Series.
* index: array-like or Index (1d)
* dtype: str, numpy.dtype, or ExtensionDtype, optional
* name: str, optional
* copy: bool, default False

### Example 1: 
```python
import pandas as pd
  
# a simple char list
list = ['p', 'a', 'n', 'd', 'a' , 's']
   
# create series form a char list
res = pd.Series(list)
print(res)
# output
# 0  p
# 1  a
# 2  n
# 3  d
# 4  a
# 5  s
```

DataFrame:
A Pandas DataFrame is a 2 dimensional data structure, like a 2 dimensional array, or a table with rows and columns.

```python
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

#load data into a DataFrame object:
df = pd.DataFrame(data)

print(df) 
#     calories  duration
#  0       420        50
#  1       380        40
#  2       390        45
```
## Describe the process of loading a dataset into a Pandas DataFrame. What are some common file formats that can be used, and which Pandas functions are utilized to read these formats?
Pandas allows you to import data from a wide range of data sources directly into a dataframe. These can be static files, such as CSV, TSV, fixed width files, Microsoft Excel, JSON, SAS and SPSS files, as well as a range of popular databases, such as MySQL, PostgreSQL and Google BigQuery. You can even scrape data directly from web pages into Pandas dataframes.

When importing data into Pandas dataframes, you can also save time and write less code by defining which columns to import, rename the columns, set their data types, define the index, and many other things. 

### Load the packages
To get started, create a new Jupyter notebook and load the Pandas library. You’ll also need the Datetime package. When importing the Pandas package the convention is to use the command import pandas as pd which allows you to call Pandas functions by prefixing them with pd. instead of pandas..
```python
import pandas as pd
import datetime as dt
```

### Reading CSV with Pandas
To import a Comma Separated Value (CSV) file and put the contents into a Pandas dataframe we use the read_csv() function, which is appended after calling the pd object we created when we imported Pandas. The read_csv() function can take several arguments, but by default you just need to provide the path to the file you wish to read. Here, data.csv will read in the file called data.csv which is present in the same directory. If the file was stored at 
/home/matt/data/data.csv you would just replace the path.

```python
df = pd.read_csv('data.csv')
```
### Reading a TSV file
(Tab separated value) files are just like CSVs, but the values are separated by a tab instead of a comma. They can also be read using the same read_csv() function, you just need to specify the separator character used. For tabs, this is \t.
```python
df = pd.read_csv('data.tsv', sep='\t')
```
### Reading Microsoft Excel files with Pandas
Pandas includes built-in functionality for reading Microsoft Excel spreadsheet files via its read_excel() function. This works in the same way as read_csv() so can be used on local Excel documents as well as remote files, however, as Excel files are a bit more bloated than CSV files, it can be a bit slower.
```python
df = pd.read_excel('data.xlsx')
```

### *Resources:*
[Pandas in 10](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
[Pandas - Getting Started](https://pandas.pydata.org/pandas-docs/stable/getting_started/intro_tutorials/index.html)
[Corey Schafer - Pandas Tutorials](https://www.youtube.com/playlist?list=PL-osiE80TeTsWmV9i9c58mdDCSskIFdDS)
[What is Pandas](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s)
[Master Pandas](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)

## Things I want to know more about