---
title: "Defining Functions"
teaching: 0
exercises: 30
questions:
- "How can I write my own functions?"
objectives:
- "Know the basic syntax of a function"
- "Be able to explain the difference between writing a function and calling a function"
- "Practice writing and calling simple functions"
- "Be able to import functions into another script"
keypoints:
- "Function statements start with the keyword *def*, and must include a name, parameters, and a return statement"
- "Functions must be *called* in order to use them"
- "Functions can be imported to be used by other scripts using the *import* command"
---

## Introduction to functions
Often, we will need to do the same calculations and the same set of commands over and over again on multiple files, or multiple 
pieces of data.  Any time you are going to repeat a set of commands, or may want to repeat them later, it makes sense to define 
a function.  Then, every time we need to do that set of commands, we only have to call the function instead of typing each 
command individually.

Let’s start by defining a simple function to convert temperatures in Fahrenheit to Kelvin.
~~~
def fahr_to_kelvin(temp):
    return ((temp - 32) * (5/9)) + 273.15
~~~
{: .language-python}

The function contains the keyword `def` and a function name (in this case, `fahr_to_kelvin`).  The **input parameters** (or 
arguments that must be passed to the function are listed inside of the parentheses.  In the function definition, these
paramaters are placeholder variables.  When we actually use the function later, we will have to supply a value for temp that the 
function will operate *on*.  Finally, the function definition also contains a return statement, which tells us what value(s) 
function will output.

Notice that typing the function doesn’t do anything.  In order to use the function, we have to **call** it, or tell Python to 
perform the function on an input.  To call it, we use the name of the function with the desired arguments inside the parentheses
(in this case, a number representing a temperature in degrees Fahrenheit).
~~~
print(fahr_to_kelvin(0))
print(fahr_to_kelvin(-324))
~~~
{: .language-python}
The value inside of the parentheses is assigned to the variable name `temp` in the function definition above so that the program 
can perform the temperature conversion calculation and return a number representing the converted temperature.

Now, if we need to redo this calculation over and over on different numbers, we can just call the function on each of those 
numbers instead of typing in the entire calculation and potentially making mistakes.

> ## Temperature conversion
> Create a second function that will convert temperatures from Fahrenheit to Celsius.  Test your function by callling it on a
> few different numbers.
> > ## Solution
> > The code below shows you how to write the function and then call it:
> > ~~~
> > def fahr_to_celsius(temp):
> >      return (temp - 32) * (5/9)
> > 
> > print(fahr_to_celsius(72))
> > ~~~
> > {: .language-python}
> > If you need some test values, try the following:  
> > `fahr_to_celsius(212)` should return *100*  
> > `fahr_to_celsius(32)` should return *0*  
> > `fahr_to_celsius(82)` should return *27.778*  
> {: .solution}
{: .challenge}

> ## Temperature conversion, part 2
> Create a new function that will take a temperature in Fahrenheit, convert it to both Kelvin and Celsius, and then return 
> a list of the three temperatures in this order:  
> [original Fahrenheit, Kelvin, and Celsius].  
> > ## Solution
> > Here is one way to do it:
> > ~~~
> > def temp_converter(ftemp):
> >      ctemp = (ftemp - 32) * (5/9)
> >      ktemp = ctemp + 273.15
> >      return [ftemp, ktemp, ctemp]
> > 
> > print(temp_converter(72))
> > ~~~
> > {: .language-python}
> > If you need some test values, try the following:  
> > `temp_converter(212)` should return *[212, 373.15, 100]*  
> > `temp_converter(32)` should return *[32, 373.15, 0]*   
> > `temp_converter(82)` should return *[82, 300.928, 27.778]* 
> {: .solution}
{: .challenge}

## Importing functions
Now that we have written a few functions, we can even import them and use them in other scripts!  

1. Save your current file as *function_examples.py*.  
2. Open a new script file in Spyder.  
3. At the top of your script, include this line:
~~~
from function_examples import fahr_to_kelvin
~~~
{: .language-python}

Now, we can use our *fahr_to_kelvin* function in our new script!  
~~~
print(fahr_to_kelvin(15))
~~~
{: .language-python}

> ## Saving in the working directory
> In order to import functions from another script, the script **must be saved in the same folder** as the script you are 
> running.  Otherwise, Python won't know where to look for the file to import the function you want.
> 
> If the script with functions to be imported is in another folder, you will have to supply the complete path to the file
> as part of the import statement.
{: .callout}


> ## Importing functions
> Open a new script.  Take the temperature conversion function that we wrote above to return the original fahrenheit, Kelvin, 
> and Celsius temperatures and modify it to import and use the functions `fahr_to_kelvin` and `fahr_to_celsius`.
> > ## Solution
> > ~~~
> > from function_examples import fahr_to_kelvin
> > from temp_conversion import fahr_to_celsius #Change temp_converion to the name of the script file with this function
> > 
> > #Define the function
> > def temp_converter(ftemp):
> >      ctemp = fahr_to_celsius(ftemp)
> >      ktemp = fahr_to_kelvin(ftemp)
> >      return [ftemp, ktemp, ctemp]
> > 
> > #call the function
> > print(temp_converter(72))
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Challenge: Finding max color change
> Write a function that examines one color channel (one row) of the file Titration_color_data_simple.csv and returns the frame 
> that has largest change in intensity from the frame before it.  
> 
> For example, if you had the data `intensities = [140, 142, 139, 128, 129, 126]` representing frames 1, 2, 3, 4, 5, and 6, for a 
> single channel you should return the number `3` because the biggest difference is 139-128 = 11 between frames 3 and 4.
> 
> You should be able to read in the entire dataset (either using standard read commands or as a numpy array) and then run your 
> function on each color channel individually.
{: .challenge}
> 
