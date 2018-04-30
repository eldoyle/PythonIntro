---
title: "Loops"
teaching: 0
exercises: ""
questions:
- "Add Questions"

objectives:
- "Add Objectives"
- ""
- ""
keypoints:
- "Add Keypoints"
- ""
- ""
---
## Making the computer repeat things

This is where being able to write your own code gets really powerful!  Often, we will need to repeat the same calculation over and over, or repeat the same analysis workflow on multiple different files.  Loops are one tool that allows us to repeat things.

Note: Because properly using loops requires careful attention to spacing and indentation, will work primarily from scripts.

~~~
#One way to print every letter in a word
word = 'lead'

print(word[0])
print(word[1])
print(word[2])
print(word[3])
~~~
{: .language-python}

However, this is a very inefficient approach!  If the word gets much longer, then we are better off typing out the letters ourselves.  Or what if we don’t know how long the word is?

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
`for thing in element: #element is a list, string, etc  
			Do something to thing
			Can be multiple lines

#This is not part of the loop (is not indented)`

In the example above, `thing` is the loop variable.  It will take on multiple values while the loop is running.  In our oxygen example, letter will be ‘o’ the first time through the loop, ‘x’, the second time, and so on, until the last time through when it takes on the value ‘n’.

We can name the loop variable anything we want, such as `banana` or `fuzzyKittens`, as long as we refer to it inside the body of the loop!

~~~
#A much better way to print every letter in the word
word2 = 'oxygen'
for apple in word2:
	print("The letter is " + apple)
    
print('Done with the for loop')
~~~
{: .language-python}

However, this violates all of our rules about good variable names!  In general, you should try to give your loop variables descriptive names that will make it clear what your code is doing.

## Examples/Exercies
Finish
