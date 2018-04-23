---
title: "Conditionals"
teaching: 30
exercises: 0
questions:
- ""
objectives:
- ""
keypoints:
- 
---

Conditionals are another powerful tool to use in our computer programs: they allow the program to make choices and run part of the code only if a specific condition or conditions are met

We use the Syntax
~~~
if <condition>:
	do this if condition 1 is true
else:
		do this if the condition is not true
		
this is not part of the if/else block and will always be executed
~~~
{: .language-python}

For example, we could write code to check the values of variables and take an action if they are in a specific range
~~~
a= 17

if a < 10:
	print("the number is less than 10")
else:
	print(“the number is 10 or greater”)

print(“this will always get printed”)
~~~
{: .language-python}

Note that we can use elif to check multiple conditions.  Python will check each condition one at a time until it finds one that is true.  It will then execute the code under that statement, and then be done with the for loop.
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

> ## SWC “How many paths”
> Consider the code below.  Which letters (A, B, and/or C) would be printed?  Why?
> ~~~
> if 4 > 5:
>    print('A')
> elif 4 == 5:
>    print('B')
> elif 6 < 5:
>    print('C')
>	else:
>	    print(“none of these is true”)
> ~~~
> {: .language-python}
> > ## Solution
> > Write out solution
> {: .solution}
{: .challenge}

## Comparison operators (==, <, >, <=, >=, !=) and booleans
We have already seen the comparison operators < (less than) and == (used for checking equality, not the same as the = assignment operator)
Other possible operators are:
+ `>` greater than
+ < less than
+ >= greater than or equal to
+ <= less than or equal to
+ == is equal to
+ != is not equal to

## Booleans
`True` and `False` are special words in Python called booleans which represent true and false statements. However, they aren’t the only values in Python that are true and false. In fact, any value can be used in an if or elif.

After reading and running the code below, explain what the rule is for which values are considered true and which are considered false.
~~~
if '':
    print('empty string is true')
if 'word':
    print('word is true')
if []:
    print('empty list is true')
if [1, 2, 3]:
    print('non-empty list is true')
if 0:
    print('zero is true')
if 1:
    print('one is true')
 ~~~
 {: .language-python}
 
 
