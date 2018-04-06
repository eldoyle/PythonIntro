---
title: "Variables"
teaching: 0
exercises: 0
questions:
- "How do we store data in variabes?"

objectives:
- "Be able to create variables"
- "Understand that different types of variables store different kinds of information"
- "Be able to perform simple arithmatic operations on variables"
keypoints:
- "First key point."
---
## Creating Variables

If we want to, we can essentially use Python as a fancy calculator:
~~~
5 + 7
~~~
{: .language-python}

Returns the output
~~~
12
~~~
{: .output}

Here's another example:
If I type 
~~~
636/8
~~~
{: .language-python}
Returns the output
~~~
79
~~~
{: .output}

However, this isn’t very efficient.  The real value of using Spyder/Python for something like this is that we can store that value in a variable and use it again later.

Imagine that we have computed a root area in pixels from one of our images and we want to convert it to actual area in square mm.  From the scale marker in our image, we also know the area in mm of each pixel.  We can create variables for each of these values.
~~~
AreaInPixels = 6929
mm2PerPixel = 0.0277
AreaInPixels*mm2PerPixel
~~~
{: .language-python}
Returns the output
~~~
191.9333
~~~
{: .output}

If we think that we will need to use this value later, we can also store it in a variable:
~~~
AreaInMm = AreaInPixels * mm2PerPixel
~~~
{: .language-python}

Notice that this doesn’t give us any output!  If we want to print the value of AreaInMm to the console, we can get it by simply calling the variable name:
~~~
AreaInMm
~~~
{: .language-python}
Returns the output
~~~
191.9333
~~~
{: .output}

## The = assignment operator

A variable is just a name for a value, like x or AreaInMm.  We assign a variable name to a value by using the assignment operator, =.  This is not the same as saying that the variable name equals the value.  Later, when we use test for equality, we will use a different operator (==).

The variable name is just a convenient handle that we assign to, and can use to refer to, a value.  You can change the value assigned to a variable at any time, just by reassigning it.

~~~
mm2PerPixel = 0.03
mm2PerPixel
~~~
{: .language-python}
Returns the output
~~~
0.03
~~~
{: .output}

~~~
AreaInPixels
~~~
{: .language-python}
Returns the output
~~~
6929
~~~
{: .output}

Notice that the value for mm2PerPixel changed, but the value for AreaInPixels did not!  If we imagine the variable as a sticky note with a name written on it, assignment is like putting the sticky note on a particular value:

This means that assigning a value to one variable does not change the values of other variables.  Since AreaInPixels doesn’t remember where it came from, it isn’t automatically updated when mm2PerPixel changes.  This is different from the way spreadsheets work.
