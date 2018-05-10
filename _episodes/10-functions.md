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

The function contains the keyword `def`, a function name (in this case, `fahr_to_kelvin`), and the **input parameters** that 
must be passed to the function listed inside of the parentheses.  The inputs are the values or data that the function will 
operate *on*.  It also contains a return statement, which tells us what value function will output.

Notice that typing the function doesn’t do anything.  In order to use the function, we have to **call** it, or tell Python to 
perform the function on an input.  To call it, we use the name of the function, along with the desired **input (in this case,
~~~
fahr_to_kelvin(0)
fahr_to_kelvin(-324)
~~~
{: .language-python}

Now, if we need to redo this calculation over and over on differernt numbers, we can just call the function instead of typing in 
the entire calculation and potentially making mistakes.
