---
title: "Analyzing Data with Numpy"
teaching: 30
exercises: 0
questions:
- "How can I analyze a data table?"
objectives:
- "Be able to load a .csv formatted data file using numpy"
- "Understand how to access specific cells, rows, or columns in the data file"
- "Perform simple mathematical operations on the data or subsets of the data"
keypoints:
- "Libraries contain specialized functions that can be imported and used in your code"
- "The numpy library contains functions that allow you to easily read in a .csv-formatted data file and perform simple 
operations on rows and columns of the data"
---

In the lesson on [Files]({{ page.root }}/08-ReadingandWritingTextFiles) we saw one way to deal with a .csv-formatted data file.  
However, Python has some built in libraries that allow us to handle a data table much more easily.

## Libraries
A library is a set of functions that you can import and use in your code.  Usually, libraries contain functions that not all 
users will regularly need.  Thus, there are many libraries available that are designed for specialized tasks.  Tomorrow, you 
will begin working with the OpenCV library, which contains many functions that are useful for image processing.

Today, we are going to use the library **numpy**, which contains many tools for analyzing data stored in a table (like a csv 
file!).

We can import numpy and all of its functions by including the command `import numpy as np` at the beginning of our code.
This will let us call functions in the numpy library as `np.<function>()`.

> ## Lesson Setup
> We will work with the practice file **Titration_color_data_simple.csv**.
> 1. Locate the file *Titration_color_data_simple* in the directory **home/Desktop/workshops/bash-git-python**.
> 2. Copy the file to your working directory, **home/Desktop/workshops/YourName**.
> 3. Make sure that your working directory is also set to the folder home/Desktop/workshops/YourName.
> 4. As you are working, make sure that you save your file opening script(s) to this directory.
{: .callout}  

### The File Setup
Let's open and examine the structure of the file *Titration_color_data_simple.csv*.  If you open the file in a text editor, you 

If you open the file, you will see that it contains a header row, followed by three rows of data.

Each row represents a single color channel (either red, green, or blue) measured over time.  Each column represents a different 
frame of the image.  The goal of the file is to track the color of the titration solution over time, to identify the point
when the reaction is finished.

We will read in this data file and then work to analyze the data.

The code below will open and load the datafile.
~~~
import numpy as np

data = np.loadtxt(fname = 'Titration_color_data_simple.csv', delimiter =',', skiprows = 1, usecols=(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15))

print(data)
~~~
{: .language-python}

Let's dig into this piece of code a little more:

The first half of the first line, `import numpy`, is the statement that tells Python to load the functions in the numpy library 
so that they will be available to use in your code.  The second half of that line, `as np`, creates a shorthand name for the
numpy library.  Now, anytime you want to use a numpy function, you only have to type `np.<function()>` instead of 
`numpy.<function()>`.

The expression `np.loadtxt(...)` is a **function** call that asks Python to run the function named *loadtxt* which is part of 
the numpy library (which we asked Python to abbeviate as *np*). This dotted notation is used everywhere in Python to refer to
the component parts of things as thing.component (in this case, *libraryName.functionName()*, since the function is a part of 
the library).

We supplied *np.loadtxt* with four parameters: 
* fname is the name of the file we want to read
* delimiter is the text that separates values on a line (in this case a comma). 

These both need to be character strings, so we put them in quotes.

* skiprows = 1 tells python to skip 1 row of the file that contains the column names (numpy can only handle numbers, not 
a mix of text strings and numbers).
* usecols=(...) tells Python to only read in these columns.
    * Note that if we are reading in a csv file that contains only numbers (no column names or row names), we can omit the last 
    two arguments skiprows and usecols

Also notice that *np.loadtxt()* handled all of the file opening and parsing for us in a single command!

## Locating specific values within the numpy array

The command `data.shape` will return a tuple that tells us the number of rows and columns in our numpy data array:
~~~
import numpy as np

data = np.loadtxt(fname = 'Titration_color_data_simple.csv', delimiter =',', skiprows = 1, usecols=(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15))

print(data.shape)
~~~
{: .language-python}

This useful command can be used to quickly check that our data was read in correctly.  The output `(3,15)` tells us that we have 
an array of data with 3 rows and 15 columns.

We can look up specific values in the array using indexing.  For example, we can look up the very first element by using the 
command `print(data[0,0])` which returns
> 190.0
{: .output}  


> ## Rows and Columns
> What does `print(data[2,0])` return?  What does it tell you about the indexing (which number is the row and which number is 
> the column?
> > ## Solution
> > `print(data[2,0])` prints out **175.0** which is the first value (index 0) in the third row (index 2).  
> > In general, numpy arrays are indexed by *[row, column]*, using zero-based indexing.
> {: .solution}
{: .challenge}

> ## The very end
> How would you print out the last (bottom right) number of the array?
> > ## Solution
> > `print(data[2,14])` prints out **172.0** which is the fifteenth and last value (index 14) in the bottom row (index 2).  
> > 
> > Note that you could also have done something like this if you did already know the number of rows and colunmns:
> > ~~~
> > nRows = data.shape[0] #gets the number of rows
> > nCols = data.shape[1] #gets the number of columns
> > print(data[nRows-1, nCols-1]) #subtract 1 to adjust for 0-based indexing
> > ~~~
> {: .solution}
{: .challenge}

We can also use this indexing to access subsections or whole rows and columns of the array.

`print(data[2,:])` will return all of row 2.  
`print(data[:,2])` will return all of column 2. 

`print(data[0:2,1:3])` will print the first two rows of the array (0:2), columns 1 and 2 only (1:3).  

Remember that the indexing is 0-based, and the ranges are up to but not inclusive, so that 1:3 gets columns 1 and 2 but not 
column 3.

> ## Taking a subset
> How would you print out the last two columns of the middle and bottom two rows of the array `data`?
>
> Your output should look like this:
> > [[ 154.  155.]    
> >  [ 171.  172.]]  
> {: .output}
> > ## Solution:
> > `print(data[1:3, 13:15])` will print the values that you want.  Since the array has 3 rows, the middle row is located at 
> > index 1 and the bottom row at index 2 (remember: 0-based indexing).  We include 1:3 because indexing is *up to, but not 
> > inclusive*.    
> > Similarly, since we have 15 columns, 13:15 will return the last two columns, located at indexes 13 and 14.
> {: .solution}
{: .challenge}

## Calling Functions on the numpy array
Python is able to do simple arithmetic operations on numpy arrays.  For example, we can divide each value in the array by 2
~~~
scaleData = data/2
print(data)
print(scaleData)
~~~
{: .language-python}

We can do similar operations using `+`, `-`, and `*` (the multiplication operator).

However, we often want to do more complicated operations, such as taking an average, or finding the minimum or maximum value.
For example, the code below will find the average value of the entire dataset.
~~~
print(np.mean(data))
~~~
{: .language-python}

`mean` is a something called a **function**.  Functions are built-in operations that can do things with variables.  All 
functions have the name of the function (in this case, *np.mean*) followed by a set of parentheses ().  The text inside the 
parentheses is called the function's **argument**, and it tells Python what to do the operation on.  After completing the 
operation, the function returns a specified **output** (in this case, a number representing the average of the data). 

Functions are useful because they can condense many lines of code into one simple command that we can call.

You have already seen some functions: `split()` for breaking apart strings is one example; `print()` and `open()` are other 
examples.

`.shape` is not a function (it lacks parentheses and an argument).  Instead, it is a piece of information about the variable 
*data* that was created when we created the numpy array.  It describes the variable *data*, just like an adjective describes a 
noun.  These descriptive pieces of information are called **attributes**.

Other useful functions include the following:
~~~
maxval = np.max(data) #returns the maximum value
minval = np.min(data) #returns the minimum value
stdev = np.std(data)  #returns the standard deviation of all values
print('maximum value:', maxval)
print('minimum value:', minval)
print('standard deviation:', stdev)
~~~
{: .language-python}

## Applying functions to an axis
Of course, none of the examples above makes much sense for our data, since we have different kinds of data in each column of our 
array. `maxval = np.max(data)`, `minval = np.min(data)`, and `stdev = np.std(data)`each applied the function to the entire data 
set.  

What if we want to apply the function to each row or each column individually?
One way is to create a variable storing just the row or column we are interested in.
~~~
reds = data[0,:] #the RedIntensity row
avgRed = np.mean(reds)
print('The average red intensity is: ', str(avgRed))
~~~
{: .language-python}

However, this will quickly get awkward and cumbersome if we need to do this for every column or row in a large dataset 
(although, we could use a for loop).  A more  efficient way is to apply the function over each row or each column by specifying 
an axis.

The code below will return the maximum value of each column and the average value of each row in `data`, respectively.
~~~
print(np.max(data, axis=0))  #axis=0 applies the function to each column
print(np.mean(data, axis=1)) #axis=1 applies the function to each row
~~~
{: .language-python}

> ## Applying functions to subsets of data
> Create a new dataset called `data2` that contains only the last 6 columns of the dataset `data`.  
> Compute the minimum value for each column in `data2` and the average value for each row.
> > ## Solution
> > ~~~
> > import numpy as np
> > 
> > data = np.loadtxt(fname = 'Titration_color_data_simple.csv', delimiter =',', skiprows = 1, usecols=(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15))
> > 
> > data2 = data[:, -6:] #create the column subset
> > 
> > print(np.min(data2, axis=0))  #axis=0 applies the function to each column
> > print(np.mean(data2, axis=1)) #axis=1 applies the function to each row
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Which channel?
> Read in the Titration_color_data_simple.csv file as a numpy array.  
> Use the numpy functions you have learned to identify the color channel that experiences the largest change.
> > ## Solution
> > ~~~
> > import numpy as np
> > 
> > data = np.loadtxt(fname = 'Titration_color_data_simple.csv', delimiter =',', skiprows = 1, usecols=(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15))
> > 
> > #apply the min and max function to each row, then take the difference to find the change
> > mins = np.min(data, axis=1) #axis=0 applies the function to each column
> > maxes = np.max(data, axis=1) #axis=1 applies the function to each row
> > 
> > difference = maxes-mins
> > print(difference)
> > 
> > stdev = np.min(data, axis=1)
> > print(stdev)
> > ~~~
> > {: .language-python}  
> > 
> > > [ 11.  36.   8.]  
> > > [  2.43493098  12.68945319   2.59401019]  
> > {: .output}
> > The output of this program shows that the second row, which represents that green channel, has both the largest max-min
> > difference, and the highest standard deviation.
> {: .solution}
{: .challenge}



