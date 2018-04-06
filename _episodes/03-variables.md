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

returns the output
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

However, this isn’t very efficient.  The real value of using Spyder/Python for something like this is that we can store that value in a variable and use it again later.

Imagine that we have computed a root area in pixels from one of our images and we want to convert it to actual area in square mm.  From the scale marker in our image, we also know the area in mm of each pixel.  We can create variables for each of these values.
~~~
AreaInPixels = 6929
mm2PerPixel = 0.0277
AreaInPixels*mm2PerPixel
~~~
{: .language-python}

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

~~~
191.9333
~~~
{: .output}
