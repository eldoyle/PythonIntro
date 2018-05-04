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

## Using a loop to update a variable
Sometimes, you may need to set up a variable outside of the loop (for example, a counter), and then update it with each run through the loop:
~~~
length = 0
for vowel in 'aeiou':
    length = length + 1

print('There are', length, 'vowels')
~~~
{: .language-python}

It’s worth tracing the execution of this little program step by step. Since there are five characters in 'aeiou', the statement on line 3 will be executed five times. The first time around, length is zero (the value assigned to it on line 1) and vowel is 'a'. The statement adds 1 to the old value of length, producing 1, and updates length to refer to that new value. The next time around, vowel is 'e' and length is 1, so length is updated to be 2. After three more updates, length is 5; since there is nothing left in 'aeiou' for Python to process, the loop finishes and the print statement on line 4 tells us our final answer.

Note that a loop variable is just a variable that’s being used to record progress in a loop. It still exists after the loop is over, and we can re-use variables previously defined as loop variables as well:
~~~
letter = 'z'
for letter in 'abc':
    print(letter)
print('after the loop, letter is', letter)
~~~
{: .language-python}

## Examples
> SWC Exercise: From 1 to N
> Python has a built-in function called `range` that creates a sequence of numbers. range can accept 1-3 parameters. 
> 
> If one parameter is input, `range` creates an array of that length, starting at zero and incrementing by 1. If 2 parameters are input, > `range` starts at the first and ends just before the second, incrementing by one. If `range` is passed 3 parameters, it starts at the  > first one, ends just before the second one, and increments by the third one. 
> 
> For example, `range(3)` produces the numbers 0, 1, 2.  `range(2, 5)` produces 2, 3, 4, and `range(3, 10, 3)` produces 3, 6, 9. 
> 
> Using `range`, write a loop that uses range to print the first 3 natural numbers: 1, 2, 3.
> > ## Solution
> > Add solution
> {: .solution}
{: .challenge}

> SWC Exercise: Reverse a String
> Knowing that two strings can be concatenated using the + operator, write a loop that takes a string and produces a new string with the characters in reverse order, so 'Newton' becomes 'notweN'
> Hint: don’t forget that you can use + to concatenate (add) strings
> > ## Solution
> > Add solution
> {: .solution}
{: .challenge}

> Modify your range code to print all of the even numbers between 1 and 10 (inclusive):  2, 4, 6, 8, 10
> > ## Solution
> > Add solution
> {: .solution}
{: .challenge}
