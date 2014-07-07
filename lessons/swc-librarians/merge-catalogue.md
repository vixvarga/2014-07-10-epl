---
layout: lesson
root: ../..
title: Merging Catalogue Data from Two Files 
---

## Opening
Now that we've learned about loops and opening files, we're going to combine the two to solve a new problem.

##Our new problem
We have two files with different information about books in the database. One file contains information about the number of circulations each item has had, and a second file contains bibliographic information, namely the title and author of each item. 

	The files look like this:

	File 1:

	Item ID,Title,Author
	312210121823,A Canticle for Leibowitz,Walter M. Miller
	312210121212,Catching Fire,Suzanne Collins
	312210123281,Foundation Trilogy,Isaac Asimov
	312210121314,The Moon is a Harsh Mistress,Robert A. Heinlein

	File 2:
	Item ID,Checkouts
	312210121212,5
	312210121823,4
	312210121314,2
	312210123281,1

You can download the sample files here:
File 1 - [title-auth.csv](files/title-auth.csv)
File 2 - [circ-id.csv](files/circ-id.csv)

###Why is this a problem?


##How to merge our dates
To solve our problem, we need to match each line in file 1 with the corresponding line in file 2. There is only one field that appears in both fields, Item ID, so we need to use this field to match lines between our files. We will do this by opening each file, looping through the contents, and printing out the lines that match each other.

###Building our program
####1. Opening the files
Our files ([title-auth.csv](files/title-auth.csv) and [circ-id.csv](files/circ-id.csv)) are stored in a file type called "comma separated values". As you can see above, commas separate each field on the lines of our document.

To begin working with our file, we must open it in our program. Whenever you open a file, you must also close it. It won't necessarily cause an error if you don't, but it is good practice to do so. We will open and close both files:

~~~ python
file1 = open('circ-id.csv')
file2 = open ('title-auth.csv')

file1.close()
file2.close()
~~~

Now, between opening and closing our files, we need to actually do something with them! We will start by reading file 1 line by line. We will do this by using a method built into python called readlines. We will store the output of this method in a new variable called file1_lines, and will print this variable to make sure we set the variable correctly.

~~~ python
file1 = open('circ-id.csv')
file2 = open ('title-auth.csv')

f1_lines = file1.readlines()
print f1_lines

file1.close()
file2.close()
~~~

When you run your program, you should get somethign like the following result:
	['Item ID,checkouts\n', '312210121212,5\n', '312210123281,1\n', '312210121314,2\n', '312210121823,4\n', '312210121284,7\n', '312210124153,18\n', '312210124153,3\n', '312210124812,4\n', '312210123691,9\n', '312210128794,7\n', '312210125321,14\n']

