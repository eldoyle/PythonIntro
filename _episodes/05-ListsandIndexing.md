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
However, it is often useful to store multiple pieces of data in a single variable.  For example, image we have calculated total 
colony are in pixels for four different images of plates.  Instead of making four different variables, we can use a list to keep 
them all together.  This is handy because we only have to keep track of one variable name! In the [next lesson]({{ page.root }}\06-Loops) 
you'll learn how to perform the same operations on each item in a list.

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
samples = ['Plate16', 'Plate20', 'Plate293']
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
 ('Before:', ['Plate16', 'Plate20', 'Plate293'])
~~~
{: .output}

Now, add an item:
~~~
samples.append('Plate17')
print("After:", samples)
~~~ 
{: .language-python}

This returns the output
~~~
('After:', ['Plate16', 'Plate20', 'Plate293', 'Plate17'])
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
samples.remove('Plate20')
print("Samples after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('Samples before:', ['Plate16', 'Plate20', 'Plate293', 'Plate17'])
('Samples after:', ['Plate16', 'Plate293', 'Plate17'])
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
'Plate293'
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
> > `samples[0]` returns the output `'Plate16'` and `samples[2]` returns the output `'Plate17'`.
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
> 'Plate17'
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
> > `samples[-2]` returns the output `'Plate293'` and `samples[-3]` returns the output `'Plate16'`.
> {: .solution}
{: .challenge}

We can also use list indexing to replace specific items in the list.  For example,

~~~
samples = ['Plate16', 'Plate293', 'Plate17']
print("List before:", samples)
samples[2] = 'Plate219'
print("List after:", samples)
~~~
{: .language-python}

Returns the output
~~~
('List before:', ['Plate16', 'Plate293', 'Plate17'])
('List after:', ['Plate16', 'Plate293', 'Plate219'])
~~~
{: .output}

### Accessing a range of objects with slicing (up to, but not inclusive)
We can also use similar syntax to return a slice or subsection of the list.  We separate the first and last indices for the 
items we want with a colon.  Note that the second index is up to, but not inclusive.  For example,
~~~
areas = [6929.6, 8536.47, 11359.3, 17743.4]
print(areas[0:2])
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
print(areas[:2]) #starts at the beginning and includes indexes 0 and 1, but not 2  
print(areas[1:]) #starts at index 1 and goes through the end of the list
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

We can also use similar indexing principles to access specific characters or substrings of a string variable. 

## Exercises
> ## Indexing characters in a string
> Assume you have the following variable: 
> `element = 'oxygen'`
> What are the values of the following?   
>     1. `element[:4]`  
>     2. `element[4:]`  
>     3. `element[:]`  
> > ## Solution
> > Create code with print statements to try this out.
> > 1. `element[:4]` starts at the beginning of the list and goes up to (but does not include) position 4, returning `'oxyg'`
> > 2. `element[4:]` starts at position 4 (`'e'`) and goes through the end of the string, returning `'en'`
> > 3. `element[:]` starts at the beginning and goes through the end of the string, returning `'oxygen'`
> {: .solution}
{: .challenge}

> ## String and list indices
> Assume you have the following variable: 
> `element = 'oxygen'`
> Explain what `element[1:-1]` does.
> > ## Solution
> > If you create and run code with a print statement, you'll get the following output:
> > `element[1:-1]` will return all but the first and last characters: `'xyge'`.  
> > 
> > Remember that position 1 is the *second* character of the string (0-based counting!) and that the slice goes *up to*, but 
> > *doesn't include* the character at the index position after the colon.  Since `element[-1]` refers to the last character, 
> > the slice will stop just before `'n'`, and only include up to the 'e' at the next-to-last position.
> {: .solution}
{: .challenge}

> ## Adding a value to a list
> Assume you have the following list: 
> `areas = [8536.47, 11359.3, 17743.4]`  
> Create a new empty list  
> `areas2 = []`  
> Now add items to `areas2` so that it is identical to `areas` except that 7798.02 has been inserted between 8536.47 and 
> 11359.3.  You should refer to the list `areas` and avoid typing in numbers whenever possible.
> 
> The final value of `areas2` should be `areas2 = [8536.47, 7798.02, 11359.3, 17743.4]`
> > ## Solution
> > ~~~ 
> > #Create the list areas
> > areas = [8536.47, 11359.3, 17743.4]
> > 
> > #Create the empty list areas2
> > areas2 = []
> > 
> > #Now, add items to areas2
> > areas2.append(areas[0])
> > areas2.append(7798.02)
> > areas2.append(areas[1])
> > areas2.append(areas[2])
> > 
> > #print areas and areas2
> > print('the value of areas is', areas)
> > print('the value of areas2 is', areas2)
> > ~~~
> > {: .language-python}
> > Note that this did not change the original list areas!
> >
> > You could also do it like this, using the `.insert()` command
> > ~~~ 
> > #Create the list areas
> > areas = [8536.47, 11359.3, 17743.4]
> > 
> > #Create the list areas2 by copying areas
> > areas2 = areas
> > 
> > #Now, use the insert command to insert the new number at index 1
> > areas2.insert(1, 7798.02)
> > 
> > #print areas and areas2
> > print('the value of areas is', areas)
> > print('the value of areas2 is', areas2)
> > ~~~
> > However, this will also change the original list `areas`!  This is because `areas2=areas` does not create a brand-new copy
> > of the list.  Instead, it points to the same location in memory as the original variable name `areas`.
> > {: .language-python}
> {: .solution}
{: .challenge}
