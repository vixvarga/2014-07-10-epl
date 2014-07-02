---
layout: lesson
root: ../..
title: Processing a Circulation Card in Python 
---

This example is based on an exercise created by [Jessica Hamrick](https://github.com/jhamrick/library-exercise)

## Opening

After learning the basics of repetitive actions (Loops) and conditional statements (IFs), we now have enough material
to use Python to solve a problem.

## Our problem

Let's say that we have an old circulation card for a book that we want to have
in electronic form (a computer file) to make it searchable to have an online
history of books.  For example, consider the following
[card](http://2.bp.blogspot.com/-6VxNTXpOnoc/URh4RVpm6wI/AAAAAAAAPEQ/c6mhrcTgEiw/s1600/duedate.jpg).

If we translate this card to a text file, either manually or using some kind
of optical character recognition (OCR), we would end up with something like
the
[following](./files/library-card.txt).While
now electronic, we have a program with inconsistent data.  We can have dates
in the following three formats:

    Feb 16 53
    Jun 21 '54
    Sep 5 1961

As well, some librarians did not always use the next available space on the card, so some dates are out of order.

### Why is this a problem?

What are three questions we can ask about this circulation card?  I suggest the following:

- When was this copy in circulation?
- How long was this copy in circulation?
- What year was the most active for this book?
- Is a book about baseball more popular during baseball season?

To answer these questions we need to analyze the dates.  The point is that
a human could answer these questions in a few minutes looking at the card.
However, once programmed a computer can answer the question in within
thousandths of a second.  Considering we may have thousands of index cards,
programming will make answering the above questions possible whereas it would
unlikely be worth a librarians time.

Our goal is to turn raw data (the circulation card) into meaningful information (the answers to the questions above).

## Why fix the dates?

We need to have the dates in a consistent format in order to do math on them.
Let's look at our first question: *When was this book in circulation?*

Can we answer it?  The first checkout was Dec 17 '49, the last was June 28, 1962.  If we simply take the first and last date on the card, we are presuming the are in order.  What if the last few dates were out of order due to a lazy checkout person?

    Feb 3 1962
    Jun 28 1962
    Oct 3 1961

Then we would not have the correct starting and ending dates of circulation.  So we need to ensure the dates are
in order!  Could a person do this?  Yes, in a few minutes and they may make
a mistake.  But remember, a computer could do it in a few thousandths of
a second and is less likely to go crazy after the 1000 circulation card :)
Once we have the dates in order, we can answer our question accurately, which
is the whole point.

What about the second question:  *How long was this copy in circulation?*

If we have the dates in order, we still have a problem.  To find how many
years it was in circulation, we would subtract that the last date from the
first (1962 minus '49).  A human would know that this means our book was in
circulation for 13 years.  But computers have no intuition, they simple perform the
math they are programmed to.  So a computer program may be programmed naively to
perform the following subtraction

    1962 - 49

which would result in an inaccurate answer of **1913**.  Clearly a book would not survive for
19 centuries, but a computer would simply spit out the answer it's programmed
to calculate.  A computer does not have any intuition that '49 means 1949, so
it must be programmed to handle such a date.  These are the kind of bugs that
make software frustrating to use.

To get the correct total, 13, we need to have both dates in 4-digit format.  So we need to fix the dates.

Our point here is simply to express why thinking about data is a necessary programming skill.  There is an axiom in computer science "Garbage In, Garbage Out".  The principle behind it is that we must have good data in order to leverage
a computer's ability to process thousands of circulation card files and give us meaningful statistics and information.

Next, we'll learn how to apply what we've learned to convert the dates into a consistent format.

## How to Fix the Dates

Recalling that our problem is that we have three different formats of date
that make calculations incompatible.

    Feb 16 53
    Jun 21 '54
    Sep 5 1961

We'll walkthrough how to fix each of the first two so that they are all of the
format of the third, **Sep 5 1961**.  Specifically, we want "MMM DD YYYY"
where each month is the standard three character month, followed by a space,
a two digit day, followed by another space, then a 4-digit year.

### First, reading a file

Our circulation card is stored in a plain-text file named .

