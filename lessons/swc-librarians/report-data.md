---
layout: lesson
root: ../..
title: Working with Report Data (Excel or Director's Station)
---

## Opening

Librarians often find themselves working with speadsheets, in particular,
Excel files.  Excel is the most popular spreadsheet software.  Spreadsheets
are designed to store and analyze tabular or categorized data.  Librarians
also use a tool called Director's Station that allows creation of 
reports of library data.

While these two tools can be useful, there are some limitations

- They often require repetative tasks to be performed in creation of reports
- They cost money to purchase licenses
- A librarian may need to learn two sets of skills - one for Excel, one
 for Director's station - to perform very similar tasks

By coupling learning how to program in a general-purpose language like Python 
with an understanding of how data is stored, a librarian can learn to automate
tasks to save time and to overcome new obstacles they
discover in either Excel, Director's Station or any other software tool.

The rest of this chapter will explore how to use Python to manipulate
library-related data.  We acknowledge that not all librarians use the same
tools, but we have designed this lessons to be as general as possible.

## A simple example

Consider a the following data as an example of a spreadsheet that a librarian
may find themself working with.

![]({{page.root}}/lessons/swc-librarians/images/excel.png)

Eventually, we will get to the point where can know how many holds 
there are on Ender's Game.

    List Titles with Holds,,,,,,,,
    Holds,Title,Author,Hold Created Date,Hold Placed Lib,Item Library,Pickup Library,Item Type,Availability
    1,RED 2,Malkovich, John,2014-05-14 0:00,EPLWMC,EPLLHL,EPLRIV,DVD7,Not Available
    1,ENDER'S GAME,Card, Orson Scott,2014-05-12 0:00,EPLWMC,EPLLHL,EPLWMC,BOOK,Available
    1,GRAMMY NOMINEES N2012,,2014-05-14 0:00,EPLWMC,EPLMNA,EPLWMC,CD,Not Available
    1,GRAMMY NOMINEES N2011,,2014-05-14 0:00,EPLWMC,EPLLON,EPLWMC,CD,Not Available
    1,GRAMMY NOMINEES N2014,,2014-05-14 0:00,EPLWMC,EPLMNA,EPLWMC,CD,Not Available
    1,GRAMMY NOMINEES N2007,,2014-05-14 0:00,EPLWMC,EPLLON,EPLWMC,CD,Not Available
    1,THE STORY OF ASTRONOMY,Aughton, Peter,2014-05-14 0:00,EPLWMC,EPLMNA,EPLWMC,BOOK,Not Available
    1,GRAMMY NOMINEES N2009,,2014-05-14 0:00,EPLWMC,EPLCPL,EPLWMC,CD,Not Available
    2,ENDER'S GAME,Hood, Gavin,2014-05-13 0:00,EPLWMC,EPLZORDER,EPLWMC,JDVD7,Not Available
    1,RAYGUN COWBOYS,Raygun Cowboys,2014-05-14 0:00,EPLWMC,EPLCSD,EPLWMC,CD,Not Available
    1,GRAMMY NOMINEES N2010,,2014-05-14 0:00,EPLWMC,EPLLON,EPLWMC,CD,Not Available
    1,ALLOSAURUS A WALKING WITH,Branagh, Kenneth,2014-05-13 0:00,EPLWMC,EPLLHL,EPLWMC,DVD7,Not Available
    1,AMAZING MAGIC TRICKS BEGINNER LEVEL,Barnhart, Norm,2014-05-13 0:00,EPLWMC,EPLABB,EPLWMC,JBOOK,Not Available
    1,BLUESAMERICANA,Mo, Keb,2014-05-13 0:00,EPLWMC,EPLZORDER,EPLWMC,CD,Not Available
    1,BRAVE,Chapman, Brenda,2014-05-13 0:00,EPLWMC,EPLWOO,EPLJPL,JDVD7,Not Available
    1,BREAKAWAY,Hirsch, Jeff,2014-05-13 0:00,EPLWMC,EPLSTR,EPLSTR,JCD,Available
    1,CLASSIC CANADIAN ROCK,,2014-05-13 0:00,EPLWMC,EPLMLW,EPLWMC,CD,Not Available
    1,CRASH MY PARTY,Bryan, Luke,2014-05-13 0:00,EPLWMC,EPLLHL,EPLMLW,CD,Not Available
    1,CREATIVE SEED BEAD CONNECT, JUMP RINGS, AND C,Meister, Teresa,2014-05-13 0:00,EPLWMC,EPLMNA,EPLWMC,BOOK,Intransit
    1,DANCE PARTY 2013 [14 ESSENTIAL HITS,Cash, Cory,2014-05-13 0:00,EPLWMC,EPLLON,EPLWMC,CD,Not Available
    1,ENDER'S GAME,Card, Orson Scott,2014-05-07 0:00,EPLWMC,EPLWMC,EPLWMC,BOOK,Available
    1,DIGGING CANADIAN HISTORY,Grambo, Rebecca,2014-05-13 0:00,EPLWMC,EPLMLW,EPLWMC,JBOOK,Not Available
