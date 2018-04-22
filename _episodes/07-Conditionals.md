---
title: "Introduction"
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
**if <condition>:
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
