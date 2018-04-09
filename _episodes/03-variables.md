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

## Mathematical operations

Python allows us to use all of the usual mathematical operators to perform operations on numbers and variables.  You have already seen addition (+), multiplication (*) and division (/).

~~~
AreaSquared = AreaInMm**2
AreaSquared
~~~
{: .language-python}
Returns the output
~~~
36838.39164889
~~~
{: .output}

The modulus operator (%) may also be useful, it returns the remainder from division.

~~~
remainder = 10.0%8
remainder
~~~
{: .language-python}
Returns the output
~~~
2.0
~~~
{: .output}

## Types of variables (ints, floats, strings)

Python lets us make different “types” of variables.  So far you have seen ints (short for integers, numbers without decimal points) and floats (floating point numbers, numbers with decimal points).  Python also allows you to make variables that are strings (strings of text, very useful in Biology when dealing with sequence data) and other types of variables that we will introduce you to later.

~~~
name = 'Erin'
word = 'image'
~~~
{: .language-python}

You can use many of the same operators on text strings that you can on floats or ints:

~~~
name + word
~~~
{: .language-python}
Returns the output
~~~
'Erinimage'
~~~
{: .output}

~~~
name * 2
~~~
{: .language-python}
Returns the output
~~~
'ErinErin'
~~~
{: .output}

However, not all operators are supported for all combinations of variables:

~~~
name + remainder
~~~
{: .language-python}

Will result in an error message
~~~
Traceback (most recent call last):

  File "<ipython-input-28-5359e87c9757>", line 1, in <module>
    name + remainder

TypeError: cannot concatenate 'str' and 'float' objects
~~~
{: .output}

Since Python doesn’t know exactly how to add a word to a number, it returns an error message.  Error messages are usually very descriptive, and can tell you a lot about problems in your code!

## Good practices- variable names

Variables should be given descriptive names.  Python requires that variable names must begin with a letter.  They are also case sensitive (Text, text, and tEXT are all different variables).  Beyond this, Python doesn’t care what you call your variables, you could name them all after different kinds of fruit if you want!  However, this would be very confusing when you went back later to look at your code.

You should do your best to give your variables descriptive, useful names that describe the data they hold.  In the DIVAS project, variables should start with a lowercase letter, and capitalize each successive letter (“camel case”).

## Examples/Exercises
SWC example: Check your understanding


> ## Variable Switching
> Draw diagrams showing what variables refer to what values after each statement in the following program:
> ~~~
> mass = 47.5
> age = 122
> mass = mass * 2.0
> age = age - 20
> ~~~
> {: .language-python}
> > ## Solution
> > Write out solution
> {: .solution}
{: .challenge}

> ## SWC Example: Sorting Out References
> What does the following program print out?  Why?
> ~~~
> first, second = 'Grace', 'Hopper'
> third, fourth = second, first
> print(third, fourth)
> ~~~
> {: .language-python}
> > ## Solution
> > Write out solution
> {: .solution}
{: .challenge}

> ## Variable Switching
>
> Given the following two variables
> ~~~
> density1 = 4.59
> density2 = 3.28
> ~~~
> {: .language-python}
> write code to “switch” the values so that the final result is that
> ~~~
> density1 = 3.28
> density2 = 4.59
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > The trick here is to create a temporary variable so that the values stored are not "lost"
> >
> > ~~~
> > temp1 = density1
> > density1 = density2
> > density2 = temp1
> > print(density1, density2)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}
