---
title: "Lists and Indexing"
teaching: 0
exercises: 0
questions:
- "Add question"

objectives:
- Add main objective
- 
- 
keypoints:
- "First key point."
---
## Numbers and strings let us store 1 piece of data in a single variable.  However, it is often useful to store multiple pieces of data in a single variable.  For example, image we have root areas for 4 different roots.  Instead of making 4 different variables, we can use a list to keep them all together.  This is also handy because we only have to keep track of one variable name! 

## Lists are created using square brackets, with the items separated by commas

## Creating a list (populated or empty)
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

## Add/delete objects (list.append(value), list.remove(value)

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

## 0-based list indexing

We can also access specific items of the list based on their position in the list.  We can use the list name followed by the number of the position we want in square brackets.

## Accessing 1 object
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


