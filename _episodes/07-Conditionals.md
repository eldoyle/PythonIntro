---
title: "Conditionals"
teaching: 30
exercises: 0
questions:
- "How can I make my program make choices?"
objectives:
- "Understand the syntax and indentation of an if statement"
- "Know when to use `if`, `elif`, and `else`"
- "Be able to explain which statements in the if statement block will be executed"
keypoints:
- "If/elif/else statements allow your program to do different things if different conditions are met"
- "If/elif/else blocks require careful attention to indentation"
- "In an if/elif/else block, the code underneath the first condition that is true will be executed"
- "Code under other conditions will not be executed, even if they are also true"
---

Conditionals are another powerful tool to use in our computer programs: they allow the program to make choices and run part of the code only if a specific condition or conditions are met

The syntax of in if statement looks like this.  Note that the indentation is very important!
~~~
if <condition>:
	do this if condition 1 is true
else:
	do this if the condition is not true
		
this is not part of the if/else block and will always be executed
~~~
{: .output}

For example, we could write code to check the values of variables and take an action if they are in a specific range
~~~
a= 17

if a < 10:
	print("the number is less than 10")
else:
	print("the number is 10 or greater")

print("this will always get printed")
~~~
{: .language-python}

Wee can use `elif` (short for "else if") to check multiple conditions.  Python will check each condition one at a time until it 
finds one that is true.  It will then execute the code under that statement, and then be done with the for loop.
~~~
number = 29
if number < 10:
	print("the number is less than 10")

elif number < 20:
	print("the number is between 10 and 20")

elif number < 30:
	print("the number is between 20 and 30")
else:
	print('It is a big number')
    
print('We are done checking if/else conditions')
~~~
{: .language-python}

When you run this code, only the statment under the second elif (`elif number < 30`) is printed.  Once a true condition is
encountered, the code under that condition is executed (`print('the number is between 20 and 30")`).  Python skips over the
remaining `else` statement and then proceeds to the last print statment, which is not part of the if/elif/else block.

Even if multiple conditions are true, Python will only execute the code under the first true if/elif statement it encounters:
~~~
number = 15
if number < 10:
	print("the number is less than 10")

elif number < 20:
	print("the number is between 10 and 20")

elif number < 30:
	print("the number is between 20 and 30")


elif number == 15:
	print("the number is exactly 15")
else:
	print('It is a big number')
    
print('We are done checking if/else conditions')
~~~
{: .language-python}

Notice that when you run this code, only the statment under the first elif (`elif number < 20`) is printed, *even though the
next elif statement is also true!*

> ## “How many paths”
> Consider the code below.  Which letters (A, B, and/or C) would be printed?  Why?
> ~~~
> if 4 > 5:
>     print('A')
> elif 4 == 5:
>     print('B')
> elif 4 < 5:
>     print('C')
> else:
>     print("none of these is true")
> ~~~
> {: .language-python}
> > ## Solution
> > Only the letter 'C' should be printed.  The first two statements (4>5 and 4==5) are not true.  The third statment (4<5) is > > > true, so the print statment underneath it will be executed.  The final else statment is not executed.
> {: .solution}
{: .challenge}

## Comparison operators (==, <, >, <=, >=, !=)
We have already seen the comparison operators `<` (less than) and `==` (used for checking equality, not the same as the `=` assignment operator)
Other possible operators are:
+ `>` greater than
+ `<` less than
+ `>=` greater than or equal to
+ `<=` less than or equal to
+ `==` is equal to
+ `!=` is not equal to

## Booleans
`True` and `False` are special words in Python called booleans which represent true and false statements. However, they aren’t 
the only values in Python that are true and false. In fact, any value can be used in an if or elif.

> ## What values are True?
> After reading and running the code below, explain what the rule is for which values are considered true and which are 
> considered false.
> ~~~
> if '':
>    print('empty string is true')
> if 'word':
>     print('word is true')
> if []:
<     print('empty list is true')
> if [1, 2, 3]:
>     print('non-empty list is true')
> if 0:
>     print('zero is true')
> if 1:
>     print('one is true')
>  ~~~
> {: .language-python}
> > ## Solution/Explanation
> > In general, the value 1 is considered to be true and 0 is false.  Empty objects, such as the empty string and empty list 
> > above are considered false.  
> {: .solution}
{: .challenge}

> ## Which parts do I need?
> In general all if statement blocks must start with an `if` statement!  However, the other parts aren't always needed.
> * An `if` statement is not required be followed by an `else`.  However, `else` must always be preceded by an `if`!
> * In general, an `else` statement is not required for if/elif code blocks.
> * You can stack up multiple if statments.  If you use if/if instead of if/elif, *both if statments will be executed* if they 
> are true.
{: .callout}

> ## Which path?
> Look at the code below.  Which print statements will be executed ans why?  If you are not sure, try running it!
> ~~~
> number = 5
>
> if number <= 10:
>     print('number is smaller than 10')
> if number <= 20:
>     print('number is smaller than 20')
> if number <= 30:
>     print('number is smaller than 30')
> elif number > 30 and  number < 100:
>     print('number is medium-sized')
> else:
>     print('the number is really big')
> ~~~
> {: .language-python}
> > ## Solution
> > The code above should generate the following output:
> > > number is smaller than 10  
> > > number is smaller than 20  
> > > number is smaller than 30  
> > {: .output}
> > The first three if statements are independent of each other.  They will all be checked, regardless of whether or not a
> > previous if statment was true.  The `elif` and `else` statements go with the third `if` statement.  `elif` will only be
> > checked if the third `if` is not true, and `else` will only be checked if the the third `if` and the `else` are not true.
> > 
> > What value of number would cause only the statement under `elif` to be printed?  What would cause only the `else` statement 
> > to be printed?
> {: .solution}
{: .challenge}
 
> ## Combining loops and conditionals: Sorting image files into bins
> 
> Imagine that we have a list of image files that are different types of images (you will learn more about the different image 
> formats later in the week).  
> You have the following list of image names and three empty lists.
> ~~~
> images = ['image1.png', 'image2.jpg', 'image3.bmp', 'image4.jpg', 'image5.png']
>
> bmps = []
> pngs = []
> jpgs = []
> ~~~
> {: .language-python}
>
> Write code to put each of the image names in `images` into the appropriate list.  Your code should 
> 1) loop through all of the images.
> 2) For each image, check the file extension (the part after the "."), and append the filename to the appropriate list
> 3) Print the final lists.  They should have these values:
> > bmps = ['image3.bmp']
> > jpgs = ['image2.jpg', 'image4.jpg']
> > pngs = ['image1.png', 'image5.png']
> {: .output}
> > ## Solution
> > ~~~
> > images = ['image1.png', 'image2.jpg', 'image3.bmp', 'image4.jpg', 'image5.png']
> > 
> > #create the empty lists that we will add file names into
> > bmps = []
> > pngs = []
> > jpgs = []
> > 
> > for filename in images:
> >     if filename[-3:] == 'bmp': # [-3:] looks at the last 3 characters of the filename
> >             bmps.append(filename)
> >     elif filename[-3:] == 'png':
> >             pngs.append(filename)
> >     elif filename[-3:] == 'jpg':
> >             jpgs.append(filename)
> >     else:
> >             print(filename, 'is not a jpg, bmp, or png file')
> > 
> > #print final lists
> > print('bmps: ', bmps)
> > print('pngs: ', pngs)
> > print('jpgs: ', jpgs)
> > {: .language-python}
> {: .solution}
{: .challenge}
