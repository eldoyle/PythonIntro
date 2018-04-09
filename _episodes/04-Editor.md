---
title: "Running code in the editor"
teaching: 0
exercises: 0
questions:
- "How do we store data in variabes?"

objectives:
- "Be able to create variables"
- "Understand that different types of variables store different kinds of information"
- "Be able to perform simple arithmatic operations on variables"
keypoints:
- "First key point."
---


> ## Variable Switching
>
> Given the following two variables
> ~~~
> density1 = 4.59
> density2 = 3.28
> ~~~
> {: .language-python}
> write code to “switch” the values so that the final result is that
> ~~~
> density1 = 3.28
> density2 = 4.59
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > The trick here is to create a temporary variable so that the values stored are not "lost"
> >
> > ~~~
> > temp1 = density1
> > density1 = density2
> > density2 = temp1
> > print(density1, density2)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}
