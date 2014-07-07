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
	<table>
		<tr><td>Item ID	</td><td>Title<td></td>Author</tr>
		<tr><td>312210121823</td><td>A Canticle for Leibowitz</td><td>Walter M. Miller, JR</td></tr>
		<tr><td>312210121212</td><td>Catching Fire</td><td>Suzanne Collins</td></tr>
		<tr><td>312210123281</td><td>I, Robot</td><td>Isaac Asimov</td></tr>
		<tr><td>312210121314</td><td>The Moon is a Harsh Mistress</td><td>Robert A. Heinlein</td></tr>
	</table>
	File 2:
	<table>
		<tr><td>Item ID</td><td>checkouts</td></tr>
		<tr><td>312210121212</td><td>5</td></tr>
		<tr><td>312210121823</td><td>4</td></tr>
		<tr><td>312210121314</td><td>2</td></tr>
		<tr><td>312210123281</td><td>1</td></tr>
	</table>

