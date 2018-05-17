---
title: "For Loops"
teaching: 0
exercises: ""
questions:
- "How can I repeat the same operations on every item in a list?"
objectives:
- "Understand basic loop syntax"
- "Be able to explain the role of the loop variable"
- "Be able to write simple loops that operate on strings or lists"
keypoints:
- "Loops require careful attention to spacing and indentation"
- "The loop variable takes on the value of each item in the object we are looping over, one at a time"
- "You must refer to the loop variable in the code written under the for loop statement"
---
## For loops: Making the computer repeat things

This is where being able to write your own code gets really powerful!  Often, we will need to repeat the same calculation over 
and over, or repeat the same analysis workflow on multiple different files.  Loops are one tool that allows us to repeat things.

Because properly using loops requires careful attention to spacing and indentation, we will work primarily from scripts.

Here is a simple example.
~~~
#One way to print every letter in a word
word = 'lead'

print(word[0])
print(word[1])
print(word[2])
print(word[3])
~~~
{: .language-python}

However, this is a very inefficient approach!  If the word gets much longer, we are better off typing out the letters ourselves.  
Or what if we don’t know how long the word is?

Here is a much better way to do things.  Notice that we don't even have to know the length of the string stored in `word2`:
~~~
#A much better way to print every letter in the word
word2 = 'oxygen'
for letter in word2:
	print("The letter is " + letter)
    
print('Done with the for loop')
~~~
{: .language-python}

This approach is much more efficient:  We only have type a few lines of code and it is scalable- we could use the same code for any word of any length.

## Loop variables
The general format of a loop is this:
~~~
for thing in element: #element is a list, string, etc  
	Do something to thing
	Can be multiple lines
	All of these lines will be executed for each thing in the string/list/whatever

This is not part of the loop (is not indented)
Code written like this will only be executed after the loop is finished
~~~
{: language-python}

In the example above, `thing` is the loop variable.  It will take on multiple values while the loop is running.  In our oxygen 
example, `letter` will be ‘o’ the first time through the loop, ‘x’, the second time, and so on, until the last time through when 
it takes on the value ‘n’.

We can name the loop variable anything we want, such as `banana` or `fuzzyKittens`, as long as we refer to it inside the body of 
the loop!

~~~
#A much better way to print every letter in the word
word2 = 'oxygen'
for apple in word2:
	print("The letter is " + apple)
    
print('Done with the for loop')
~~~
{: .language-python}

However, this violates all of our rules about good variable names!  In general, you should try to give your loop variables 
descriptive names that will make it clear what your code is doing.

> ## Looping over a list
> Previously, we used this code to convert area in pixels to area in mm2:
> ~~~ 
> """
> Created on Mon Apr 24 21:15:50 2017
> @author: erin.doyle
> A script to convert measured area in pixels to actual area in mm2
> """
> 
> #Set variables and conversion factors
> AreaInPixels = 6929 
> mm2PerPixel = 0.0277 
> 
> #Convert from pixels to mm2
> AreaInMM = AreaInPixels*mm2PerPixel
> 
> #Print the final area in mm2
> print('The area in mm2 is', AreaInMM) 
> ~~~
> {: .language-python}
> Write a new script that uses a for loop to compute and print the area in mm2 for all of the areas stored in the list 
> `areas = [6929.6, 8536.47, 11359.3, 17743.4]`  
> 
> > ## Solution
> > ~~~
> > """
> > Created on Mon Apr 24 21:15:50 2017
> > @author: erin.doyle
> > 
> > A script to convert measured area in pixels to actual area in mm2
> > """
> > 
> > #Set variables and conversion factors
> > areas = [6929.6, 8536.47, 11359.3, 17743.4]
> > mm2PerPixel = 0.0277
> > 
> > #Convert from pixels to mm2
> > for area in areas:
> >      areaInMm = area*mm2PerPixel
> > 
> >      #Print the final area in mm2
> >      print('area in pixels is: ' + str(area) + '. The area in mm2 is: '  + str(AreaInMm)) #print description + number
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## Using a loop to update a variable
Sometimes, you may need to set up a variable outside of the loop (for example, a counter), and then update it with each run 
through the loop:
~~~
length = 0
for vowel in 'aeiou':
    length = length + 1

print('There are', length, 'vowels')
~~~
{: .language-python}

It’s worth tracing the execution of this little program step by step. Since there are five characters in 'aeiou', the statement 
on line 3 will be executed five times. The first time around, length is zero (the value assigned to it on line 1) and vowel is 
'a'. The statement adds 1 to the old value of length, producing 1, and updates length to refer to that new value. The next time 
around, vowel is 'e' and length is 1, so length is updated to be 2.  The trace below walks you through this process.

|                     | vowel | length |
| ------------------  |-------| -------|
| Before the loop:    | n/a   | 0      |
| During the loop:    | a     | 0 + 1 = 1 |
|                     | e     | 1 + 1 = 2 |
|                     | i     | 2 + 1 = 3 |
|                     | o     | 3 + 1 = 4 |
|                     | u     | 4 + 1 = 5 |
| After the loop:     | u     | 5 |

After three more updates, length is 5; Since there is nothing left in 'aeiou' for Python to process, the loop finishes and the print statement on the last line tells us our final answer.

Note that a loop variable is just a variable that’s being used to record progress in a loop. It still exists after the loop is 
over, and we can re-use variables previously defined as loop variables as well:
~~~
letter = 'z'
for letter in 'abc':
    print(letter)
print('after the loop, letter is', letter)
~~~
{: .language-python}

## Exercises
> ## From 1 to N
> Python has a built-in function called `range()` that creates a sequence of numbers. `range()` can accept 1-3 parameters. 
> 
> If one parameter is input, `range()` creates an array of that length, starting at zero and incrementing by 1. If 2 parameters 
> are input, `range()` starts at the first and ends just before the second, incrementing by one. If `range()` is passed 3 
> parameters, it starts at the first number, ends just before the second one, and increments by the third one. 
> 
> For example, `range(3)` produces the numbers 0, 1, 2.  `range(2, 5)` produces 2, 3, 4, and `range(3, 10, 3)` produces 3, 6, 9. 
> 
> Using `range()`, write a loop that prints the first 3 natural numbers: 1, 2, 3.
> > ## Solution
> > ~~~
> > #Create the range
> > numbers = range(1,4) #note that we have to add one to the top number
> > 
> > for number in numbers: #for loop: numberS is the range, number is one item
> >      print(number)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Reverse a String
> Knowing that two strings can be concatenated (added together) using the `+` operator, write a for loop that takes a string and 
> produces a new string with the characters in reverse order, so `'Newton'` becomes `'notweN'`.
> > ## Solution
> > ~~~
> > word = 'Newton'
> > #Create an empty string that we will add on to
> > newWord = ''
> > 
> > #Loop through word, adding each letter to the end of the string
> > for letter in word:
> >     newWord = newWord + letter #The order of these is important!
> >     
> > print(newWord) #Print the final value of newWord
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Adding up a range of numbers
> Modify your range code from the first exercise to add up all of the even numbers between 1 and 10 (inclusive): 2, 4, 6, 8, 10.
> > ## Solution
> > ~~~
> > #Create the range
> > numbers = range(2,11,2) #note that we have to add one to the top number of the range.  The second 2 is the "step" size.
> > 
> > #Create a variable total to store the sum
> > total = 0
> > for number in numbers: #for loop: numberS is the range, number is one item
> >      total = total + number
> > 
> > #after going through all of the numbers, print the final total
> > print(total)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}
