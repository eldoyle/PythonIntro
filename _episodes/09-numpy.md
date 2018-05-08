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
- "Numpy allows you to easily read in a .csv-formatted data file and perform "
- "In an if/elif/else block, the code underneath the first condition that is true will be executed"
- "Code under other conditions will not be executed, even if they are also true"
---

In the lesson on [Files]({{ page.root }}\ReadingandWritingTextFiles) we saw one way to deal with a .csv-formatted data file.  
However, Python has some built in libraries that allow us to handle a data table much more easily.

## Libraries
A library is a set of functions that you can import and use in your code.  Typically, libraries contain functions that not all 
users would typically need.  Thus, there are many libraries available that are designed for specialized tasks.  Tomorrow, you will 
begin working with the OpenCV library, which contains many functions that are useful for image processing.

Today, we are going to use the library **numpy**, which contains many tools for analyzing data stored in a table (like a csv 
file!).

We can import numpy and all of its functions by including the command `import numpy as np` at the beginning of our code.
This will let us call functions in the numpy library as `np.<function>()`.

## Using the numpy library to load a dataset
We are going to look at the file DIRT_output_selected_images_simple.csv.
Open the file and take it look. We will use the numpy library to load specific columns:  
X_PIXEL: x pixels in scale marker
Y_PIXEL: y pixels in scale marker
X_SCALE: mm per pixel (x)
Y_SCALE: mm per pixel (y)
DIA_STEM: stem diameter
DIA_STEM_ SIMPLE: stem diameter
AREA: the number of root (light) pixels
AVG_DENSITY: the ratio of root to background pixels within the root ball
WIDTH_MED: the median width of the rootball
WIDTH_MAX: the maximum width of the rootball

The code below will open and load the datafile.
~~~
import numpy as np

data = np.loadtxt(fname = 'DIRT_output_selected_images_simple.csv', delimiter =',', skiprows = 1, usecols=(1,2,3,4,5,6,7,8,9,10))

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
the parts of things as thing.component.

We supplied *numpy.loadtxt* with 4 parameters: 
* fname is the name of the file we want to read
* delimiter is the text that separates values on a line (in this case a comma). 

These both need to be character strings, so we put them in quotes.

* skiprows = 1 tells python to skip the first row of the file that contains the column names (numpy can only handle numbers, not 
a mix of text strings and numbers
* usecols=(...) tells Python to only read in these columns
    * Note that if we are reading in a csv file that contains only numbers (no column names or row names, we can omit the last 
    two arguments skiprows and usecols)

Also notice that numpy.loadtxt() handled all of the file opening and parsing for us in a single command!

