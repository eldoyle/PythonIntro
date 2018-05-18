---
title: "Variables"
teaching: 0
exercises: 60
questions:
- "How do we store data in variabes?"

objectives:
- "Be able to create variables"
- "Understand that different types of variables store different kinds of information"
- "Be able to perform simple arithmatic operations on variables"
keypoints:
- "Creating variables allows you to \"reuse\" a number or value in multiple locations in your code"
- "Python stores different kinds of information (text, numbers, decimal numbers, and others) as different \"types\" of variables"
- "You should give your variables descriptive names! This will make your code easier to read!"
---
## Creating Variables

If we want to, we can essentially use Python as a fancy calculator.  Type the command below into the Spyder console and press 
`Enter':
~~~
5 + 7
~~~
{: .language-python}

You should see the result returned as output in the console:
~~~
12
~~~
{: .output}

Here's another example.  If I type: 
~~~
636/8
~~~
{: .language-python}
I should get back the output 
~~~
79
~~~
{: .output}

However, this isn’t very efficient.  The real value of using Spyder/Python for something like this is that we can store that value in a variable and use it again later.

Imagine that we have computed colony area in pixels from one of our plate images and we want to convert it to actual area in 
square mm.  Based on the size properties of our image or some kind of scale marker, we have figured out the number of pixels.
That corresponds to a square mm of area.  We can create variables for each of these values and use them to do calculations.

Type the commands below in the console, hitting `Enter` after each line.
~~~
AreaInPixels = 6929
mm2PerPixel = 0.0277
AreaInPixels*mm2PerPixel
~~~
{: .language-python}
This will return the value of the last calculation:
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

### The assignment operator, `=`

A variable is just a name for a value, like x or AreaInMm.  We assign a variable name to a value by using the assignment 
operator, `=`.  This is not the same as saying that the variable name equals the value.  Later, when we use test for equality, 
we will use a different operator (==).

The variable name is just a convenient handle that we assign to, and can use to refer to, a value.  You can change the value 
assigned to a variable at any time, just by reassigning it.

This code
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
The value of *mm2PerPixel* has been updated.

Now, check the value of *areaInPixels*
~~~
AreaInPixels
~~~
{: .language-python}
It still has the same value:
~~~
6929
~~~
{: .output}

The value for mm2PerPixel changed, but the value for AreaInPixels did not!  If we imagine the variable as a sticky note with a 
name written on it, assignment is like putting the sticky note on a particular value:

This means that **assigning a value to one variable does not change the values of other variables**.  Since AreaInPixels doesn’t 
remember where it came from, it isn’t automatically updated when mm2PerPixel changes.  This is different from the way 
spreadsheets work.

### Mathematical operations

Python uses all of the usual mathematical operators to perform operations on numbers and variables.  You have 
already seen addition several  
* `+` addition
* `*`multiplication 
* `/` division
* `**` exponentiation
* `%`, the modulus operator (pronounced "mod") , which returns the remainder from division
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

### Different types of variables store different types of data

Python lets us make different “types” of variables.  So far you have seen ints (short for integers, numbers without decimal 
points) and floats (floating point numbers, numbers with decimal points).  Python also allows you to make variables that are 
strings (strings of text, very useful in Biology when dealing with sequence data) and other types of variables that we will 
introduce you to later.

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

  File "<ipython-input-17-5359e87c9757>", line 1, in <module>
    name + remainder

TypeError: Can't convert 'int' object to str implicitly
~~~
{: .output}

Since Python doesn’t know exactly how to add a word to a number, it returns an error message.  Error messages are usually very descriptive, and can tell you a lot about problems in your code!

### Good practices- variable names

Variables should be given descriptive names.  Python requires that variable names must begin with a letter.  They are also case 
sensitive (Text, text, and tEXT are all different variables).  Beyond this, Python doesn’t care what you call your variables.  
You could name them all after different kinds of fruit if you want!  However, this would be very confusing when you went back 
later to look at your code.

You should do your best to give your variables descriptive, useful names that describe the data they hold.  

> ## DIVAS variable name conventions
> In the DIVAS project, variables should start with a lowercase letter, and capitalize the first letter of each successive 
> word (“camel case”).  
> 
> For example, `plateArea`, or `colonyCount`.
{: .callout}

## Examples/Exercises

> ## Variable Switching
> Draw diagrams showing what variables refer to what values after each statement in the following program:
> ~~~
> avgCount = 47.5
> time = 122
> avgCount = avgCount * 2.0
> time = time - 24
> ~~~
> {: .language-python}
> > ## Solution
> > On line 1 of the code, the value **47.5** is assigned to the variable `avgCount`.  Similarly, line 2 assigns **122** to the
> > variable name `time`.
> > 
> > On line 3, `avgCount` is reassigned.  This line of code takes the value stored in `avgCount` (currently 47.5), multiplies it 
> > by 2, and then stores the new value **95.0** to the variable name `avgCount`.  The effect is that the value stored in 
> > `avgCount` is updated to be **95.0**.  
> > 
> > The 4th line similarly takes the old value of `time`, subtracts 24, and reassigns the variable name `time` to point to this 
> > new value (98).
> {: .solution}
{: .challenge}

> ## Sorting Out References
> What does the following program print out?  Why?
> ~~~
> first, second = 'Plate302', 'Ecoli'
> third, fourth = second, first
> print(third, fourth)
> ~~~
> {: .language-python}
> > ## Solution
> > If you run the code above, you should get printed output that looks like this:
> > ~~~
> > Ecoli Plate302
> > ~~~
> > To understand what is happening, you can think of the first line of code as storing the value “Plate302” somewhere in your 
> > computer’s memory and then assigning it the handle `first`.  At the same time, it stores the value “Ecoli” and assigns it the 
> > handle `second`.  Then, the second line of code creates new handles pointing to those same values.  So `third` points at the 
> > same value/memory location as `second` (“Ecoli”) and `fourth` points at the same value/location as `first` (“Plate302”).
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
