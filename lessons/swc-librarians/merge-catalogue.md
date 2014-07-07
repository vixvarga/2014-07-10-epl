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

	**Item ID**		Title							*Author*
	312210121823	A Canticle for Leibowitz		Walter M. Miller, JR
	312210121212	Catching Fire					Suzanne Collins
	312210123281	I, Robot						Isaac Asimov
	312210121314	The Moon is a Harsh Mistress	Robert A. Heinlein

	File 2:
	*Item ID*		*Checkouts*
	312210121212	5
	312210121823	4
	312210121314	2
	312210123281	1

You can download the sample files here:
File 1 - [title-auth.csv](files/title-auth.csv)
File 2 - [circ-id.csv](files/circ-id.csv)

###Why is this a problem?


##How to merge our dates
Now that we understand the problem, how to solve it? Examining the 