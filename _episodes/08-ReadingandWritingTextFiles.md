---
title: "Reading and Writing Text Files"
teaching: 0
exercises: 30
questions:
- "Add Question"

objectives:
- "Add Objectives"
keypoints:
- "Add Keypoints"
---

Being able to open and read in files allows us to work with larger data sets, where it wouldn’t be possible to type in each and every value and store them as variables.  Writing files allows us to process our data and then save the output to a file so we can look at it later.

Right now, we will practice working with a comma-delimited text file (.csv) that contains several columns of data.  However, what you learn in this lesson can be applied to any general text file.  In the next lesson, you will learn another way to read and process .csv data.

### Paths to files
In order to open a file, we need to tell Python exactly where the file is located, relative to where Python is currently working (the working directory).  In Spyder, we can do this by setting our current working directory to the folder where the file is located.  Or, when we provide the file name, we can give a complete path to the file.

For now, we will set our working directory to the correct folder.

Set working directory (top right corner of the Spyder window)to 
`/home/diva/Desktop/divas/projects/002/morph03`

This is also where we will have to save and run our file opening script.

### Opening and reading files
We will open and read the file in three steps.  First, we will create a variable to hold the name of the file that we want to open.  Next, we will call a command to open the file.  Finally, we will actually read the data in the file into a variable so that we can process it.  When we are done, we should remember to close the file!

You can think of these three steps as being similar to checking out a book from the library.  First, you have to go to the catalog or database to find out which book you need.  Then, you have to go and get it off the shelf.  But in order to actually look at the information in the book, you actually have to read the words!

`#Create a variable for the file name
filename = “Root_Density_Data_full.csv”

#Open the file
#r tells Python we are opening the file to read it

infile = open(filename, ‘r’) 
#Store the file data in a variable
data = infile.read()

#Print the data in the file
print(data)

#close the file
infile.close()`

### There are a variety of commands to read in data from files.  

`infile.read()` will read in the entire file as a single string of text.
`infile.readline()` will read in one line at a time (each time you call this command, it reads in the next line).  `infile.readlines()` will read all of the lines into a list, where each line of the file is an item in the list.

Mixing these commands can have some unexpected results.

`#Create a variable for the file name
filename = “Root_Density_Data_full.csv”

#Open the file
infile = open(filename, ‘r’) 

#Print the first two lines of the file
print(infile.readline())
print(infile.readline())

#call infile.read()
print(infile.read())

#close the file
infile.close()`

Notice that  the `infile.read()`command started at the third line of the file, where the first two `infile.readline()` commands left off. 

In general, if you want to switch between the different commands, you should close the file and then open it again to start over.

Add New header here?
`infile.readlines()` will read all of the lines into a list, where each line of the file is an item in the list.  This is extremely useful, because it will allow us to loop through each line of the file.

`#Create a variable for the file name
filename = “Root_Density_Data_full.csv”

#Open the file
infile = open(filename, ‘r’) 

lines = infile.readlines() 

for line in lines:
	if ‘C’ in line:
		print(line) #print lines for control condition

infile.close()`

Since our data is in a .csv file, we can use the `split` command to separate each line of the file into a list.  This can be useful if we want to access specific columns of the file.  

`#Create a variable for the file name
filename = “Root_Density_Data_full.csv”

#Open the file
infile = open(filename, ‘r’) 

lines = infile.readlines() 

for line in lines:
	sline = line.split(‘,’)
		print(sline) #each line is now a list

infile.close()`
  
> ## Example
> For each line in the file, the MAX_WIDTH is stored in the 10th column (index 4 with our 0-based counting). 
> 
> When we called the readlines() command in the previous code, Python read in the contents of the file as a string.  If we want Python  > to recognize something as a number, we need to tell it this!  
> 
> For example, float(‘5.0’) will tell Python to treat the text string ‘5.0’ as the number 5.0.  int(sline[4]) will tell Python to treat > the text string stored in the 5th position of the list sline as an integer (non-decimal) number.
> 
> Modify the code above to only print the line if the MAX_WIDTH is less than 200.
> > ## Solution
> > Write solution  
> {: .solution}
{: .challenge}

