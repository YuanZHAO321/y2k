---
title: "Lecture2-DEES-Programming-2025"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 2/Lecture2-DEES-Programming-2025.pdf"
type: pdf
---

# part 2 - loops and conditionals

conditional statements nested loops [loops in more than one dimension] practical 2

###### 'Vanilla' Python

Data types Loops Basic operations Conditionals **1 2 3 4 5**

<!-- Start of picture text -->
1<br><!-- End of picture text -->

<!-- Start of picture text -->
2<br><!-- End of picture text -->

<!-- Start of picture text -->
3<br><!-- End of picture text -->

<!-- Start of picture text -->
4<br><!-- End of picture text -->

<!-- Start of picture text -->
5<br><!-- End of picture text -->

The Numpy Conway's Game Differential module Of Life Equations Modules and Functions

course layout lecture + practical. Solutions are given

###### Pandas and data discovery

Geospatial analysis Statistical Cluster Analysis Analysis **6 7 8 9**

<!-- Start of picture text -->
6<br><!-- End of picture text -->

<!-- Start of picture text -->
7<br><!-- End of picture text -->

<!-- Start of picture text -->
8<br><!-- End of picture text -->

<!-- Start of picture text -->
9<br><!-- End of picture text -->

<!-- Start of picture text -->
10<br><!-- End of picture text -->

<!-- Start of picture text -->
11<br><!-- End of picture text -->

<!-- Start of picture text -->
12<br><!-- End of picture text -->

### recap

- Programming is great. Multiple languages, each with their own syntax [set of rules and style]

- We write 'source code' as our software. Code is the text behind our novel!

- We can write python in a seperate .py file, but we will be using Jupyter notebooks in this course

##### multiple data types

- We can store individual float and integers [and strings...]

- We can store entries in an array, called a list in Vanilla Python, and modify/add entries

- Indexing starts at 0

##### behind the scenes, the hardware dictates the range of numbers/words we can work with

The third generation of video game consoles, also referred to as the 8- bit era, began in 1983.

### recap

- Programming is great. Multiple languages, each with their own syntax [set of rules and style]

- We write 'source code' as our software. Code is the text behind our novel!

- We can write python in a seperate .py file, but we will be using Jupyter notebooks in this course

##### loops

- Rather than manually access values/entries, we can access and modify by ‘looping’ through our arrays

### 'for' loops

A feature of every programming language. Iterating over components of an array and performing an action or modifying an entry

<!-- Start of picture text -->
4<br><!-- End of picture text -->

<!-- Start of picture text -->
5<br><!-- End of picture text -->

<!-- Start of picture text -->
6<br><!-- End of picture text -->

<!-- Start of picture text -->
0<br><!-- End of picture text -->

<!-- Start of picture text -->
1<br><!-- End of picture text -->

<!-- Start of picture text -->
2<br><!-- End of picture text -->

<!-- Start of picture text -->
3<br><!-- End of picture text -->

Can be any name I want The variable adopts the same format as the array/iterable it is searching across

# part 2 - loops and conditionals

##### 'for' loops

nested loops [loops in more than one dimension] practical 2

### Conditional statements: The IF, ELIF and ELSE statements

Changing the flow of a program using basic logic very important

Examples include:

- Waiting for user input

- Detecting a certain type of input - Knowing when to change theory - Stopping a process in risk mitigation

- Can operate on numeric and non-numeric examples - Wait for maximum/minimum values

- - Select specific entry in database - Search for existence of entry

<!-- Start of picture text -->
CONDITION<br>TRUE? FALSE?<br>DO THIS DO THAT<br>CONDITION 1<br>FALSE?<br>TRUE?<br>DO THIS CONDITION 2<br>TRUE? FALSE?<br>DO THIS DO THAT<br><!-- End of picture text -->

### Conditional statements: The IF, ELIF and ELSE statements

Changing the flow of a program using basic logic very important

Examples include:

- Waiting for user input

- Detecting a certain type of input - Knowing when to change theory

- Can operate on numeric and non-numeric examples - Wait for maximum/minimum values

- - Select specific entry in database - Search for existence of entry

###### e.g. two ways to perform the same operation using just IF or combination of IF and ELSE

Notice the use of comments using the # symbol and also the correct use of the : operator

###### e.g. How might we change equation to calculate variable ‘Y’ according to the value of ‘X’

We have two variables 'x' and 'y'. Each has 50 elements and thus we represent in a list, or array. Lets assume that we want to implement two functions:

- one that is used if our x value is less than or equal to 20

- the other if x is greater than 20. We can use a combination of the IF and ELSE statements.

## the 'and' statement

Once we move beyond two mutually exclusive conditions, we can also use the ELIF statements. However we need to be careful that we are assigning correct boundaries on our conditions. For example, what if we wanted to check the following conditions: If variable x < 20,                                    perform action1 If variable x >= 20 but <= 60,                perform action2 If variable x > 60,                                    perform action 3 is the following correct?

## the 'and' statement

If variable x < 20,                                   perform action1 If variable x >= 20 but <= 60,               perform action2 If variable x > 60,                                   perform action 3 is the following correct?

Code that works isnt necessarily correct!!

# part 2 - loops and conditionals

recap and 'for' loops conditional statements

practical 2

## nested loops: Working with more than 1 dimension

In many cases we want to work with more than one variable at a time, often in a two [or more] dimensional setting. We can combine 'FOR' loops on any number of levels.

We can use conditional statements to refine the process

## nested loops: Working with more than 1 dimension

In many cases we want to work with more than one variable at a time, often in a two [or more] dimensional setting. We can combine 'FOR' loops on any number of levels.

<!-- Start of picture text -->
0<br><!-- End of picture text -->

<!-- Start of picture text -->
1<br><!-- End of picture text -->

<!-- Start of picture text -->
step1 0 1<br>step2 0 1 2 3 4 5 6<br><!-- End of picture text -->

<!-- Start of picture text -->
0<br><!-- End of picture text -->

<!-- Start of picture text -->
1<br><!-- End of picture text -->

<!-- Start of picture text -->
2<br><!-- End of picture text -->

<!-- Start of picture text -->
3<br><!-- End of picture text -->

<!-- Start of picture text -->
4<br><!-- End of picture text -->

<!-- Start of picture text -->
5<br><!-- End of picture text -->

<!-- Start of picture text -->
6<br><!-- End of picture text -->

## nested loops: Working with more than 1 dimension

In many cases we want to work with more than one variable at a time, often in a two [or more] dimensional setting. We can combine 'FOR' loops on any number of levels.

# part 2 - loops and conditionals

##### 'for' loops

conditional statements nested loops [loops in more than one dimension]

# Lecture 2                                                  summary

#### 'FOR' loops

- Allow us to move through lists and arrays sequentially

- Can work with appropriate indices [e.g. x[1] ] to add or modify elements

- Can have different 'nested' levels

#### conditional statements

- Allow us to check if a condition is true

- Allow us to change the flow of our code

- Work by using a range of operators [e.g. if x == y]

- Working code does not mean it is correct

# practical 2                                               goals

#### code

- Start to work with FOR loops

- Use conditional statements: IF, ELSE and ELIF

- Nested loops: Start working with more than 1 dimension

#### general experience

- Build more complex workflows into your code

- Make code responsive to change of status/input
