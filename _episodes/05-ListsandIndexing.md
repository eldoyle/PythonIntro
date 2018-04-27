---
title: "Lists and Indexing"
teaching: 0
exercises: 0
questions:
- "How can we group similar values into one variable?"

objectives:
- "Learn to create lists to group similar values or items together"
- "Learn to modify lists by adding or deleting items"
- "Be able to access a specific item or items in a list using list indexing"
keypoints:
- "Lists can be used to group numbers (ints or floats), strings, or other kinds of values together in one variable"
- "Lists are ordered- objects stay in the order you add them"
- "Lists are indexed using 0-based indexing"
---
1. Numbers and strings let us store 1 piece of data in a single variable.  However, it is often useful to store multiple pieces of data in a single variable.  For example, image we have root areas for 4 different roots.  Instead of making 4 different variables, we can use a list to keep them all together.  This is also handy because we only have to keep track of one variable name! 

2. Lists are created using square brackets, with the items separated by commas

3. Creating a list (populated or empty)
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

4. Add/delete objects (list.append(value), list.remove(value)

Unlike floats, ints, and strings, lists can be modified after we make them.  For example, we can add objects using the append command

~~~ 
print('Before:', samples)
~~~
{: .language-python}

Returns the output
~~~
 ('Before:', ['Trial16', 'Trial20', 'Trial293'])
~~~
{: .output}

~~~
samples.append('Trial17')
print("After:", samples)
~~~ 
{: .language-python}

Returns the output
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
~~~
{: .language-python}

Returns the output
~~~
('Samples before:', ['Trial16', 'Trial20', 'Trial293', 'Trial17'])
~~~
{: .output}


~~~
samples.remove('Trial20')
print("Samples after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('Samples after:', ['Trial16', 'Trial293', 'Trial17'])
~~~
{: .output}

5. 0-based list indexing

..* We can also access specific items of the list based on their position in the list.  We can use the list name followed by the number of the position we want in square brackets.

..* Accessing 1 object
What do you think samples[1] will result in?

~~~
samples[1]
~~~
{: .language-python}

Returns the output
~~~
'Trial293'
~~~
{: .output}

Notice that giving the index “1” returned the second item in the list.  This is because Python (like many programming languages) begins counting at 0.  

How would you get the first item in the list samples?  How would you get the last item?

~~~
samples[0]
~~~
{: .language-python}

Returns the output
~~~
'Trial16'
~~~
{: .output}

Seperate the two questions to split out these two seperate coding instructions??

~~~
samples[2]
~~~
{: .language-python}

Returns the output
~~~
'Trial17'
~~~
{: .output}

Note that we can always use the index -1  to get the last item of a list if we don’t know it’s length

~~~
samples[-1]
~~~
{: .language-python}

Returns the output
~~~
'Trial17'
~~~
{: .output}

We can use this to replace specific items in the list.  For example,

~~~
print("List before:", samples)
~~~
{: .language-python}

Returns the output
~~~
('List before:', ['Trial16', 'Trial293', 'Trial17'])
~~~
{: .output}

~~~
samples[2] = 'Trial216'
~~~
{: .language-python}

~~~
print("List after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('List after:', ['Trial16', 'Trial293', 'Trial216'])
~~~
{: .output}

6. Accessing a range of objects (up to, but not inclusive)
We can also use the same syntax to return a slice or subsection of the list.  We separate the first and last indices for the items we want with a colon.  Note that the second index is up to, but not inclusive.  For example,
~~~
 areas[0:2]
 ~~~
{: .language-python}

Returns the output
~~~
 [6929.6, 8536.47]
~~~ 
{: .output}

This returns a list of areas[0] and areas[1].  It does not include areas[2].

If we want to start at the beginning of the list, we can leave out the first coordinate.  Similarly, if we want to start our slice at a specific index and go to the end of the list, we can leave out the second coordinate.
~~~
areas[:2]
~~~
{: .language-python}

Returns the output
~~~
[6929.6, 8536.47]
~~~
{: .output}

~~~
areas[1:]
~~~
{: .language-python}

Returns the output
~~~
[8536.47, 11359.3, 17743.4]
~~~
{: .output}

7. Len() function
We may not always know (or remember) the length of a list.  If we need to get this number, we can use the len() function to find it.
~~~
len(areas)
~~~
{: .language-python}

Returns the output
~~~
4
~~~~
{: .output}

Note that this returns the expected length of the list.  Even though 'areas[3]' is the last item of the list (0-based counting!), the length is returned as 4.

8. We can also use similar indexing principles to access specific characters or substrings of a string variable 
