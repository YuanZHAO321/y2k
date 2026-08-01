---
title: "Lecture4_25"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 4/Lecture4_25.pdf"
type: pdf
---

<!-- Start of picture text -->
part 3 - modules and functions<br><!-- End of picture text -->

coding the game practical 4

###### 'Vanilla' Python

Data types Loops Basic operations Conditionals **~~1 2~~**

# course layout

**~~3 4 5~~**

The Numpy Conway's Game Differential module Of Life Equations

Modules and Functions

###### Pandas and data discovery

Geospatial analysis

Statistical Cluster Analysis Analysis

**~~6 7 8 9~~**

<!-- Start of picture text -->
Creating a notebook assessment<br>select topic from weeks 4 - 9<br>10 11 12<br><!-- End of picture text -->

lecture + practical. Solutions are given

## recap

##### • Functions help us repeat a set of operations many times - They are speci�ed using ‘def’ and ‘return’ statements

- Modules contain functions we can access using the ‘.’ operator

- The Numpy module is the standard way to deal with numerical operations in Python

why do we recognise certain patterns?

## conways game of life

**John Horton Conway** (26 December 1937 - 11 April 2020) was an English mathematician active in the theory of �nite groups, number theory, combinatorial game theory and coding theory. He has also made contributions to many branches of recreational mathematics, most notably the invention of the cellular automaton called the Game of Life.

## conways game of life

**Every cell interacts with its neighbours, whether they are horizontally, vertically of diagonally adjacent. There are 4 laws that de�ne these interactions:**

- **Any live cell with fewer than two live neighbours dies, as if by underpopulation.**

- • **Any live cell with two or three live neighbours lives on to the next generation.**

- • **Any live cell with more than three live neighbours dies, as if by overpopulation.**

- • **Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.**

**�rst, de�ne a space and shape of species…**

conways game of life

<!-- Start of picture text -->
part 3 - modules and functions<br><!-- End of picture text -->

#### conways game of life

<!-- Start of picture text -->
practical 4<br><!-- End of picture text -->

## 1) Define a 2D array as your space and then populate each value with a 1 or 0.

## e.g. a ‘Block’, ‘Tub’ and ‘Boat’

## 2) Populate a 2D Universe with our species

##### e.g. a 10 x 23 Universe

What Python commands do we need to use to initialize the above?

## 3) Search the 2D Universe to find how many live or dead [1 or 0’s] neighbour’s [cells] each cell has.

<!-- Start of picture text -->
row<br><!-- End of picture text -->

**column**

**0 1** 2 **3 4 5 6 0 1** 2 **3 4 5 6**

## 4) Search the 2D Universe to find how many live or dead [1 or 0’s] neighbour’s [cells] each cell

has.

## 5) Perform one pass across the entire 2D space

- Any live cell with fewer than two live neighbours dies, as if by underpopulation.

- Any live cell with two or three live neighbours lives on to the next generation.

- Any live cell with more than three live neighbours dies, as if by overpopulation.

- • Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.

lets use a function that we can call over and over......

Iterate over a function that searches and changes our Universe.....

## endless creative opportunities...

<!-- Start of picture text -->
Lecture 4                                                   summary<br><!-- End of picture text -->

### conways game of life

- Is based on 4 rules of life in a 2D universe

- Requires us to search and count in speci�c locations

- Requires us to modify existing values in arrays

- Combines the above using condition statements and FOR loops

<!-- Start of picture text -->
practical 4                                               goals<br><!-- End of picture text -->

### code

- Create different shapes through 2D Numpy array modi�cations

- Create a function that searches a local neighbourhood for values of '1' and '0'

- Populating Conway's Universe with multiple species

### general experience

- Learn by working on a speci�c problem - often the best way!

-

- Start to think about how you check for correct behaviour in working code
