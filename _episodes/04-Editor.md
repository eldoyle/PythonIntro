---
title: "Running code in the editor"
teaching: 0
exercises: 0
questions:
- "How can I use the editor window to write and run multiple lines of code at once?"

objectives:
- "Be able to write and run a Python script"

keypoints:
- "A script is a file that contains multiple lines of code"
- "A script can be run all at once rather than writing and running one line at a time"
- "A script can be reused over and over again"
---

## Writing scripts

Rather than running our code one line at a time, we could write it in the Editor window, save it, and run everything at once.
A script is a file that contains multiple line of code.  Scripts have many advantages over working in the console: they can be 
saved and worked on over time (useful for writing all but the tiniest programs!), and they can be reused.  This means that you
don't have to type the same commands over and over!

When you run a script, Spyder will run your code in order, line by line, from top to bottom.

### Script example
In the lesson on [Variables]({{ page.root }}/03-variables) we we wrote code to convert an area in pixels to area in mm2.  Let's convert it to a script.

Create a new script file by clicking the blank page button on the top left.  Then, type in the following lines of code:

~~~
AreaInPixels = 6929
mm2PerPixel = 0.0277
AreaInMM = AreaInPixels*mm2PerPixel
print(AreaInMM)
~~~ 
{: .language-python}

Run the program by clicking the green arrow button at the top of the Spyder window.

### Where do scripts get saved?

The first time you run a script, Spyder will ask you to save your code.  This is when you can choose where to save it.

By default, the Working Directory is where Spyder will save your scripts and look for files.  You can change your working
directory by using the buttons at the top-right of Spyder.  It is a good idea to create one folder that you can easily find to
store all of your Python projects.  On the DIVAS VM, your working directory is automatically set to </home/diva>.

> ## Know your Working Directory
> Later, when we use scripts to open files or import functions from other .py files, you will need to either 1) Make sure the 
> file you are trying to open/import is located in the same folder as the script you are running OR 2) supply the full path to > > the file.
{: .callout}

> ## .py files
> When you save your program, make sure the name ends in the file extension “.py”.  This tells  your computer that this is a 
> Python script.  It will also enable color coding in Spyder.  In fact, if you open a script in Spyder and don’t see color 
> coding, the first thing you should check is for the “.py” extension.
{: .callout}

### The ```print()``` statement
The last line of the script contains a new command: ```print()```.  When running code as a script, the values of variables or 
computations are not automatically displayed (trying running the script above without that line!).  If you want to show a 
variable or print some other output, you can use the ```print()``` command.  ```print()``` goes on its own line, with whatever 
you want to print inside the parentheses.

The output of the print statement will be printed in the console.

> ## Using informative print statements
> We can make the print statement more informative by including some explanatory text.  For example, we could combine a 
> descriptive text string with the variable that we wish to print.  This will prevent you from printing out multiple numbers or 
> variables with no indication of which one is which!
>
> As an example, change the last line of the script above to read
> ~~~
> print("The area in mm2 is", AreaInMM)
> ~~~
> {: .language-python}
>
> Then run the script.  You should get a more informative output statement!
{: .callout}

## Good practices- Write your code for a human, not a computer!

Python doesn’t care about picking good variable names, whether or not you break up chunks of code with whitespace, or whether or 
not you include helpful notes to yourself or other users.  However, all of these things will make a difference to a human 
reader.  You should always write your code for a human audience- specifically yourself or someone else who might pick up your 
project months or years from now and need to figure out what your code actually does.

To include the readability and usefulness of your code, you should
1. Use good variable names (see the [previous lesson]({{ page.root }}/03-variables) for examples.
2. Break up long pieces of code logically, using empty lines (whitespace).  Try to break up your code into chunks based on 
function.
3. Include comments.  The `#` symbol indicates that everything that comes after it on a line of code is a comment.  The 
comment will be ignored by Python, but it can provide useful information to future users of your code (including you!).  At a 
minimum, you should include
    * A comment line at the beginning of each section of code explaining what the section is doing
    * Comments at the end of lines if the line of code does something unusual or interesting
    * Put the comment on the line above if it is long

Anything that will be important to remember later should be commented!  You will not remember why you made that choice 3 days, 
months, or years later!

Python also allows you to include longer comments a block comments (such as the block comment automatically generated by Spyder 
at the top of a script).  Block comments are denoted by three double quotes at the beginning of the block comment `"""` and 
three double quotes at the end. 

~~~
"""
This is an example of a block comment.
This is the second line of the comment.
"""
~~~
{: .language-python}

At minimum, include a block comment at the beginning of your script explaining the name, usage, and the purpose/goal of the 
script.

> ## Examples/Exercises
> Modify the script below to include appropriate comments and a descriptive print statement.
> ~~~ 
> AreaInPixels = 6929
> mm2PerPixel = 0.0277
> AreaInMM = AreaInPixels*mm2PerPixel
> print(AreaInMM)
> ~~~
> {: .language-python}
> > ## Solution
> > ~~~
> > """
> > Created on Mon Apr 24 21:15:50 2017
> > 
> > @author: erin.doyle
> > 
> > A script to convert measured area in pixels to actual area in mm2
> > """
> > #Set variables and conversion factors
> > AreaInPixels = 6929 #example of an end-of-line comment
> > mm2PerPixel = 0.0277 #Python ignores everything after the '#'
> > 
> > #Convert from pixels to mm2
> > AreaInMM = AreaInPixels*mm2PerPixel
> > 
> > #Print the final area in mm2
> > print("The area in mm2 is", AreaInMM) #print description + number
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Example
> In a previous example from the lesson on [Variables]({{ page.root }}/03-variables), you wrote code to take twp variables and 
> “switch” their values, so that 
> `density1 = 4.59` and `density2 = 3.28`
> became
> `density1 = 3.28` and `density2 = 4.59`
> Now, take that code and convert it to a script.  Your script should 1) include descriptive comments and 2) print out 
> a useful statement explaining what the values of the variables are both before and after the switch.
> > ## Solution
> > #print values before switching:
> > print(“Before switching, density1 is”, density1, “and density2 is”, density2) 
> >
> >
> > #Swap variables
> > temp1 = density1 #create a temporary variable to store density 1
> > density1 = density2 #reassign density1
> > density2 = temp1 #Assign density2 to the value in the temp variable
> > 
> > #print values after
> > print(“After switching, density1 is”, density1, “and density2 is”, density2)
> {: .solution}
{: .challenge}
