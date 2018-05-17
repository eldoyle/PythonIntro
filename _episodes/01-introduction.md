---
title: "Introduction"
teaching: 30
exercises: 0
questions:
- "Why learn Python?"
objectives:
- "Understand \"Why Python?\""
- "Be introduced to some of the examples you will see throughout the DIVAS workshop."
keypoints:
- "The best way to learn to code is by actually writing code to solve a problem."
- "You don't have to remember every single detail of each episode or exercise."
---

The ability to write your own computer code to analyze data is a great skill for any scientist to have!  By taking the time to 
write few lines of code, you can analyze experimental data, organize your files, automate repetitive number-crunching tasks, and 
create workflows that will be transparent, reproducible, and easily shared with colleagues and collaborators.

The goal of these workshops is to help you get your coding "feet" wet, by learning some basic Python programming skills.  Then, 
you'll move on to apply those skills to real image data sets.

## Why Python?

Python is a programming language that is commonly used in the natural sciences to create workflows and analyze data. Although you 
should use whatever programming language makes sense for your work, Python has several advantages:
1. Python is an open-source language that is freely available
2. Python runs on almost all computing platforms and environments
3. Python has a growing base of scientific users!  There are numerous online resources and examples available
4. Python is relatively easy for new users to learn
5. Python has a variety of tools available for image processing and computer vision, including the [OpenCV]( https://docs.opencv.org/) library.

> ## Learn the language that makes the most sense for you! 
> Although Python is commonly used in the natural sciences, different communities of scientists may have a different "preferred" 
> programming language.  You should learn and use the language that is common in your community, so that will be easier to share
> and collaborate on code with your colleagues.
> 
> Fortunately, the basic concepts and ideas you are learning in Python will also be present in another programming language!  
> Once you've learned one, picking up another language will be much easier.
{: .callout}

## The examples
The best way to learn Python is to read, write, and experiment with Python code that solves real problems!  To help you do this,
we will focus on two image-based examples.

### Example 1: Bactera growing on a plate
The images below show a number of bacterial colonies growing on plates. Imagine that you have conducted a large experiment, with 
multiple plates growing under different conditions.  You might be interested in counting colonies on each plate, in computing
the total percent area covered by the bacterial colonies, or even tracking colony growth over time.  All of these tasks could be 
accomplished by a computer program!  And once you have analyed your images to get colony counts or total area, you could write 
and use a second program to analyze the data (for example, to compare colony number and total growth at different timepoints or
under different growth conditions).  

![Plate1](../fig/00-colonies01.jpg)       
![Plate3](../fig/00-colonies03.jpg)

### Example 2: Analyzing a titration 
The video below (click on the image to see the video) shows the progress of a titration reaction.  Rather than watch the 
reaction's progress yourself, you could write a program to monitor the color of the solution, graph the change in color over 
time, and even send you a an alert notification when the reaction is complete!

[![Titration video](../fig/00-titration.jpg)](https://youtu.be/NLSY5S8CABk?t=554)

### Image processing and data analysis in a single workflow 
As you work through the Python Intro tutorials, you will encounter these examples at different points.  At each point, you will
be asked to apply the tools you have just learned to tackle analysis of one of these image-based data sets.  For our purposes
of learning basic Python skills, we will assume that you have already analyzed the images: that is, you have already counted 
colonies on a plate or measured solution color at different timepoints. This set of tutorials will help you build the skills to
analyze the data collected from the images.  

Later in the [Image Processing](https://mmeysenburg.github.io/image-processing/) tutorials, you will learn how to write code to
do image processing: for example, to write code that will "look" at an image and count colonies, or write the code that will
measure solution color every few seconds.

When put together, these two sets of skills will allow you to construct complete workflows that allow you to collect data and 
measurements directly from images and then output and analyze the data to answer experimental questions.

> ## How to use these lessons
> It would be impossible for us to cover every single programming or Python concept that you might need to know.  You also 
> shouldn’t expect yourself to remember every single thing that was covered.  The goal of these lessons is to expose you to some 
> fundamental concepts of programming, using Python,  Later when you need to accomplish a task you can remember that you 
> probably learned something about it, and then you can go look up the details in your notes or somewhere else on the internet.
>
> Just because we show you one way to do something doesn’t mean that’s the only way, or even the best way, to do it!  Good 
> programmers are constantly learning new ways to do things.
> 
> Don’t feel like you have to reinvent the wheel every time and write all of your code from scratch.  Someone has probably 
> written code that is similar to what you want to do, and it’s probably on the internet.  Just make sure you understand what 
> the code is doing before you copy it into your program!
{: .callout}  

Plate images are from the paper "High-throughput imaging of bacterial colonies grown on filter plates with application to serum 
bactericidal assays." Liu X, Wang S, Sendi L, Caulfield MJ.  J Immunological Methods, 2004. 
