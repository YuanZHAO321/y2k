---
title: "Lecture5_25"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 5/Lecture5_25.pdf"
type: pdf
---

<!-- Start of picture text -->
part 5 - modules and functions<br><!-- End of picture text -->

some examples practical 5

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

differential equations

## differential equations

##### integration

differentiation

sometimes, we can integrate by hand

sometimes, we cant

differential equations

differential equations

## differential equations

– - Coupled Differential Equations GeoGebra 28 February 2024

<!-- Start of picture text -->
3 views<br><!-- End of picture text -->

<!-- Start of picture text -->
45 sec<br><!-- End of picture text -->

�

<!-- Start of picture text -->
1.2�<br>45 sec ⚡ 37 sec<br><!-- End of picture text -->

## differential equations

There are many ODE solvers that can integrate coupled differential equations

Get Python to solve it!

There are ‘good’ default options, but you need to know a little about the problem you

Code design includes domain knowledge

differential equations

## differential equations

Using module documentation The most useful have examples as code so you can at least understand the required code structure Options can look like “gobble-de-gook”, until you practice running examples

<!-- Start of picture text -->
part 3 - modules and functions<br><!-- End of picture text -->

#### conways game of life

<!-- Start of picture text -->
practical 4<br><!-- End of picture text -->

## general structure for solving ODEs, using scipy

Import modules

De�ne a function to solve. The 'Right Hand Side' [RHS] De�ne a period to provide outputs Call the ODFE solver, with relevant options

## 1) e.g. simulating multiple instances of the radioactive decay equation

What do we need to import to solve this equation?

## 2) coupled differential equations

e.g. The Lorentz system

_In popular media the 'butter�y effect' stems from the real-world implications of the Lorenz attractor, i.e. that in any physical system, in the absence of perfect knowledge of the initial conditions (even the minuscule disturbance of the air due to a butter�y �apping its wings), our ability to predict its future course will always fail._

_The series does not form limit cycles nor does it ever reach a steady state. Instead it is an example of deterministic chaos. Two initial states no matter how close will diverge, usually sooner rather than later._

## 2) coupled differential equations - the lorentz system

Still define our ODE Still define a time period Still define initial conditions Now we pass an array to the ODE function and return an array

## 2) coupled differential equations - the predator-prey equations

Where the variables and constant parameters are de�ned as follows:

- U: number of preys

- V: number of predators (for example, foxes)

- • a is the natural growing rate of rabbits

- • b is the natural dying rate of rabbits

- • c is the natural dying rate of fox

- d is the factor describing how many caught rabbits lead to an increased population of foxes.

<!-- Start of picture text -->
part 3 - modules and functions<br><!-- End of picture text -->

#### conways game of life

some examples

<!-- Start of picture text -->
Lecture 5                                                   summary<br><!-- End of picture text -->

Import modules

### Solving differential equations

De�ne a function to solve. The 'Right Hand Side' [RHS]

De�ne a period to provide outputs

-

-

- We need to integrate ordinary differential equations [ODEs]

- Where solutions to ODEs are di�cult/impossible to arrive at by hand - there are functions in Python to solve/integrate

Call the ODE solver, with relevant options

-

- Requires us to de�ne the ODE to be solved through arrays and indices.

<!-- Start of picture text -->
practical 5                                               goals<br>code<br>•<br>•<br>•<br>•<br>•<br><!-- End of picture text -->

- Learning how we solve a single differential equation using the Scipy package

- Integrate an exponential decay equation

- Solve coupled equations: Implement the Predator-Prey equations, or the LotkaVolterra model

- general experience

- Learn how to use existing modules to solve a particular problem

- Start to consider sensitivity to variables
