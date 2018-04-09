---
title: "Running code in the editor"
teaching: 0
exercises: 0
questions:
- "What is the question?"

objectives:
- What are the main objectives?
- 
- 
keypoints:
- "First key point."
---

a. Rather than running this code one line at a time, we could write it in the Editor window, save it, and run everything at once.
b. Spyder will run your code in order, line by line, from top to bottom.
c. Example- same as code above to convert area in pixels to mm2.  Create a new script file by clicking the blank page button on the top left.  Then, type in the following commands:
~~~
"""
Created on Mon Apr 24 21:15:50 2017

@author: erin.doyle
"""

AreaInPixels = 6929
mm2PerPixel = 0.0277
AreaInMM = AreaInPixels*mm2PerPixel
print(AreaInMM)
~~~ 
{: .language-python}

d. Run the program by clicking the green arrow button at the top of the Spyder window.
The first time you run a script, Spyder will ask you to save your code.  This is when you can choose where to save it
By default, the Working Directory is where Spyder will save your scripts and look for files.  You can change your working directory by using the buttons at the top-left of Spyder.  It is a good idea to create one folder that you can easily find to store all of your Python projects.   On the DIVAS VM, your working directory is automatically set to </home/diva>.  
Later, when we use scripts to open files or import functions from other .py files, you will need to either 1) Make sure the file you are trying to open/import is located in the same folder as the script you are running OR 2) supply the full path to the file.
When you save your program, make sure the name ends in the file extension “.py”.  This tells  your computer that this is a Python script.  It will also enable color coding in Spyder.  In fact, if you open a script in Spyder and don’t see color coding, the first thing you should check is for the “.py” extension.

