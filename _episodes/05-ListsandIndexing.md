---
title: "Lists and Indexing"
teaching: 0
exercises: 0
questions:
- "How can we group similar values or data into one variable?"

objectives:
- "Create lists to group similar values or items together"
- "Learn to modify lists by adding or deleting items"
- "Be able to access a specific item or items in a list using list indexing and slicing"
keypoints:
- "Lists can be used to group numbers (ints or floats), strings, or other kinds of values together in one variable"
- "Lists are ordered- objects stay in the order you add them"
- "Lists are indexed using 0-based indexing"
---
## Lists
The variable types we have seen so far, such as floats, ints, and strings let us store one piece of data in a single variable.  
However, it is often useful to store multiple pieces of data in a single variable.  For example, image we have root areas for 
four different roots.  Instead of making four different variables, we can use a list to keep them all together.  This is handy 
because we only have to keep track of one variable name! In the [next lesson]({{ page.root }}\06-Loops) you'll learn how to 
perform the same operations on each item in a list.

### Creating lists
Lists are denoted using square brackets, with the items separated by commas.  The code below will create and print a populated
list called `areas`.
~~~
areas = [6929.6, 8536.47, 11359.3, 17743.4]
print('Areas are:', areas)
~~~
{: .language-python}

We can also make lists of strings, or even lists of lists!
~~~
samples = ['Trial16', 'Trial20', 'Trial293']
print('Sample names are:', samples)
~~~
{: .language-python}

It can also be useful to make an empty list:
~~~
plateCounts = []
print('The plate counts are:', plateCounts)
~~~
{: .language-python}
This will seem more useful after we have talked about adding items to lists!

### Modifying lists: adding, removing, and altering values
Add/delete objects (list.append(value), list.remove(value)

Unlike floats, ints, and strings, lists can be modified after we make them.  For example, we can add objects using the append 
command:
~~~ 
print('Before:', samples)
~~~
{: .language-python}

Returns the output
~~~
 ('Before:', ['Trial16', 'Trial20', 'Trial293'])
~~~
{: .output}

Now, add an item:
~~~
samples.append('Trial17')
print("After:", samples)
~~~ 
{: .language-python}

This returns the output
~~~
('After:', ['Trial16', 'Trial20', 'Trial293', 'Trial17'])
~~~
{: .output}

We can even make an empty list and add objects to it!

~~~
genotypes = []
genotypes.append('Mo17')
genotypes.append('B73')
print(genotypes)
~~~
{: .language-python}

Returns the output
~~~
['Mo17', 'B73']
~~~
{: .output}

We can also modify a list by removing items

~~~
print("Samples before:", samples)
samples.remove('Trial20')
print("Samples after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('Samples before:', ['Trial16', 'Trial20', 'Trial293', 'Trial17'])
('Samples after:', ['Trial16', 'Trial293', 'Trial17'])
~~~
{: .output}

### 0-based list indexing
We can also access specific items of the list based on their position in the list.  We can use the list name followed by the 
number of the position we want in square brackets.

What do you think `samples[1]` will result in?
~~~
print(samples[1])
~~~
{: .language-python}

This code returns the output
~~~
'Trial293'
~~~
{: .output}

Notice that giving the index “1” returned the second item in the list.  This is because Python (like many programming languages) 
begins counting at 0.  

> ## List Indexing
> How would you get the first item in the list `samples`?  How would you get the last item?
> > ## Solution
> > ~~~
> > print(samples[0]) #Returns the first item, at index position 0
> > print(samples[2]) #Returns the first item, at index position 2 (the list contains 3 items)
> > ~~~
> > {: .language-python}
> > `samples[0]` returns the output `'Trial16'` and `samples[2]` returns the output `'Trial17'`.
> {: .solution}
{: .challenge}

> ## Using -1 and negative indexes to count backwards
> The index -1 is a special index that always refers to the last item of the list.
> Similarly, we can use other negative numbers to count backwards from the end of a list.  This can be very useful if we know 
> we want to get items from the end of a list, but we don't know the list's length!
> 
> ~~~
> print(samples[-1])
> ~~~
> {: .language-python}
>
> Returns the output
> ~~~
> 'Trial17'
> ~~~
> {: .output}
{: .callout}

> ## List Indexing With Negative Numbers
> How would you use negative numbers to get the next-to-last item in the list `samples`?  How would you get the third-to-last 
> item?
> > ## Solution
> > ~~~
> > print(samples[-2]) #Returns the next-to-last item
> > print(samples[-3]) #Returns the third-to-last item (which is the same as the first item in this example)
> > ~~~
> > {: .language-python}
> > `samples[-2]` returns the output `'Trial293'` and `samples[-3]` returns the output `'Trial16'`.
> {: .solution}
{: .challenge}

We can also use list indexing to replace specific items in the list.  For example,

~~~
samples = ['Trial16', 'Trial293', 'Trial17']
print("List before:", samples)
samples[2] = 'Trial216'
print("List after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('List before:', ['Trial16', 'Trial293', 'Trial17'])
('List after:', ['Trial16', 'Trial293', 'Trial216'])
~~~
{: .output}

### Accessing a range of objects with slicing (up to, but not inclusive)
We can also use similar syntax to return a slice or subsection of the list.  We separate the first and last indices for the 
items we want with a colon.  Note that the second index is up to, but not inclusive.  For example,
~~~
areas = [6929.6, 8536.47, 11359.3, 17743.4]
areas[0:2]
 ~~~
{: .language-python}

Returns the output
~~~
 [6929.6, 8536.47]
~~~ 
{: .output}

This returns a list of `areas[0]` and `areas[1]`.  It does not include `areas[2]`.

If we want to start at the beginning of the list, we can leave out the first coordinate.  Similarly, if we want to start our slice at a specific index and go to the end of the list, we can leave out the second coordinate.
~~~
print(areas[:2])
print(areas[1:])
~~~
{: .language-python}

Returns the output
~~~
[6929.6, 8536.47]
[8536.47, 11359.3, 17743.4]
~~~
{: .output}

### Finding the length of a list 
We may not always know (or remember) the length of a list.  If we need to get this number, we can use the `len()` function to 
find it.
~~~
print('The length of areas is:', len(areas))
~~~
{: .language-python}

Returns the output
~~~
The length of areas is 4
~~~~
{: .output}

Note that this returns the expected length of the list.  Even though `areas[3]` is the last item of the list (0-based counting!), the length is returned as 4.

We can also use similar indexing principles to access specific characters or substrings of a string variable 

## Exercises
> ## Indexing characters in a string
> Assume you have the following variable: 
> `element = 'oxygen'`
> What are the values of  
>     1. `element[:4]`  
>     2. `element[4:]`  
>     3. `element[:]`  
> > ## Solution
> > Create code with print statements to try this out.
> > 1. `element[:4]` starts at the beginning of the list and goes up to (but does not include) position 4, returning `'elem'`
> > 2. `element[4:]` starts at position 4 (`'e'`) and goes through the end of the string, returning `'ent'`
> > 3. `element[:]` starts at the beginning and goes through the end of the string, returning `'element'`
> {: .solution}
{: .challenge}
