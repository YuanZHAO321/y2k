---
title: "main(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).pdf"
type: pdf
---

EART11200 - The Natural Scientists Toolkit Mathematics and Physics Semester 2 Handbook - 2024-25 Academic Year

Matthew Thomas

### © 2025, Matthew Thomas

CREATED FOR THE DEPARTMENT OF EARTH AND ENVIRONMENTAL SCIENCE, UNIVERSITY OF MANCHESTER

This material may not be shared outside of the course and degree in which it is delivered. These notes are designed to supplement your learning and not replace the experience gained in the classroom. Where appropriate, all references to external sources for figures are provided.

# Contents

## Differentation

|1|Calculating Gradients . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7|
|---|---|
|1.1|Maths, Calculus and Physics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7|
|1.2|Approximating gradients . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11|
|1.3|Working in the practical classes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22|
|2|Introduction to Differentiation . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27|
|2.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27|
|2.2|Defning differentiation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28|
|2.3|Common differentials . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31|
|2.4|Differentiating sums of functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36|

|4|CONTENTS|
|---|---|
|3|Differentiating combinations of functions . . . . . . . . . . . . . . . 41|
|3.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41|
|3.2|Functions of functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42|
|3.3|Products of functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43|
|3.4|Quotients of functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 50|
|4|Optimisation and Properties of Derivatives . . . . . . . . . . . . . 59|
|4.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59|
|4.2|Properties of a derivative . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59|
|4.3|Optimisation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 63|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 68|
|5|Second Order Derivatives & Root Finding . . . . . . . . . . . . . . . 75|
|5.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 75|
|5.2|Second-order derivatives . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 75|
|5.3|Finding roots of equations: Newton-Raphson method . . . . . . . . . . . 79|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 82|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 84|
||Integration|
|6|Introduction to Integration . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 93|
|6.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 93|
|6.2|Integration as the reverse of differentiation . . . . . . . . . . . . . . . . . . . . . 93|
|6.3|Solving Ordinary Differential Equations (ODEs) . . . . . . . . . . . . . . . . . . 97|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 100|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102|
|7|Integration using Newton’s Laws . . . . . . . . . . . . . . . . . . . . . . . . 107|
|7.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107|

|CON|TENTS|5|
|---|---|---|
|7.2|Newtons laws of motion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 107|
|7.3|Newtons second law of motion . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 108|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 112|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 114|
|8|Integration by Substitution. . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 119|
|8.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 119|
|8.2|Integration by substitution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 120|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 125|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 128|
|9|Integration by Parts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 139|
|9.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 139|
|9.2|Integration by parts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 139|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 142|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 142|
|10|Second-Order Ordinary Differential Equations . . . .|. . . . 143|
|10.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 143|
|10.2|Second-order Differential Equations . . . . . . . . . . . . . . . . . . . . . .|. . . . 143|
|10.3|Applied boundary value problems and steady-state . . . . . .|. . . . 147|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 150|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . 153|

||Partial Differentiation|
|---|---|
|11|Vectors and Partial Differentiation . . . . . . . . . . . . . . . . . . . . . . 161|
|11.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161|
|11.2|Scalar felds . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161|
|11.3|Vectors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162|
|11.4|Partial Differentiation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 166|
||Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169|
||Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 171|

6

CONTENTS

## Additional Materials

|12|Crib Sheet . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 175|
|---|---|---|
|12.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 175|
|12.2|Differentiation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 175|
|12.3|Integration . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 182|
|13|Constants and Physical Laws . . . . . . . . . . . . . . . . . . . . .|. . . . . . 187|
|13.1|Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 187|
|13.2|Constants, units and common formulae . . . . . . . . . . . . . . . . .|. . . . . . 187|
|13.3|Common formulae . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 189|
|13.4|Radioactive decay . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 189|
|13.5|Newton’s laws . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 191|
|13.6|Heat transfer and Fourier’s laws. . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 193|
|13.7|Mass transfer and Fick’s laws . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 195|
|13.8|Atmospheric pressure and the hydrostatic equation . . . . .|. . . . . . 197|
|14|Provided Equations in the Exam . . . . . . . . . . . . . . . . . .|. . . . . . 199|
|15|Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .|. . . . . . 201|

# 1. Calculating Gradients

### 1.1 Maths, Calculus and Physics

In Earth and Environmental Science we are typically interested in understanding our past, and predicting our future. We live in a dynamic world where processes change in a matter of milliseconds to millennia. But what is Physics? If we check Encyclopedia Britannica we see that:

_Physics can, at base, be defined as the science of matter, motion, and energy. Its laws are typically expressed with economy and precision in the language of mathematics._

Essentially, Physics presents us with equations that describe the movement of energy through motion. Imagine relevant questions within our scientific domain:Where will warm air move from the tropics? How long will it take for the glacier to melt? But how do we solve these equations? We use the laws of Calculus. Again, if we check Encyclopedia Britannica we find one definition:

_Calculus makes it possible to solve problems as diverse as tracking the position of a space shuttle or predicting the pressure building up behind a dam as the water rises._

Calculus gives us the tools to calculate how quickly something is changing for example, or using that information to calculate quantities and states in the past or future. Is that relevant to understanding our changing climate? Physics is intricately built around laws of mathematics, and calculus provides us with the tools to understand the past, present

8

Chapter 1. Calculating Gradients

and future of our planet and our role on it. If we treat mathematics as the language of the universe then, through this course, we are going to expand our vocabulary. Understanding the basic laws of calculus and being able to implement fundamental laws of physics has been central to progressing all physical sciences.

What equations do we start with to practice implementing common rules of Calculus? This depends on the problem we wish to solve and each week we will focus on common problems in physics that are relevant to earth and environment sciences. As a start, we need to become familiar with a number of descriptions and concepts. For example, the following list of equations were taken from Ian Stewart in his book _17 Equations That Changed The World_ . Let us quickly review some of these. You may have come across all of them or a subset, in your previous studies:

1. The first is the Pythagorean theorem. It was Pythagoras of Samos (c.570 – c.495 BC), who was an ancient Greek philosopher that discovered this:

This formula describes the relationship between the sides of a right triangle on a flat plane.

2. The second ones are a handful of laws of logarithms:

You will find in the crib sheet provided in this course booklet. This simple rule turns multiplication into addition, division into subtraction and powers into multiples! Logarithms were introduced by John Napier in 1614 to simplify calculations. Indeed, this was the most common way to quickly multiply together large numbers, greatly speeding up calculations in physics, astronomy, and engineering.

3. The third we look at is is Newton’s law of gravitation:

It describes the force of gravity between two objects, _F_ , in terms of a universal constant, _G_ and the masses of the two objects, _m_ 1 and _m_ 2, and the distance between the objects, _r_ . Newton’s law is remarkable in that it explains, almost perfectly, why

9

the planets move in the way they do. Notice the power; how would you rearrange this to calculate _r_ ?.

4. The fourth was derived by Albert Einstein as part of the theory of special relativity, and has adorned many a t-shirt:

This famous formula states matter and energy are equivalent to each other.

5. The fifth describes the **derivative** :

Derivatives are central to Calculus, and tell us how much one variable is changing with respect to one or many others. The expression<sup>_d_</sup> _dt_<sup>_<u>f</u>_in the English equivalent</sup> reads: the rate of change of _f_ with respect to variable _t_ , which is often time. We use Calculus to arrive at an expression for<sup>_d_</sup> _dt_<sup>_<u>f</u>_, rather than calculating this by hand.</sup> In this equation, we are using an approximation which forms the basis of the final exercise in today’s class.

6. The final is actually called a Fourier Transform:

These take a messy wave function like a recording of a person talking, and allow us to break the messy function into a combination of a number of simple waves. This transform is at the heart of modern signal processing and analysis, and data compression. However the important component of this equation is the symbol � , which represents the act of **integration** .

The final two equations are particularly relevant to this module. Not because of the definition of the variable _f_ ( _f_ ( _x_ ) tells us that _f_ is a function of variable _x_ e.g. temperature as a function of latitude), but because of the procedures they represent. Whilst a derivative function tells us how much one variable is changing as a function of time, for example, the integral reverses this operation. Specifically, we can convert a derivative at a given point in time (or space) to an absolute or net quantity. For example, if water is flowing out of a reservoir at a variable rate, we could work out the total water lost or gained over a set period of time through the act of integration. Conversely, if we measure the actual value of water in the reservoir at certain points in time, we could then derive a derivative expression that tells us the rate of change at any point in time.

10

Chapter 1. Calculating Gradients

**Figure 1.1:** Interplay between differentiation and integration throughout this course. We start with differentiation and move in to integration later on

We have some key definitions we use throughout the course:

1. **Differentiation** allows us to quantify the rate at which much one variable is changing with respect to one or many others.

   - <sup>Algebraically, this is expressed using a</sup><sup>**differential equation**.For example,</sup><sup>_d_</sup> _dt_<sup>_<u>f</u>_</sup> represented by equation 1.1 is a **differential equation** . The expression<sup>_d_</sup> _dt_<sup>_<u>f</u>_in</sup> the English equivalent reads: the rate of change of _f_ with respect to variable _t_ .

   - <sup>We can derive the</sup><sup>**differential equation**using the laws of calculus.Imagine</sup> we measured variable _f_ as a function of variable _t_ . We then fit a line through so we have an expression for _f_ ( _t_ ). We might be able to use calculus to derive an equation for<sup>_d_</sup> _dt_<sup>_<u>f</u>_directly so we can calculate the gradient at any point.We</sup> say we have derived an **analytical** expression.

   - <sup>In many cases we cannot derive an expression for</sup><sup>_d_</sup> _dt_<sup>_<u>f</u>_directly.It may simply be</sup> too complicated to use the laws of calculus. However, we can approximate a derivative using the difference between two values of both _f_ and _t_ . We say we have used a **numerical** approximation. Equation 1.1 represents this operation and we will be using this from today.

2. **Integration** reverses the act of differentiation.

   - <sup>If we are given a differential equation, integration allows us to predict values</sup> in the past or future based on this gradient expression. We will see integration effectively sums derivatives to arrive at absolute quantities of values we are interested in: heat, mass, velocity etc.

   - <sup>In some cases we can derive the</sup><sup>**integral**using the laws of calculus.We say</sup> we have derived an **analytical** expression.

   - <sup>In many cases we cannot derive an expression for</sup> � _d dtf_<sup>directly.It may simply</sup>

11

be too complicated to use the laws of calculus. However, we can approximate an integral using using a technique very similar to approximations for derivatives. We say we have used a **numerical** approximation.

Figure 1.1 summarises how these types of operations are linked through our course. In weeks 1-5 we will be driven by different ways to arrive at differential equations. We use both numerical and analytical approaches and start with equations that express one quantity as a function of another, so we can extract the gradient. From week 6 onward we apply the process of integration. Here we start with a differential equation, and then integrate this to calculate quantities in the past or future. In both sections we will find we need to solve problems based on a subset of laws in Physics as applied to problems in earth sciences. These will be introduced each week, when relevant, to frame the problems we wish to solve. You can also take a look at more detail in the supporting material section, specifically Chapter 11. Here I provide a little more information on each theory should it help with the course content.

### 1.2 Approximating gradients

Figure 1.2 plots the change in variable _y_ as a function of variable _x_ according to the following equation, between the limits _x_ =0 and _x_ =20:

**Figure 1.2:** Generic function in which variable _y_ changes with _x_ . The line does not have a constant gradient.

How might we obtain a numerical approximation for the gradient at _x_ = 2, _x_ = 4, _x_ = 6 and so on up to _x_ = 20? A **numerical approximation** represents a manual derivative where

12

Chapter 1. Calculating Gradients

you take two values of both _x_ and _y_ , to obtain a derivative. Many times in research, we do not have a function from which we can obtain an **analytical derivative** and have to use numerical methods.

You may have seen previously that to calculate a gradient, you divided the change in _y_ by the change in _x_ . We are going to continue to use this idea to build up the principle of differentiation. Thus we say:

There are many methods to do calculate a gradient. The first approach we’ll consider is to take the current _y_ value, subtracted from the previous _y_ value and divided by the increment in _x_ :

In the current problem, this procedure restricts us to start at _x_ =4. Think about why this might be quite restrictive. We will call this the **Euler backward** method.

What happens if we change the direction of our increment to obtain this numerical approximation? To test this, rather than taking the value from a previous point, we could take the value at a future point. Thus, we start at _x_ = 2 and take the value at _x_ = 4. The approximate formula then becomes:

Here you can start at _x_ = 4 but only obtain the gradient up to _x_ = 18. Again, why is this restrictive? We will call this the **Euler forward** method.

Let us re-write the Euler’s forward and backward methods using slightly different notation:

Here, ∆ _x_ refers to the step-size or increment used between values in the approximation. Both of these approximations are attempting to calculate the same gradient but using different parts of the function curve, or function values.

The **central difference** method is another way to obtain a numerical approximation for the gradient and is more accurate for smooth functions, though this accuracy can vary depending on the shape of our curves. In this approach we take function values either side

13

of our current value and use the difference in a similar way. If we have two equally spaced function values, we can write the central approximation approach as:

Can you see why we now use 2∆ _x_ in the denominator?

You may come across other (slightly) different notation when writing differential equations. Sometimes we write _dx_<sup>_dy_as</sup><sup>_y′_.All of the following expressions are equally valid:</sup>

Now we are done with numerical approximations. The analytical derivative of Equation 1.2 above happens to be given by the following:

In the first practical session you will be asked to compare the accuracy of all approaches.

### 1.3 Working in the practical classes

For the exercises given out each week, you will find the solutions at the end of each Chapter. Rather than print these out in class, I would encourage you to try these first and then take a look at your working. Do try to resist looking at these solutions until you have given each problem a shot. Once you read through the solutions to check your answer, if anything is not clear then please do ask for help during each class. I will walk through example solutions, often at the beginning of the following weeks lecture.

You are not expected to retain a carbon copy of each solution in your head as we move through the course content. Do feel free to revisit material and operations as appropriate. The point of this course is to become familiar with numerical operations used to solve common problems in physical sciences. The more time you spend on these problems, the easier they will become.

Chapter 1. Calculating Gradients

14

## Exercises

### Introductory Exercises

We first need to practice manipulating components of equations. In any area of science, as we pull apart various theorems ( _a statement proven to be true and expressions through mathematical operations and arguments_ ), we are often left with a core set of operations. The analogy is pulling apart a physical instrument or device that is then left as a collection of nuts, bolts, wires, connections etc. Recognising how to manipulate powers and logarithms, for example, allows us to understand relationships between variables we are interested in whilst also building our own theoretical basis. When you move on to the programming course in the toolkit, we will then understand the process that allows us to implement these formulas on a computer through a programming language. In this module we start with the underlying mathematics.

In this section we practice manipulating powers, re-arranging equations and understanding relevant trigonometric relationships. All of these are relevant to the problems we will come across in the course. Some of the following examples in the first two sections are taken in part from Foundation Maths Third Edition by Anthony Croft & Robert Davison [ISBN 0 130 45426-5], which we provide as a PDF on the course blackboard site. You might find these examples easy, or not, but I would recommend running through them nonetheless.

#### Powers and indices

The function

states that variable _y_ is a function of _x_ to the power of 3.

**Question 1.1** : Without using a calculator, work out the value of:

- (a) 4<sup>2</sup>

- (b) 5<sup>3</sup> (c)<sup><u>2</u></sup> 5 3

**Question 1.2** : Write the following expressions more concisely by using an index:

- (a) _a ∗ a ∗ a ∗ a_

15

To manipulate expressions involving indices we use common laws given below:

**Question 1.3** : In each of the following, chose an appropriate law to simplify the expression: (a) 5<sup>13</sup> _∗_ 5<sup>3</sup>

#### Logarithms and exponentials

Logarithms provide an alternative way of writing expressions involving powers. If:

then:

_logba_ = _c_

For example, using the above we could solve the expression:

to find _x_ as:

You will often use what we call natural logarithms and logarithms with a base 10. A natural logarithm is also written as:

**Question 1.4** : Write down the expressions below in their simplest form:

exp( _−_ 8) (a) exp( _−_ 10) exp(3) (b) exp( _−_ 15) (c)<sup>exp(</sup> exp<sup>_−_1)</sup> (<sup>ex</sup> _−_ 5<sup><u>p</u></sup> )<sup><u>(</u></sup><sup>_−_1)</sup> (d)<sup>ex</sup> exp<sup><u>p(</u></sup> (<sup>_−_</sup> _−_<sup>3</sup> 6<sup><u>)</u></sup> )<sup>2</sup>

**Question 1.5** : Solve the following for _b_ :

**Question 1.6** : Solve the following for _t_ :

(a) exp (2 _t_ ) = 5

(b) exp (5 _t_ ) _×_ exp ( _−t_ ) = 5

Chapter 1. Calculating Gradients

16

- (c) exp (10 _t_ ) _÷_ exp ( _−t_ ) = 5

- (d) Two equations: exp (4 _t_ ) = 0 _._ 1 _N_ and exp ( _t_ ) = _N_ [hint: divide one equation by the other to cancel _N_ ]

**Question 1.7** : Evaluate the following (to 3 decimal places):

- (a) _x_ = log3 (3). Or what power do I need to raise 3 by to equal 3?

- (b) _x_ = log5 (10). Or what power do I need to raise 5 by to equal 10?

- (c) _x_ = log2 (8). Or what power do I need to raise 2 by to equal 8?

- (d) _x_ = log3 (59049). Or what power do I need to raise 3 by to equal 59049?

#### Rearranging expressions

**Question 1.8** : Rearrange the following equations to make _x_ the subject:

- (a) _y_ = 2 _x_ + 4 _x_ + 5 _x_

   - <u>1</u>

- (b) _y_ = 2 _x_ +4 _x_ +5 _x_

   - <u>1</u>

- (c) _y_ = 2 _x_<sup>2</sup> +4 _x_<sup>2</sup> +5 _x_<sup>2</sup>

   - _<u>x</u>_

- _<u>x</u>_

- (d) _y_ = 2 _x_<sup>2</sup> +4 _x_<sup>2</sup> +5 _x_<sup>2</sup>

- (e) _y_ =<sup>_~~√~~_</sup> _x_ + 1

- (f) _M_ =<sup>_πρ_</sup> 6<sup>_x_3</sup>

**Question 1.9** : Expand the following:

- (a) 3 � _x_<sup>2</sup> + 3 _y_ � (b) 7 _x_ � _−_<sup><u>1</u></sup> _x_<sup>+</sup><sup>_y_3�</sup> (c) 3 _xy x_ +<sup><u>2</u></sup> � _xy_ �

**Question 1.10** : The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay constant.

This is a differential equation. The solution to this differential equation is given by the following:

The half-life is the time it takes for the number of unstable nuclei to decrease by one half. Your task is to prove that the decay constant is given by the following expression:

where _t_ 1 _/_ 2 is the half-life of the sample.

17

#### Trigonometry

**Question 1.11** : The questions below are about triangles labelled below:

- (a) A right angled triangle, ABC, has AB= 10 and BC= 25, what is the angle _θ_ ?

- (b) A right angled triangle, ABC, has _θ_ = 40<sup>_◦_</sup> and AB= 5, what is the length of the hypotenuse?

- (c) A right angled triangle, ABC, has _θ_ =<sup>_<u>π</u>_</sup> 8<sup>radians and BC= 10, what is the length of</sup> the hypotenuse?

- (d) A right angled triangle, ABC, has a hypotenuse of length 50 and BC= 10, what is the angle _θ_ in radians?

**Question 1.12** : Below is a schematic of a block placed on an incline: You will come

across this schematic a number of times when we solve problems using Newton’s law of motion. In questions involving trigonometry thus far, you have been calculating lengths of opposite and adjacent sides of a triangle. We can use the same procedure to calculate the magnitude of different forces acting on a body. In this example, we have a block sat on an incline that is subject to the Earths gravitational pull. The gravitational force acts vertically, from the centre of the block to the centre of the earth. Assuming the triangle is a hard object, a component of this force will drag the block down the slope, labeled as _F_ 2. Another component will act perpendicular to the slop, which we have labeled as _F_ 1 and is known as the normal force. If the magnitude of the gravitational pull is given by the formula _m.g_ , where _m_ is the mass of the block and _g_ is a constant, what is the magnitude of (a) _F_ 1 and (b) _F_ 2?

18

Chapter 1. Calculating Gradients

### Calculating a gradient

In this section we practice calculating gradients and approximating differentiation using Euler’s backward method, Euler’s forward method and the central differences method. Recall that the formulae for Euler’s backward method, Euler’s forward method and the central differences method are as follows:

**Question 1.13** : Figure plots the change in variable y as a function of variable x according to the following equation, between the limits x=0 and x=20:

- (a) Your task is obtain a numerical approximation for the gradient at _x_ = 2, _x_ = 4, _x_ = 6 and so on up to _x_ = 20. Recall, this represents a manual derivative where you take two numbers for both _x_ and _y_ , to obtain your derivative. Many times in research we do not have a function from which we can obtain an analytical derivative and have to use numerical methods. Evaluate the values of _y_ at each value of _x_ and use the Euler’s backward method, Euler’s forward method and the central differences method to fill in the first four columns of the following table:

|**x**|**y**|**Backward**|**Forward**|**Central**|**Analytical**|
|---|---|---|---|---|---|
|2||–|–|–|–|
|4||||||
|6||||||
|8||||||
|10||||||
|12||||||
|14||||||
|16||||||
|18||||||
|20||–|–|–|–|

- (b) Now we are done with numerical approximations, the analytical derivative is given

   - by:

_dy x −_ 10 _dx_<sup>= 0</sup><sup>_._5</sup><sup>_x−_0</sup><sup>_._5 + 2</sup> 3 � 3 �

19

Fill in the final column with the values of the table with the analytical derivative.

- (c) Compare the approximations with the analytical derivative. Is one method better than the other?

**Figure 1.3:** Generic function in which variable _y_ changes with _x_ . The line does not have a constant gradient.

**Question 1.14** : The equation describing radioactive decay is given by:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay constant. This is a **differential equation** . The solution to this differential equation is given by the following:

which means the more radioactive atoms we have the higher the decay rate. In future classes we can use both **differentiation** and **integration** to move between the differential equation 1.2 and equation 1.3. For now we want to quantify the accuracy of a **numerical** approach to calculating the how _N_ varies with time, thus approximate<sup>_<u>dN</u>_</sup> _dt_<sup>over and over</sup> again, when compared with the expression given by equation 1.3.

Radioactive caesium has a half-life of 30 years and so the decay constant, _λ_ =<sup><u>ln2</u></sup> 30<sup>_∼_= 0</sup><sup>_._0231</sup> yr<sup>_−_1</sup> . Using the radioactive decay equation we know that the gradient in the number of atoms vs time is equal to _−λ N_ (where _N_ is the number of radioactive atoms). The initial number of radioactive Cs atoms is 1000 at _t_ = 0.

- (a) Fill in the values in the table below using both the _Euler forward step_ finite difference approximation and equation 1.3, using ∆ _t_ = 1 year:

20

Chapter 1. Calculating Gradients

|_t_|_N_(_t_)|**Numerical**(∆_N_)|**Analytical**(_−λN_(_t_))|
|---|---|---|---|
|0|1000.00|-22.84|-23.10|
|1|977.16|-22.31|-22.57|
|2||||
|3||||
|4||||
|5||||
|6||||
|7||||
|8||||
|9||||
|10||||

#### (b) How is the agreement between the analytic and approximate methods?

**Figure 1.4:** Mauna Loa Daily, Monthly and Weekly Averages for two years. See `gml.noaa.gov/ ccgg/trends/` for more details

21

**Question 1.15** : The table below provides monthly mean _CO_ 2 (in parts per million, or ppm) constructed from daily mean values measured at the Mauna Loa observatory (See here for additional details). These are also plotted as lines amongst raw data in figure 1.4.

|**year**|**month**|**decimal date**|**monthly average (ppm)**|
|---|---|---|---|
|2021|4|2021.2917|419.05|
|2021|5|2021.3750|419.13|
|2021|6|2021.4583|418.94|
|2021|7|2021.5417|416.96|
|2021|8|2021.6250|414.47|
|2021|9|2021.7083|413.30|
|2021|10|2021.7917|413.93|
|2021|11|2021.8750|415.01|
|2021|12|2021.9583|416.71|
|2022|1|2022.0417|418.19|
|2022|2|2022.1250|419.28|
|2022|3|2022.2083|418.81|
|2022|4|2022.2917|420.23|
|2022|5|2022.3750|420.99|
|2022|6|2022.4583|420.99|
|2022|7|2022.5417|418.90|
|2022|8|2022.6250|417.19|

- (a) Use a numerical approximation to derive rates of change in June for both 2021 and 2022. By using ∆ _t_ of 1 month, compare the results from a central difference approximation to a forward difference approximation.

- (b) Repeat the above operation but this time using a ∆ _t_ of 2 months.

**Question 1.16** : Consider the following cubic equation:

- (a) Calculate the numerical approximation of the derivative of _f_ ( _x_ ) for _x_ = 1 using Eulers Backward, Eulers Forward, and the Central Differences Methods using a stepsize of ∆ _x_ = 1, ∆ _x_ = 0 _._ 1, ∆ _x_ = 0 _._ 01, and ∆ _x_ = 0 _._ 001.

- (b) The analytical derivative is given by:

Calculate the differences (or the percentage difference) between the analytical derivative and the numerical approximation at _x_ = 1 that calculated from part (a). What do you notice as we increase the step size?

22

Chapter 1. Calculating Gradients

## Solutions

**Question 1.1** :

(a) 4<sup>2</sup> = 16 (b) 5<sup>3</sup> = 125 (c) 5<sup><u>2</u></sup> 3 = 1258

**Question 1.2** :

(a) _a ∗ a ∗ a ∗ a_ = _a_<sup>4</sup> (b) ( _yz_ ) _∗_ ( _yz_ ) _∗_ ( _yz_ ) = ( _yz_ )<sup>3</sup> 2 _<u>a a a</u>_ (c) _∗_ = � _f_ � � _f_ � � _f_ �

**Question 1.3** :

(a) 5<sup>13</sup> _∗_ 5<sup>3</sup> = 5<sup>16</sup> (b) 8<sup>13</sup> _/_ 8<sup>5</sup> = 8<sup>8</sup> (c) <u>�</u> _a_<sup>3�4</sup> = _a_<sup>12</sup> (d)<sup>_<u>y</u>_7=</sup><sup>_y_4</sup> _y_<sup>3</sup>

**Question 1.4** :

exp( _−_ 8) (a) exp( _−_ 10)<sup>= exp(2)</sup> exp(3) (b) exp( _−_ 15)<sup>=</sup> (c)<sup>exp(</sup> exp<sup>_−_1)</sup> (<sup>ex</sup> _−_ 5<sup><u>p</u></sup> )<sup><u>(</u></sup><sup>_−_1)</sup> = exp (3) (d)<sup>ex</sup> exp<sup><u>p(</u></sup> (<sup>_−_</sup> _−_<sup>3</sup> 6<sup><u>)</u></sup> )<sup>2= 1</sup>

**Question 1.5** :

(a) log10 <u>�4</u> _b_<sup>2�</sup> = 3 = _⇒ b_ = 15 _._ 811. <u>2</u> _<u>b−</u>_ <u>1</u> (b) exp � 3 � = 5 = _⇒ b_ = 2 _._ 914

**Question 1.6** :

(a) exp (2 _t_ ) = 5 = _⇒ t_ = 0 _._ 805

(b) exp (5 _t_ ) _×_ exp ( _−t_ ) = 5 = _⇒ t_ = 0 _._ 402

(c) exp (10 _t_ ) _÷_ exp ( _−t_ ) = 5 = _⇒ t_ = 0 _._ 146

(d) Two equations: exp (4 _t_ ) = 0 _._ 1 _N_ and exp ( _t_ ) = _N_ = _⇒ t_ = _−_ 0 _._ 768

**Question 1.7** :

(a) _x_ = log3 (3) = _⇒ x_ = 1 _._ 000

(b) _x_ = log5 (10) = _⇒ x_ = 1 _._ 431

23

(c) _x_ = log2 (8) = _⇒ x_ = 3 _._ 000

(d) _x_ = log3 (59049) = _⇒ x_ = 10 _._ 000

#### **Question 1.8** :

(a) _y_ = 2 _x_ + 4 _x_ + 5 _x_ = _⇒ x_ = 11<sup>_<u>y</u>_</sup> <u>1 1</u> (b) _y_ = 2 _x_ +4 _x_ +5 _x_<sup>=</sup><sup>_⇒x_=</sup> 11 _y_ <u>1 1</u> (c) _y_ = 2 _x_<sup>2</sup> +4 _x_<sup>2</sup> +5 _x_<sup>2=</sup><sup>_⇒x_=</sup><sup>_±_</sup> ~~<u>�</u>~~ 11 _y_ _<u>x</u>_ <u>1</u> (d) _y_ = 2 _x_<sup>2</sup> +4 _x_<sup>2</sup> +5 _x_<sup>2=</sup><sup>_⇒x_=</sup> 11 _y_ (e) _y_ =<sup>_~~√~~_</sup> _x_ + 1 = _⇒ x_ = _<u>y</u>_<sup>2</sup> _−_ 1 (f) _M_ =<sup>_πρ_</sup> 6<sup>_x_3</sup> = _⇒ x_ = 3 <u>� 6</u> _πρM_ <u>�</u> ~~�~~

**Question 1.9** : Expand the following:

**Question 1.10** : The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay constant. This is a differential equation. The solution to this differential equation is given by the following:

Here we can simply set the value of _N_ to be half of _No_ . Then, by using common laws regarding re-arranging logarithms, we can use the following procedure:

where _t_ 1 _/_ 2 is the half-life of the sample.

**Question 1.11** :

24

Chapter 1. Calculating Gradients

- (a) 68 _._ 2<sup>_◦_</sup> (b) 6 _._ 53

- (c) 26 _._ 13 (d) 0 _._ 20 radians

#### **Question 1.12** :

1. _F_ 1 = _mg_ cos( _θ_ )

2. _F_ 2 = _mg_ sin( _θ_ )

#### **Question 1.13** :

#### (a) - (b) Filled in table:

|**x**|**y**|**Backward**|**Forward**|**Central**|**Analytical**|
|---|---|---|---|---|---|
|2|8.53|–|–|–|–|
|4|6.00|-1.26|-0.89|-1.07|-1.08|
|6|4.23|-0.89|-0.48|-0.68|-0.69|
|8|3.27|-0.48|-0.06|-0.27|-0.27|
|10|3.16|-0.06|0.37|0.16|0.16|
|12|3.91|0.37|0.81|0.59|0.59|
|14|5.52|0.81|1.24|1.02|1.02|
|16|8.00|1.24|1.68|1.46|1.46|
|18|11.35|1.68|2.12|1.90|1.90|
|20|15.58|–|–|–|–|

#### (c) Looking at the raw differences:

|**x**|**Backward**|**Forward**|**Central**|
|---|---|---|---|
|4|-0.18|0.20|0.01|
|6|-0.20|0.21|0.00|
|8|-0.21|0.21|0.00|
|10|-0.21|0.22|0.00|
|12|-0.22|0.22|0.00|
|14|-0.22|0.22|0.00|
|16|-0.22|0.22|0.00|
|18|-0.22|0.22|0.00|

and also looking at the percentage difference:

25

|**x**|**Backward**|**Forward**|**Central**|
|---|---|---|---|
|4|16.55|18.18|0.81|
|6|29.44|30.31|0.44|
|8|78.28|79.34|0.53|
|10|134.97|135.99|0.51|
|12|36.63|36.80|0.09|
|14|21.23|21.30|0.03|
|16|14.95|14.99|0.02|
|18|11.54|11.56|0.01|

We can see that the central differences method is very accurate. Recall from lectures that the central differences method is more accurate for smooth functions, though this accuracy can vary depending on the shape of our curves.

#### **Question 1.14** :

(a) Filled in table:

|_t_|_N_(_t_)|**Numerical**(∆_N_)|**Analytical**(_−λN_(_t_))|
|---|---|---|---|
|0|1000.00|-22.84|-23.10|
|1|977.16|-22.31|-22.57|
|2|954.85|-21.80|-22.06|
|3|933.05|-21.31|-21.55|
|4|911.74|-20.82|-21.06|
|5|890.92|-20.34|-20.58|
|6|870.58|-19.88|-20.11|
|7|850.70|-19.43|-19.65|
|8|831.27|-18.98|-19.20|
|9|812.29|-18.55|-18.76|
|10|793.74|-18.13|-18.34|

- (b) The agreement is pretty good in this case. Note that when using the approximate method the step size chosen must be small enough. You will only figure this out by trial and error (e.g. try a step size and then try a smaller step size to see if the results are the same).

26

Chapter 1. Calculating Gradients

#### **Question 1.15** :

- (a) - (b) The table below gives the solutions to both parts where the time difference moves from 1 to 2 months. Notice how just using these derived gradients could be misleading. We need to see longer term trends to infer any global changes.

|**year**|**month**|**average (ppm)**|**forward**|**central**|**forward**|**central**|
|---|---|---|---|---|---|---|
|2021|4|419.05|–|–|–|–|
||5|419.13|–|–|–|–|
||6|418.94|-1.980|-1.085|-2.235|-1.145|
||7|416.96|–|–|–|–|
||8|414.47|–|–|–|–|
|2022|4|420.23|–|–|–|–|
||5|420.99|–|–|–|–|
||6|420.99|-2.090|-1.045|-1.900|-0.760|
||7|418.90|–|–|–|–|
||8|417.19|–|–|–|–|

#### **Question 1.16** :

- (a) The table below gives the solutions for the numerical approximation of the derivative of _f_ ( _x_ ) for _x_ = 1 using Euler’s Backward, Euler’s Forward, and the Central Differences Methods using a step size of ∆ _x_ = 1, ∆ _x_ = 0 _._ 1, ∆ _x_ = 0 _._ 01, and ∆ _x_ = 0 _._ 001. We observe that _f_ ( _x_ ) = 14 when _x_ = 1.

|∆_x_|_f_(_x−_∆_x_)|_f_(_x_+∆_x_)|**Backward**|**Forward**|**Central**|
|---|---|---|---|---|---|
|1|16.000|22.000|-2.000|8.000|3.000|
|0.1|13.849|14.251|1.510|2.510|2.010|
|0.01|13.980|14.021|1.950|2.050|2.000|
|0.001|13.998|14.002|1.995|2.005|2.000|

- (b) We observed that _f_<sup>_′_</sup> ( _x_ ) = 2 when _x_ = 1. The table below gives differences between the numerical and analytical derivatives. We can see that as we increase the step size that the accuracy of the numerical derivative increases also. This is one of the considerations when finding derivative numerically, increasing the step size increases the accuracy but also increase the computation, so there is a trade off in big applications.

|∆_x_|**Backward**|**Forward**|**Central**|
|---|---|---|---|
|1|-4.000|6.000|1.000|
|0.1|-0.490|0.510|0.010|
|0.01|-0.050|0.050|0.000|
|0.001|-0.005|0.005|0.000|

# 2. Introduction to Differentiation

### 2.1 Overview

Take a look at the graph of the function _f_ ( _x_ ) = 2 _x_<sup>3</sup> _−_ 20 _x_<sup>2</sup> + _x_ + 4000 in Figure 2.1. Clearly it can be seen that the gradient of this line is not constant with _x_ . For example:

1. at _x_ = _−_ 5 the gradient is quite steep and positive.

2. at _x_ = 0 the gradient is almost zero.

3. at _x_ = 5 the gradient is fairly shallow and negative.

<!-- Start of picture text -->
A line with a non−constant gradient<br>5000<br>f(x)=2x 3 −20x 2 +x+4000 @X=0 ∆  X<br>4000 ∆  Y ∆  Y<br>∆  X<br>@X=−5 @X=5<br>∆  Y<br>3000<br>∆  X<br>2000<br>m :  ∆  Y /  ∆  X=351.0<br>1000 mm12: :  ∆∆  Y /  Y /  ∆∆  X=1.0 X=−49.0<br>3<br>0<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>1500<br>Its gradient<br>1000 f’(x)=6x 2 −40x+1<br>500<br>0<br>−500<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 2.1:** Top shows the function _f_ ( _x_ ) = 2 _x_<sup>3</sup> _−_ 20 _x_<sup>2</sup> + _x ∗_ 4000; bottom shows the gradient _dx_<sup>_dy_,</sup> or _f_<sup>_′_</sup> ( _x_ ), which is positive until about _x_ = 0, negative until about _x_ = 6 and positive thereafter.

28

Chapter 2. Introduction to Differentiation

You could find the gradient at every point by drawing a tangent to the line at that point and determining how much _y_ changes for a given change in _x_ , like we did in Chapter 1. However, we can use **differentiation** to find a function that describes the gradient, which we will call<sup>_dy_In this case the function 6</sup><sup>_x_2</sup><sup>_−_40</sup><sup>_x_+1 describes the gradient of</sup><sup>_f_(</sup><sup>_x_).This</sup> _dx_<sup>.</sup> is shown in the bottom panel of Figure 2.1, labelled as _f_<sup>_′_</sup> ( _x_ ) which is often used in place of<sup>_dy_Once we have</sup><sup>_dy_</sup> _dx_<sup>.</sup> _dx_<sup>, we can evaluate it for any value of</sup><sup>_x_to find the gradient.</sup>

### 2.2 Defining differentiation

How can we arrive at the formula used to generate the line in the bottom figure? We use the rules of **differentiation** . These rules are central to the application of calculus. We do not cover the derivation of all rules here; rather we learn how and where to apply them. You should treat these rules as an engineer might treat a screwdriver or hammer. Please keep a copy of your crib sheet nearby throughout the course. You can use this to determine which rule to apply for a given problem that requires differentiation. For now, let us take a look at a straight line and quadratic.

**Figure 2.2:** A hypothetical curve with a _y_ value that increases non linearly as _x_ increases. The gradient at points _P_ and _Q_ are different.

In Figure 2.2 we find a curved line and compare two positions on that line, namely _P_ and _Q_ . These position have coordinates, or values for _x_ and _y_ as ( _x, y_ ) and ( _x_ + ∆ _x_ 1 _, y_ + ∆ _y_ 1) respectively. In other words, position _Q_ is found by movement along from _P_ by an increment given by ∆ _x_ 1 and ∆ _y_ 1. We want to derive an expression for _dx_<sup>_dy_, and we keep</sup> referring to approximating this using a finite difference approach (please refer to week 1). However, the choice of the increment used to arrive at this approximation is important. You can tell from our figure that we will arrive at a different gradient if we used a combination of increments ∆ _x_ 1 and ∆ _y_ 1 compared with ∆ _x_ 2 and ∆ _y_ 2. If this isn’t clear, please ask in class. As our increment gets smaller and smaller, we get closer to the accurate value for<sup>_dy_.</sup>

_dx_<sup>.</sup>

29

Indeed, we can write the following equation:

which states that as our increment, ∆ _x_ tends to 0, we arrive at our derivative value. This gives us a mechanism for deriving a formula for our gradient. For example, take the straight line displayed in Figure 2.3.

#### Derivative of a straight line

**Figure 2.3:** A hypothetical curve with a _y_ value that increases linearly as _x_ increases. The gradient at points _P_ and _Q_ are the same so we expect our gradient, thus derivative, to be constant.

The equation of a straight line can be expressed as the following:

where the constant _a_ is our gradient. We know our derivative _dx_<sup>_dy_should therefore be equal</sup> to _a_ . But can we show this through a derivation? Using the equation of the straight line we can work through the following steps to arrive at an expression for ∆<sup>∆</sup> _x_<sup>_<u>y</u>_:</sup>

If we then subtract _y_ = _ax_ from both sides we get :

Rearranging this gives us:

If we let ∆ _x �→_ 0 then we see that

So perhaps if we can keep deriving expressions for ∆<sup>∆</sup> _x_<sup>_<u>y</u>_wecanseeifthatexpression</sup> simplifies as ∆ _x_ tends to 0 and identify a pattern which we could wrap up in a general rule.

30

Chapter 2. Introduction to Differentiation

Derivative of a quadratic line

**Figure 2.4:** A hypothetical curve with a _y_ value that increases quadratically as _x_ increases. The gradient at points _P_ and _Q_ are different.

The equation of a quadratic can be expressed as the following:

In Figure 2.4 we again position two points on our curve. Let us derive an expression for ∆ _<u>y</u>_ ∆ _x_<sup>in moving between these points by substituting the</sup><sup>_x_and</sup><sup>_y_coordinates and isolating</sup> expressions for ∆ _x_ and ∆ _y_ :

Lets subtract _y_ = _ax_<sup>2</sup> from both sides of the equation:

Now let’s divide the equation by ∆ _x_ :

If we let ∆ _x �→_ 0 then we see that

If we repeat this procedure for higher order polynomials, we calculate that the gradient function for some simple functions of _x_ by **multiplying the original function of** _x_ **by its power** and **reducing the power that** _x_ **is raise to by 1** :

31

### 2.3 Common differentials

What if we didn’t have a polynomial in _x_ ? There are many other types of functions, so we will also need expressions for other common types of functions. Table 2.1 we list all of the common differentials you will use in this course. Learning how to apply them is a key aspect of the problems we will encounter.

**Table 2.1:** List of common differentials

<!-- Start of picture text -->
Function  y  = f ( x ) Derivative dx dy<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>d f<br>e f ( x )<br>dx e f ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

### 2.4 Differentiating sums of functions

So far we have seen how to differentiate simple functions (see Table 2.1. What happens when we have a sum of functions such as:

It turns out that differentiation is invariant to sums of functions. This means that when you differentiate the sum of two or more functions:

the **derivative of the sum** is equal to the **sum of the derivatives** of the individual functions.

Therefore, using the list of common derivatives, we see that the derivative of _y_ = 2 _x_<sup>2</sup> + 3 _x_ is:

We’ll see what happens when we get more complicated combinations of functions (i.e. functions of functions, products, fractions) in the next Chapter!

32

Chapter 2. Introduction to Differentiation

## Exercises

In the following exercises we can start to practice using them to derive derivative functions and thus calculate gradients. Please read the questions carefully before answering them. Throughout the course questions will be split and laid out as follows:

1. **Algebraic problems** : These questions are what I often call "pure" mathematical problems in the sense that they are not driven by a specific real word application. The functions might represent any given process in the earth system, however. The key point here is to continue practicing methods for differentiating.

2. **Real-world problems** : Here you are given a scenario that requires framing of a specific problem. You wont necessarily be asked to derive long derivatives here, but work with expressions of derivatives to get a better understanding of their role.

I would recommend you first try them without looking at crib sheets, but go back to that when you encounter any problems. For those who have not encountered the ∑ operator before, this represents a summation over the function given to the right hand side. For example, ∑<sup>4</sup> _x_ =1<sup>3</sup><sup>_x_is saying we need to sum the values obtained from from x=1 to x=4,</sup> stepping over increments of 1. In the problem provided below, try expanding the expression for a number of values before re-expressing your answer using the ∑ operator. Also note that an expression that uses<sup>_√_</sup> as the square root operator can be re-expressed using the <u>1</u> power<sup><u>1</u></sup> 2<sup>(i.e.</sup><sup>_√_</sup> _<u>x</u>_ = _x_ 2 ).

### Algebraic problems

**Question 2.1** : Differentiate the following functions with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>2</sup>

- (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup>

- (c) _h_ ( _x_ ) = 11 _x_<sup>1</sup>

**Question 2.2** : Differentiate the following polynomials with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>3</sup> + 2 _x_<sup>2</sup> + 3 _x_ + 5

- (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup> + _x_ + 5

- (c) _h_ ( _x_ ) = 11 _x_<sup>5</sup> + 2 _x_<sup>4</sup> + 2 _x_<sup>3</sup> + _x_<sup>2</sup> + 3 _x_ + 2

- **Question 2.3** : Find the gradient of the following functions at the values of _x_ specified: (a) _f_ ( _x_ ) = _x_<sup>2</sup> _−_ 3 _x_ at _x_ = 10

- (b) _f_ ( _x_ ) = 5 _x_<sup>5</sup> _−_ 2 _x_ at _x_ = 0

- (c) _f_ ( _x_ ) = 10 _x −_ 3 _x_<sup>7</sup> at _x_ = _−_ 2

33

**Question 2.4** : What function when differentiated gives the following [Hint: you will need to do the process of differentiation in reverse]:

- (a) _dx_<sup>_dy_= 2</sup><sup>_x_</sup>

- (b) _dx_<sup>_dy_=</sup><sup>_−_3</sup><sup>_x_3</sup> (c) _dx_<sup>_dy_= 7</sup>

**Question 2.5** : Obtain the derivative of the following functions:

- (a) _y_ = 10 _x_ (5 _x_ + 3 _x_ )

- (b) _y_ = 50 _x_<sup>2</sup> + 30 _x_<sup>2</sup>

- (c) _y_ = 3 _ce_<sup>_ix_</sup>

- (d) _y_ =<sup>_~~√~~_</sup> _<u>x</u>_

- (e) _y_ = cos( _x_ )

- (f) _y_ = _e_<sup>5</sup><sup>_x_</sup>

- (g) _y_ = 3 _x_ + 5 _y_

- (h) _y_ = 2 _ln_ ( _x_ )

**Question 2.6** : Obtain the derivative of the following (slightly harder) functions:

- (a) _y_ = ∑ _i_ 3 _ce_<sup>_ix_</sup> <u>4</u> _<u>x</u>_

- (b) _y_ = ~~�~~ _π_

- (c) _y_ = cos( _x_ )+ sin( _x_ )

- (d) _y_ = _e_<sup>5</sup><sup>_x_+4</sup>

- (e) _y_ = _ln_ (2 _x_ )

- (f) _y_ = 4 _x_<sup>4</sup> + _e_<sup>_x_</sup> + sin( _x_ )

### Real-world problems

**Question 2.7** : The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay constant. _λ_ =<sup><u>ln2</u></sup> _t_ 1 _/_ 2<sup>where</sup><sup>_t_1</sup><sup>_/_2 is the half-life of the sample.</sup>

The solution to equation 2.1 is

where _N_ 0 is the starting number of unstable nuclei (a constant).

In radioactive decay the number of unstable nuclei reduces with time. After a period of time known as the half-life. _t_ 1 _/_ 2, we have half the initial number of nuclei,<sup>_N_</sup> 2<sup><u>0</u>due</sup> to radioactive decay of the other nuclei. After another half-life we will have half those number of nuclei again (i.e.<sup>_N_</sup> 4<sup><u>0</u>).</sup>

34

Chapter 2. Introduction to Differentiation

This behaviour can also be described using:

where _n_ is the number of half-lifes that have elapsed.

- (a) Differentiate Equation 2.2 and substitute to show that it satisfies Equation 2.1.

- (b) A radioactive material has a half-life of _t_ 1 _/_ 2 = 30 years and there are 10 _,_ 000 nuclei in the sample. Using Equation 2.3, calculate how many nuclei there are after 90 years (i.e. 3 half-lifes).

- (c) Repeat the calculation using Equation 2.2.

**Question 2.8** : The hydrostatic equation describes how pressure changes with altitude in relation to other variables such as gravity and temperature. It is a fundamental principle in fluid mechanics and atmospheric science. We will use this a lot more later, but it has a similar formulation to the radioactive decay equation and is given (here) by

where _g_ , _Ra_ and _T_ are assumed to remain constant. Show that the following equation:

is a solution to the differential equation by differentiating and substituting it back into the differential equation.

**Question 2.9** : Imagine we are studying the volume of water in an ecosystem reservoir over time.

- (a) If we say that the volume of water in the system can be described as:

what is the drainage rate? Where _V_ 0 is the volume of water in our system when _t_ = 0, in _m_<sup>3</sup> . (take _V_ 0 = 1 _×_ 10<sup>_−_2</sup> )

- (b) In reality the water would drain at a non-constant rate. If we say that the volume of water in the reservoir can be described as:

what is the drainage rate at time 600s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using a finite difference method with a time step ∆ _t_ of 20 seconds, 10 seconds either side of 600s.

35

- (c) If we say that the volume of water in the sink can be described as:

what is the drainage rate at time 600s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using the finite difference method with a time step ∆ _t_ of 20 seconds, 10 seconds either side of 600s.

- (d) If we say that the volume of water in the sink can be described as:

what is the drainage rate at time 600 s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using the finite difference method with a time step ∆ _t_ of 20 seconds, 10 seconds either side of 600s.

36

Chapter 2. Introduction to Differentiation

## Solutions

### Algebraic problems

**Question 2.1** : Differentiate the following functions with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>2</sup> = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_= 10</sup><sup>_x_</sup> (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup> = _⇒_<sup>_d_</sup> _dx_<sup>_<u>g</u>_= 30</sup><sup>_x_2</sup> (c) _h_ ( _x_ ) = 11 _x_<sup>1</sup> = _⇒_<sup>_<u>dh</u>_</sup> _dx_<sup>= 11</sup>

**Question 2.2** : Differentiate the following polynomials with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>3</sup> + 2 _x_<sup>2</sup> + 3 _x_ + 5 = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_= 15</sup><sup>_x_2 +4</sup><sup>_x_+3</sup>

- (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup> + _x_ + 5 = _⇒_<sup>_d_</sup> _dx_<sup>_<u>g</u>_= 30</sup><sup>_x_2 +1</sup> (c) _h_ ( _x_ ) = 11 _x_<sup>5</sup> + 2 _x_<sup>4</sup> + 2 _x_<sup>3</sup> + _x_<sup>2</sup> + 3 _x_ + 2 = _⇒_<sup>_<u>dh</u>_</sup> _dx_<sup>= 55</sup><sup>_x_4 +8</sup><sup>_x_3 +6</sup><sup>_x_2 +2</sup><sup>_x_+3</sup>

**Question 2.3** : Find the gradient of the following functions at the values of _x_ specified:

**Question 2.4** : What function when differentiated gives the following [Hint: you will need to do the process of differentiation in reverse]:

- (a) _dx_<sup>_dy_= 2</sup><sup>_x_=</sup><sup>_⇒y_=</sup><sup>_x_2</sup> (b) _dx_<sup>_dy_=</sup><sup>_−_3</sup><sup>_x_3=</sup><sup>_⇒y_=</sup><sup>_−_</sup> 4<sup><u>3</u></sup><sup>_x_4</sup> (c) _dx_<sup>_dy_= 7=</sup><sup>_⇒y_= 7</sup><sup>_x_+</sup><sup>_d_</sup>

[ _d_ is a constant. Why do you think we need this? Ask in class if this is unclear]

**Question 2.5** : Obtain the derivative of the following functions:

- (a) _y_ = 10 _x_ (5 _x_ + 3 _x_ ) = 80 _x_<sup>2</sup> = _⇒ dx_<sup>_dy_= 160</sup><sup>_x_</sup> (b) _y_ = 50 _x_<sup>2</sup> + 30 _x_<sup>2</sup> = 80 _x_<sup>2</sup> = _⇒ dx_<sup>_dy_= 160</sup><sup>_x_</sup>

**Question 2.6** : Obtain the derivative of the following (slightly harder) functions:

- (a) _y_ = ∑ _i_ 3 _ce_<sup>_ix_</sup> = _⇒ dx_<sup>_dy_= 3</sup><sup>_cieix_(Remember the differential of a sum is the sum of the</sup>

37

differential. See Section 2.4)

#### **Question 2.7** :

- (a) Differentiating Equation 2.2 gives us:

substituting this in Equation 2.1 gives us

Alternatively, arranging the equation we see that:

Therefore Equation 2.2 is indeed the solution to the radioactive decay equation!

- (b) A radioactive material has a half-life of _t_ 1 _/_ 2 = 30 years and there are 10 _,_ 000 nuclei in the sample, so at 90 years, the number of nuclei is

There are 1250 nuclei remaining after 90 years.

- (c) A radioactive material has a half-life of _t_ 1 _/_ 2 = 30 years we see that the decay parameter is:

38

Chapter 2. Introduction to Differentiation

So after 90 years we see that

There are 1250 nuclei remaining after 90 years (i.e. the same).

**Question 2.8** : Differentiating _P_ ( _z_ ) with respect to _z_ gives us:

substituting these in Equation 2.1 gives us

Alternatively, arranging the equation we see that:

Therefore _P_ ( _z_ ) is indeed the solution to the hydrostatic equation!

#### **Question 2.9** :

- (a) Differentiating with respect to _t_ to get the (analytical) drainage rate:

We can see that the drainage rate is constant here.

- (b) Differentiating with respect to _t_ to get the (analytical) drainage rate:

At time _t_ = 600, the drainage rate is:

39

Using the central differences method:

- (c) Differentiating with respect to _t_ to get the (analytical) drainage rate:

At time _t_ = 600, the drainage rate is:

Using the central differences method:

- (d) Differentiating with respect to _t_ to get the (analytical) drainage rate:

At time _t_ = 600, the drainage rate is:

Using the central differences method:

# 3. Differentiating combinations of functions

### 3.1 Overview

We saw Chapter 2 that for a sum of functions, the **derivative of the sum** is equal to the **sum of the derivatives** of the individual functions.

However, in many cases we are faced with more complicated combinations of functions such as **functions of functions**

or **products of functions**

or **quotients of functions**

and the basic laws of calculus can no longer apply to find the derivative of _y_ . Another scenario arises where we wish to obtain a derivative of a function that does not fit under any of the criteria we use in our common rules of differentiation. In other words it does not look like we can obtain an analytical derivative and we may need to use a numerical approach (like we saw in Chapter 1). We will now look at expanding the laws of differentiation to deal with these new types of functions.

42

Chapter 3. Differentiating combinations of functions

### 3.2 Functions of functions

Lets first consider the case when we have **functions of functions** such as:

An example of this would be _y_ = ln(2 _x_ ) where we can split this into two functions, _u_ ( _x_ ) = ln( _x_ ) and _v_ ( _x_ ) = 2 _x_ . How do we obtain the derivative _dx_<sup>_dy_?Luckily,thereare</sup> properties of derivatives that we can use to slightly modify

and make it look like things we have seen before and differentiate as normal. This is called the chain rule and is best illustrated with an example. One of our common rules of differentiation shows us that the derivative function of the natural logarithm (i.e. _y_ = ln( _x_ ) is given as follows:

But what if our function looked slightly different? Let’s return to _y_ = ln(2 _x_ ). What is the derivative?

It is tempting to assume the answer would be _dx_<sup>_dy_=</sup> 2<sup><u>1</u></sup> _x_<sup>wouldn’t it?We know that this is</sup> wrong since we can rewrite _h_ ( _x_ ) = ln(2 _x_ ) = ln(2)+ ln( _x_ ) and therefore we see that

Fortunately, we have the **chain rule** . We can re-write the derivative of a function of a function such that it resembles a form we can derive an analytical derivative from. In this case, what if we assumed we could replace the expression 2 _x_ by a new variable _z_ . Our expression now reads:

We are not quite done, however. The chain rule allows us to treat derivatives in the same way we can multiply fractions. We **chain** together operations. Formally, it states that to get the derivative of a function, _f_ , which can be written as a function of another function, _g_ ( _x_ ) you differentiate the function, _f_ , wrt the function _g_ and multiply the result by the derivative of _g_ with respect to _x_ :

43

This tells us that we first obtain the analytical derivative of our function _f_ with respect to a new variable _g_ and then multiply the derivative of our new variable _g_ with respect to our original variable _x_ . Can you see how the terms _dg_ cancel out?

**Example 3.1** : Differentiate _y_ = (3 _x_ + 1)<sup>2</sup> . We could expand the bracket and differentiate as we have seen before:

or we could use _chain rule_ . Let

and differentiate as usual

Therefore using the chain rule formula and substitution the solution is:

which is what we expected!

**Example 3.2** : Differentiate _y_ = _√_ 13 _x_<sup>2</sup> _−_ 6 _x_ + 8. There is no obvious way to differentiate this using methods we have used before, we must use _chain rule_ . Let

and differentiate as usual

Therefore using the chain rule formula and substitution the solution is:

### 3.3 Products of functions

In many cases we are faced with the **product of two, or more, functions** . We might described a general case where we have two functions multiple as :

Chapter 3. Differentiating combinations of functions

44

where _u_ is a function that varies only with respect to variable _x_ and _v_ is also a function that varies only with respect to _x_ . How do we obtain the derivative _dx_<sup>_dy_?Using the tools we have</sup> met so far, then we might first attempt to expand terms and separate variables. But what if we decided that the derivative could be calculated by simply multiplying the associated derivatives from each function. So, we might assume we can use the formula:

This would be useful if our functions were somewhat complex but could be treated in isolation i.e. we did not want to expand all of the terms. Let us look at a relatively simple example to see which is a valid approach, one where we can access the expression _u_ ( _x_ ) _v_ ( _x_ ). If we assume _u_ ( _x_ ) = _x_<sup>3</sup> and _v_ ( _x_ ) = _x_<sup>6</sup> then we know that:

From this we can obtain the derivative as follows:

But what if we had chosen to use the approach written in align 3.2. We would arrive at the following formula:

which is wrong! We saw that it is wrong as our expansion leads to a derivative of 9 _x_<sup>8</sup> . So here we can see that we have to be careful when working with products of functions.

Fortunately, in cases where we cant easily expand our expression, there is the **product rule** which states that to get the derivative of a function, _y_ , which can be written as the _product_ of two functions, _u_ and _v_ we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and calculate:</sup>

45

**Example 3.3** : Differentiate _y_ = (3 _x_ + 1)<sup>2</sup> . We could expand the bracket and differentiate as we have seen before:

or we could use _product rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:

which is what we expected!

**Example 3.4** : Differentiate _y_ = _x_ exp ( _−_ 3 _x_ ). There is no obvious way to differentiate this using methods we have used before, we must use _product rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:

### 3.4 Quotients of functions

What if we **divided one function by another** ? We find similar problems. We might described a general case where we have two functions multiple as :

where _u_ is a function that varies only with respect to variable _x_ and _v_ is also a function that varies only with respect to _x_ . How do we obtain the derivative _dx_<sup>_dy_?Using the tools</sup>

Chapter 3. Differentiating combinations of functions

46

we have met so far, then we might first attempt to simplify into one expression. But what if we decided that the derivative could be calculated by simply dividing the associated derivatives from each function? We might assume we can use the formula:

Again, this would be useful if our functions were somewhat complex but could be treated in isolation i.e. we did not want to expand and simplify all of the terms. Let us look at a relatively simple example to see which is a valid approach, one where we can access the expression _u_ ( _x_ ) _v_ ( _x_ ). If we assume _u_ ( _x_ ) = _x_<sup>3</sup> and _v_ ( _x_ ) = _x_<sup>6</sup> then we know that:

Once again we can rearrange this expression and arrive at the correct derivative through the following:

But what if we had chosen to use the approach written in align 3.5? We would arrive at the following formula:

which is wrong! We saw that it is wrong as our expansion leads to a derivative of _−_ 3 _x_<sup>_−_4</sup> . So here we can see that we have to be careful when working with fractions of functions.

Fortunately, in cases where we cant easily expand and simplify our expression, there is the **quotient rule** which states that to get the derivative of a function, _y_ , which can be written as the _quotient_ of two functions, _u_ and _v_ we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and calculate:</sup>

**Example 3.5** : Differentiate _y_ =<sup><u>3</u></sup><sup>_<u>x</u>_</sup> _x_<sup><u>+21.</u>Wecouldsplitthisupintotwofractionsand</sup> differentiate,

47

or we could use _quotient rule_ . Let

and differentiate as usual

Therefore using the quotient rule formula the solution is:

which is what we expected!

**Example 3.6** : Differentiate _y_ =<sup><u>3</u></sup> _x_<sup>2</sup><sup>_<u>x</u>_</sup> +<sup><u>+</u></sup> 1<sup><u>1.</u>There is no obvious way to differentiate this using</sup> methods we have used before. We must use _Quotient Rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:

48

Chapter 3. Differentiating combinations of functions

## Exercises

### Algebraic problems

**Question 3.1** : Use the chain rule to differentiate the following functions:

- (a) _y_ = exp( _x_<sup>2</sup> + 5 _x_ + 2)

- (b) _y_ = cos(3 _x_ + 5)

- (c) _y_ = sin( _x_ )<sup>2</sup>

**Question 3.2** : Use the product rule to differentiate the following functions:

- (a) _y_ = _x_ exp( _x_ )

- (b) _y_ = _x_<sup>2</sup> exp(4 _x_ )

- (c) _y_ = ( _x_<sup>2</sup> + 9) exp( _−x_ )

**Question 3.3** : Use the quotient rule to differentiate the following functions:

- (a) _y_ =<sup>exp(</sup><sup>_−x_</sup><sup><u>)</u></sup>

_x_

- _<u>x</u>_

- (b) _y_ = _x_<sup>2</sup> +25 _<u>x</u>_<sup>2</sup>

- (c) _y_ = _x_<sup>3</sup> +25 _x_

**Question 3.4** : Use the chain rule for (a) and the result of (a) in (b)-(e) find _dx_<sup>_dy_ofthe</sup> following equations (Hint: you may need to use a mixture of chain, product and quotient rules):

- (a) _y_ = _~~√~~ x_<sup>2</sup> + 25

- (b) _y_ = sin _<u>√x</u>_<sup>2</sup> + 25

- (c) _y_ = _x√x_<sup>2</sup> + 25

- _<u>x</u>_

- (d) _y_ = _~~√~~ x_<sup>2</sup> +25

**Question 3.5** : Find where the following functions are decreasing and increasing. These problems require a number of steps. We know that where the derivative is 0 it is likely the function will be changing direction either side. We will come across the important property a zero derivative has soon. But for now, once you find where the derivatives are 0 you can then explore regions either side to determine if the gradient is positive or negative.

- (a) _V_ ( _t_ ) = (4 _− t_<sup>2</sup> )(1 + 5 _t_<sup>2</sup> ) (b) _f_ ( _x_ ) = 1<sup>_<u>x</u>_</sup> +<sup>_−_</sup> 8<sup>_<u>x</u>_</sup> _x_<sup>22</sup>

**Question 3.6** : Use the chain, product or quotient rules to find the derivative of the given function.

- (a) _Z_ ( _s_ ) = (sin( _x_<sup>2</sup> ))<sup>2</sup>

49

### Real-world problems

**Question 3.7** : Imagine we are studying the volume of water in an ecosystem reservoir over time (in hours).

- (a) If we say that the volume of water in the sink can be described as:

Where _V_ 0 is the volume of water in our system when _t_ = 0, in _m_<sup>3</sup> . Use the chain rule to determine the gradient analytically. What is the drainage rate after 10 hours when _V_ 0 = 10?

- (b) If we say that the volume of water in the sink can be described as:

Where _V_ 0 is the volume of water in our system when _t_ = 0, in _m_<sup>3</sup> . Use the product rule to determine the gradient analytically. What is the drainage rate after 10 hours when _V_ 0 = 10?

- (c) If we say that the volume of water in the sink can be described as:

Where _V_ 0 is the volume of water in our system when _t_ = 0, in _m_<sup>3</sup> . Use the quotient rule to determine the gradient analytically. What is the drainage rate after 10 hours when _V_ 0 = 10?

50

Chapter 3. Differentiating combinations of functions

## Solutions

**Question 3.1** : Use the chain rule to differentiate the following functions:

- (a) Split the function and differentiate:

Apply the chain rule:

- (b) Split the function and differentiate:

Apply the chain rule:

- (c) Split the function and differentiate:

Apply the chain rule:

**Question 3.2** : Use the product rule to differentiate the following functions:

- (a) Split the function and differentiate:

51

Apply the product rule:

- (b) Split the function and differentiate:

Apply the product rule:

- (c) Split the function and differentiate:

Apply the product rule:

**Question 3.3** : Use the quotient rule to differentiate the following functions:

- (a) Split the function and differentiate:

Apply the quotient rule:

52

Chapter 3. Differentiating combinations of functions

- (b) Split the function and differentiate:

Apply the quotient rule:

- (c) Split the function and differentiate:

Apply the quotient rule:

**Question 3.4** : Use the chain rule for (a) and the result of (a) in (b)-(e) find _dx_<sup>_dy_ofthe</sup> following equations (Hint: you may need to use a mixture of chain, product and quotient rules):

- (a) Split the function and differentiate:

Apply the chain rule:

53

- (b) Split the function and differentiate:

Apply the chain rule:

- (c) Split the function and differentiate:

Apply the product rule:

- (d) Split the function and differentiate:

Apply the quotient rule:

**Question 3.5** :

- (a) Split the function and differentiate:

Chapter 3. Differentiating combinations of functions

54

Apply the product rule:

Next, we need to know where the function is not changing and so we set the derivative equal to zero and solve. From the factored form of the derivative we can see that the derivative will be zero at:

We need to know is where the derivative is positive (and hence the function is increasing) or negative (and hence the function is decreasing). Because the derivative is continuous we know that the only place it can change sign is where the derivative is zero. We have been given 3 point where the derivative is zero. Lets use these points to define some regions to evaluate the sign of the derivative. This is best illustrated using Figure 3.1. From this we get the following increasing/decreasing information.

**Figure 3.1:** Here we identify where along the _x_ axis the function derivative has a value of 0 [dashed lines] and then interrogate the sign of the derivatives either side. From this information we can identify regions where the function is increasing or decreasing.

#### (b) Split the function and differentiate:

55

Apply the quotient rule:

Next, we need to know where the function is not changing and so we set the derivative equal to zero and solve. The denominator will never be zero for any real number and so the derivative will only be zero where the numerator is zero. Thus:

When we solve this we arrive at the following roots:

We need to know is where the derivative is positive (and hence the function is increasing) or negative (and hence the function is decreasing). Because the derivative is continuous we know that the only place it can change sign is where the derivative is zero. We have been given 3 point where the derivative is zero. Lets use these points to define some regions to evaluate the sign of the derivative. This is best illustrated using the Figure 3.2.From this we get the following increasing/decreasing information.

**Figure 3.2:** Here we identify where along the _x_ axis the function derivative has a value of 0 [dashed lines] and then interrogate the sign of the derivatives either side. From this information we can identify regions where the function is increasing or decreasing.

Chapter 3. Differentiating combinations of functions

56

#### **Question 3.6** :

- (a) In this Question 3.we need to apply the chain rule twice. To make sure we don’t make any mistakes, lets do it part by part. First we differentiate _y_ = sin( _x_<sup>2</sup> ). Split the function and differentiate:

Apply the chain rule:

Now lets apply the chain rule to _Z_ = (sin( _x_<sup>2</sup> ))<sup>2</sup> . Split the function and differentiate:

Apply the chain rule:

- (b) Split the function and differentiate:

Apply the product rule:

- (c) Split the function and differentiate:

57

Apply the quotient rule:

### Real-world problems

**Question 3.7** : Imagine we are studying the volume of water in an ecosystem reservoir over time (in hours).

- (a) Split the function and differentiate:

Apply the chain rule:

The drainage rate at _t_ = 10 is

- (b) Split the function and differentiate:

58

Chapter 3. Differentiating combinations of functions

Apply the product rule:

The drainage rate at _t_ = 10 is

(c) Split the function and differentiate:

Apply the quotient rule:

The drainage rate at _t_ = 10 is

# 4. Optimisation and Properties of Derivatives

### 4.1 Overview

In Chapters 2 and 3, we have been calculating derivatives of functions. Whilst telling us the rate of change of a function, derivatives can also be used to determine certain properties of a function and how it behaves. We now carry on with the topic of differentiation onto the topic of **properties of derviatives** and using them to **find maxima and minima** of functions.

### 4.2 Properties of a derivative

Remember, the derivative of a function at a given point represents the gradient of a function at that point, indicating the rate of change. Therefore, we can use the derivative to know where a function is increasing, decreasing or neither. We can see that if the rate of change is negative,

then the function is decreasing and that if the rate of change is positive,

then the function is increasing. If the derivative is zero,

then it is likely the function will be changing direction either side. This means that the point on the function where the derivative is either a **maximum value** , **minimum value**

60

Chapter 4. Optimisation and Properties of Derivatives

or a **saddle point** . This turns out to be a very useful property and more generally we call these **stationary values** or **stationary points** . Once we know where the these stationary points are for a function, further analysis can help classify them. There will be more on this in the next Chapter, but for now, once you find where the derivatives are 0 you can then explore regions either side to determine if the gradient is positive or negative. Let’s consider some examples.

**Example 4.1** : Let’s consider the quadratic function

This function is shown in the top panel of Figure 4.1, over the range: _−_ 5 _< x <_ 15. We can see that there is a point on the curve that where the minimum occurs ( _x_ = 5 in the plot, but note that it is not obvious). Now lets differentiate the function _f_ ( _x_ ) and look at how it behaves:

The derivative function is shown in the bottom panel of Figure 4.1, over the range: _−_ 5 _< x <_ 15.

<!-- Start of picture text -->
40<br>f(x)=x 2 /2−5x+2<br>20<br>0<br>−20<br>−5 0 5 10 15<br>x<br>10<br>f’(x)=x−5<br>5<br>0<br>−5<br>−10<br>−5 0 5 10 15<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 4.1:** Top: _y_ changing as a function of _x_ . Bottom: Derivative value for the same function, also varying as a function of _x_

61

The thing to notice about the gradient function, _f_<sup>_′_</sup> ( _x_ ), is that it is equal to zero at the point where _f_ ( _x_ ) is a minimum. Therefore we can find the minimum of _f_ ( _x_ ) by differentiating it and setting it to zero:

we can then solve _x −_ 5 = 0 to get that _x_ = 5. This tells us that the minimum value occurs at _x_ = 5. We can evaluate the value of _f_ at the stationary value (i.e. maximum and minimum) _f_ (5) =<sup><u>5</u></sup> 2<sup>2</sup><sup>_−_5</sup><sup>_._5+2 =</sup><sup>_−_10</sup><sup>_._5.</sup>

**Example 4.2** : Sometimes there can be more than one stationary point. Let’s consider the cubic function

This function is shown in the top panel of Figure 4.2, over the range: _−_ 10 _< x <_ 5. We can see that there is a point on the curve that where a minimum occurs ( _x_ = 2) and where a maximum occurs ( _x_ = _−_ 5), again not immediately visible. Now lets differentiate the function _f_ ( _x_ ) and look at how it behaves:

_d f_<sup>_f ′_(</sup><sup>_x_) =</sup><sup>_x_2 +4</sup><sup>_x−_5</sup> _dx_<sup>=</sup>

<!-- Start of picture text -->
f(x)=x 3 /3+2x 2 −5x+1<br>40<br>20<br>0<br>−10 −5 0 5<br>x<br>100<br>f’(x)=x 2 +4x−5<br>50<br>0<br>−50<br>−10 −5 0 5<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 4.2:** Top: _y_ changing as a function of _x_ . Bottom: Derivative value for the same function, also varying as a function of _x_

62

Chapter 4. Optimisation and Properties of Derivatives

The derivative function is shown in the bottom panel of Figure 4.2, over the range: _−_ 10 _< x <_ 5. If we set the gradient function to zero we have a quadratic equation:

which we can solve either by the quadratic formula, or by factorisation:

so that the two solutions are _x_ = 1 and _x_ = _−_ 5 (as shown in the Figure 4.2).

Sometimes it will not always be possible to solve an equation equal to zero by rearranging or factorising, due to the complexity of the function. We then must use an algorithm to find the stationary values. We will explore this topic in the next Chapter.

So, to summarise to find a stationary value we:

1. Differentiate the function, to find the gradient function, _f_<sup>_′_</sup> ( _x_ ) or _dx_<sup>_dy_</sup>

2. Set the gradient function to zero and solve for _x_ .

3. Substitute _x_ into _f_ ( _x_ ) to get what the value of the stationary points are.

We could (and strictly should) verify that we have found a minimum and maximum point. We will again see this more in next Chapter, but a quick way of doing this is to evaluate _f_ ( _x_ ) for _x_ just a little bit more and just a little bit less than the stationary value. Returning to Example 4.1, we can try _f_ (4 _._ 5), which is equal to _−_ 10 _._ 375 and _f_ (5 _._ 5) which is also equal to _−_ 10 _._ 375. Both of these values, are greater than the stationary value, so this tells us that the stationary value is indeed a minimum. If we had found a maximum we would find that _f_ ( _x_ ) either side of the stationary point to be less than the value of the stationary point. More generally, we can use properties of a derivative. We can see that when _x <_ 5, then _f_<sup>_′_</sup> ( _x_ ) _<_ 0 and when _x >_ 5, then _f_<sup>_′_</sup> ( _x_ ) _>_ 0, so we see that the stationary value is a minimum.

### 4.3 Optimisation

Optimisation problems involve finding the best solution, often the maximum or minimum value(s) of a function given set of constraints. They are quite common in areas such as

- <sup>Business and Economics:Maximize profit or minimize cost functions.</sup>

- <sup>Physics and Engineering:Minimize energy or optimize the performance of systems.</sup>

- <sup>Geometry:Find dimensions that maximize area or volume subject to constraints.</sup>

Derivatives and their properties play a crucial role in a wide range of problems such as optimisation. We can study a function to find the maxima and minima which "optimises" a function, which can play a vital role in decision making.

63

## Exercises

### Algebraic problems

**Question 4.1** : Find the stationary point of the following functions and verify whether they are maxima or minima either by evaluating the function, or using the properties of the derivative.

- (a) _f_ ( _x_ ) = _x_<sup>2</sup> + _x_

- (b) _f_ ( _x_ ) = 2 _x − x_<sup>2</sup>

- (c) _f_ ( _x_ ) = ( _x −_ 2)<sup>2</sup>

- (d) _f_ ( _x_ ) = ( _x −_ 2)(3 _− x_ ) (e) _f_ ( _x_ ) =<sup>_<u>x</u>_</sup> 3<sup>3</sup><sup>_−_4</sup><sup>_x_2 +15</sup><sup>_x_+5</sup> (f) _f_ ( _x_ ) = _ln_ ( _x_ ) _− x_

**Question 4.2** : Find two non-negative numbers whose sum is 9 and so that the product of one number and the square of the other number is a maximum. To solve this, first construct the two equations that define these conditions, using variables _x_ and _y_ . To start, you can write _x_ + _y_ = 9.

### Real-world problems

**Question 4.3** : Amazon wants to construct a box with length _l_ , width _w_ and height _h_ which has volume:

and only has 10 _m_<sup>2</sup> of material to use in construction of the box:

If the box will have a square base (i.e. _l_ = _w_ ) and assuming that all the material is used in the construction process, determine the maximum volume that the box can have. You will need to rearrange the constraints and substitute into the volume equation to find a function with respect to one variable before optimising.

**Question 4.4** : Amazon now wants to construct an open rectangular box with square base is to be made from 48 m<sup>2</sup> of material. What dimensions will result in a box with the largest possible volume?

**Question 4.5** : A cylindrical aluminium can of cola is to hold 330 ml of liquid. Coca-Cola would like to know what the dimensions of the can that uses the least amount of aluminium. The volume for a cylinder of base radius _r_ and height _h_ is given by

Chapter 4. Optimisation and Properties of Derivatives

64

The formula for surface area of a cylinder is given by:

The volume is constrained so for whatever value of _r_ we pick, we can calculate _h_ and therefore estimate the surface area of the can. Rewrite the volume equation to get:

Substitute this into the surface area equation:

If you choose _r_ = 0 _._ 01m, then, since the volume has to be 330 _×_ 10<sup>_−_6</sup> , the height, _h_ , and surface area, _A_ , has to be:

- (a) Complete the table below for surface area for different values of the radius _r_ . Which is the best value to select?

|Radius|Height for volume to equal 330 ml|Surface area of aluminium|
|---|---|---|
|0.010|1.050|0.067|
|0.020|||
|0.030|||
|0.040|||
|0.050|||
|0.060|||
|0.070|||

- (b) Use differentiation to find the minimum amount, what value do you arrive at?

**Question 4.6: A gold seam optimisation problem.** You decide to mine a gold seam and want to decide on how long to mine it for to maximise your profits. The cost of gold you can mine per day, _G_ , is a function of the number of days, _n_ , that you mine for. It becomes more difficult to mine the gold as time goes on:

In addition the cost of renting the equipment to mine the gold, _C_ , increases with the number of days:

So that your profit is _P_ = _G −C_ . Graphs of _P, G_ and _C_ are shown in Figure 4.3.

65

- (a) Work out how long you should mine the gold to optimise (find the stationary value of) your profit, _P_ . (Hint: you can either use _chain or quotient rules_ to perform the differentiation. To find the stationary points you will need to solve a quadratic equation).

- (b) In the project a "snag" occurs that causes no profit to be made on one day (see Figure 4.4). After the snag is overcome mining can proceed at a faster rate. A function describing the cost of gold mined as the project goes on is:

Use this function to find the day where the amount of gold extracted hits a snag (you will need to make use of the product rule).

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>Gross profit, G<br>0<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

**Figure 4.3:** Hypothetical plot of profit as a function of time

<!-- Start of picture text -->
4<br>10  x 10<br>8<br>Snag<br>6<br>4<br>2<br>0<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

**Figure 4.4:** Hypothetical plot of profit as a function of time

Chapter 4. Optimisation and Properties of Derivatives

66

**Question 4.7: Geoengineering.** In this problem economists investigating the _economic cost to society_ , _E_ , of an increase in global temperature, ∆ _T_ (e.g. see the Stern report) estimate that:

with _E_ in billions of dollars (see Figure 4.5). In addition climate scientists investigating the _marine cloud brightening_ proposal for geoengineering estimate that the technique does have the capability to offset warming by rising CO2. They estimate spending money, _C_ , on a program to implement geoengineering can result in a lower increase in temperature:

where _C_ is the amount spent on the scheme and _d_ is a constant that has some uncertainty (see Figure 4.6).

<!-- Start of picture text -->
5000<br>E( ∆  T)=500 ×∆  T<br>4000<br>3000<br>2000<br>1000<br>0<br>0 2 4 6 8 10<br>Change in global temperature,  ∆  T (K)<br> dollars)<br>9<br>Cost to society, E (x10<br><!-- End of picture text -->

**Figure 4.5:** Hypothetical cost to society as a function of changes in global temperatures

<!-- Start of picture text -->
10<br>∆  T(C)=10 exp(−dC)<br>8<br>6<br>4<br>2<br>0<br>0 10 20 30 40 50<br>Billions spent on geoengineering, C ( ×  10 9  dollars)<br> T (K)<br>∆<br>Change in temperature if we  use geoengineering,<br><!-- End of picture text -->

**Figure 4.6:** Hypothetical change in global temperatures as a function of investment in geoengineering

67

In order to decide whether the scheme is worth implementing we need to get an idea of the _total cost_ that implementing the scheme has (i.e. the benefit plus cost of scheme) vs the _<u>E</u>_ amount spent on implementing it. To do this rearrange Equation 4.1 to give ∆ _T_ = 500<sup>and</sup> substitute into Equation 4.2 to get an equation for the economic cost to society, _E_ , vs the amount spent on geoengineering, _C_ . Then add on the cost of the scheme, _C_ , to get the _total cost_ , _T_ = _E_ + _C_ :

This function can be seen in Figure 4.7 and we can see there is a minimum in the _total cost_ .

Your goal is to optimise / find the stationary value of Equation 4.3 (i.e. find how much we should spend on the scheme so that we can minimise the total cost). Choose the parameter _d_ to be equal to 2 _×_ 10<sup>_−_4</sup> ; how much should be spent? What is the meaning of your answer (i.e. what should the advice to policy makers be?)

<!-- Start of picture text -->
χ =E+C<br>χ =500 ×  10 exp(−dC)+C<br>Billions spent on geoengineering, C ( ×  10 9  dollars)<br> dollars)<br>9<br> 10<br>×<br> (<br>χ<br>Total cost in billions,<br><!-- End of picture text -->

**Figure 4.7:** Hypothetical total cost to society as a function of investment in geo-engineering

68

Chapter 4. Optimisation and Properties of Derivatives

## Solutions

**Question 4.1** : Find the stationary point of the following functions and verify whether they are maxima or minima either by evaluating the function, or using the properties of the derivative.

- (a) _f_ ( _x_ ) = _x_<sup>2</sup> + _x_ = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_=</sup><sup>_f ′_(</sup><sup>_x_) = 2</sup><sup>_x_+1=</sup><sup>_⇒_2</sup><sup>_x_+1 = 0</sup> _x_ = _−_<sup><u>1</u></sup> 2<sup>is a stationary value and this is a minimum.</sup>

- (b) _f_ ( _x_ ) = 2 _x − x_<sup>2</sup> = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_=</sup><sup>_f ′_(</sup><sup>_x_) = 2</sup><sup>_−_2</sup><sup>_x_=</sup><sup>_⇒_2</sup><sup>_−_2</sup><sup>_x_= 0</sup>

- (c) _f_ ( _x_ ) = ( _x −_ 2)<sup>2</sup> = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_=</sup><sup>_f ′_(</sup><sup>_x_) = 2(</sup><sup>_x−_2)=</sup><sup>_⇒_2(</sup><sup>_x−_2) = 0</sup>

   - _x_ = 2 is a stationary value and this is a minimum.

- (d) _f_ ( _x_ ) = ( _x −_ 2)(3 _− x_ ) = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_=</sup><sup>_f ′_(</sup><sup>_x_) = (3</sup><sup>_−x_)</sup><sup>_−_(</sup><sup>_x−_2) = 5</sup><sup>_−_2</sup><sup>_x_=</sup><sup>_⇒_5</sup><sup>_−_2</sup><sup>_x_= 0</sup> _x_ = 2 _._ 5 is a stationary value and this is a maximum.

- (e) _f_ ( _x_ ) =<sup>_<u>x</u>_</sup> 3<sup>3</sup><sup>_−_4</sup><sup>_x_2 + 15</sup><sup>_x_+ 5=</sup><sup>_⇒_</sup> _d dxf_<sup>=</sup><sup>_f ′_(</sup><sup>_x_) =</sup><sup>_x_2</sup><sup>_−_8</sup><sup>_x_+ 15 = (</sup><sup>_x −_3)(</sup><sup>_x −_5)=</sup><sup>_⇒_</sup> ( _x −_ 3)( _x −_ 5) = 0

   - _x_ = 3 and _x_ = 5 are stationary values, and they are a maximum and a minimum respectively.

- (f) _f_ ( _x_ ) = _ln_ ( _x_ ) _− x_ = _⇒_<sup>_d_</sup> _dx_<sup>_<u>f</u>_=</sup><sup>_f ′_(</sup><sup>_x_) =</sup><sup><u>1</u></sup> _x_<sup>_−_1=</sup><sup>_⇒_</sup><sup><u>1</u></sup> _x_<sup>_−_1 = 0</sup> _x_ = 1 is a stationary value and this is a maximum.

**Question 4.2** : Write down an equation describing the problem: _x_ + _y_ = 9, where _x × y_<sup>2</sup> is a maximum. Using the first equation we can write: _x_ = 9 _− y_ , sub this in the second to give:

so expanding, differentiating and setting to zero gives

Factorise to get

which gives us _y_ = 0 or _y_ = 6 as stationary values. We see that _y_ = 0 is a minimum and _y_ = 6 is a maximum. Choosing _y_ = 6 gives _x_ = 9 _−_ 6 = 3 and the maximum value is 3 _×_ 6<sup>2</sup> = 108.

**Question 4.3** : We should write down the relevant equations and constraints. Since the box has a square base (i.e _l_ = _w_ ) we can rewrite the equations as

69

Since we want to maximise _V_ and use a derivative, can we re-arrange the expressions to express _V_ with regards to _w_ ? We can. An expression for _h_ is given as:

Substitute this in to the expression for _V_ to arrive at the following expression that we will need to maximise:

The derivative is given by:

Set this to 0 and rearrange to find we have one position solution as per the following:

Since we cannot get negative width, we see the volume is maximised at

so the optimum box is a cube. The maximum volume is:

**Question 4.4** : This is very similar to the previous question. We should write down the relevant equations and constraints. The rectangular box has a square base (i.e _l_ = _w_ ) and it is open so we can write the equations as

Note that we’re leaving one square side off the constraint. Since we want to maximise _V_ and use a derivative, can we re-arrange the expressions to express _V_ with regards to _w_ ? We can. An expression for _h_ is given as:

70

Chapter 4. Optimisation and Properties of Derivatives

Substitute this in to the expression for _V_ to arrive at the following expression that we will need to maximise:

The derivative is given by:

Set this to 0 and rearrange to find we have one position solution as per the following:

Since we cannot get negative width, we see the volume is maximised at

The maximum volume is:

#### **Question 4.5** :

- (a) See table below: _r_ = 0 _._ 04 m seems to minimise the surface area required.

|Radius|Height for volume to equal 330 ml|Surface area of aluminium|
|---|---|---|
|0.010|1.050|0.067|
|0.020|0.263|0.036|
|0.030|0.117|0.028|
|0.040|0.066|0.027|
|0.050|0.042|0.029|
|0.060|0.029|0.034|
|0.070|0.021|0.040|

- (b) Since we need to minimise the surface area, we need to rearrange the volume to get an expression for _h_

Substitute this into the surface area equation to get a function in terms of _r_

71

The derivative is given by:

Set this to 0 and rearrange to find we have one position solution as per the following:

we see the surface area is minimised at

#### **Question 4.6: A gold seam optimisation problem.**

(a) Firstly, write down the equation for profit, _P_ = _G −C_ :

Find<sup>_<u>dP</u>_</sup> _dn_<sup>:</sup>

Use the chain rule to differentiate _f_ =<sup><u>1</u></sup> _n_<sup>_<u>×</u>_</sup> +<sup><u>10</u></sup> 1<sup>5call</sup><sup>_u_=</sup><sup>_n_+1, so</sup><sup>_f_=</sup><sup><u>1</u></sup><sup>_<u>×</u>_</sup> _u_<sup><u>105</u></sup> and then

so we see that

Now set to zero and solve for _n_ to find the stationary values:

We see that this function has two stationary values:

So the answer is that the profit is maximised after 9 days. Substitute this into the formula for _P_ to get _P_ = 80 _,_ 000 profit after 9 days.

72

Chapter 4. Optimisation and Properties of Derivatives

(b) To find the snag, we differentiate _G_ with respect to _n_ :

Note that the first term is a constant so, when differentiated it goes to zero. To differentiate �0 _._ 01 _n_<sup>2</sup> + 1� exp ( _−_ 0 _._ 1 _n_ ) we use the product rule. Split the function and differentiate:

Apply the product rule:

Now set to zero and solve for _n_ to find the stationary values:

We see that this function has a stationary value:

So the answer is that the snag occurs after 10 days. This is an example of a saddle point.

**Question 4.7: Geoengineering.** For the problem you should first find<sup>_<u>dT</u>_</sup> _dC_<sup>,</sup>

73

Now set to zero and solve for _C_ to find the stationary values:

Substitute _d_ = 2 _×_ 10<sup>_−_4</sup> to find the amount to be spent on geoengineering, _C_ , that minimises the total cost, _χ_ :

therefore this means that we can only _increase_ the temperature by implementing the scheme! It should not go ahead.

# 5. Second Order Derivatives & Root Finding

### 5.1 Overview

In Chapters 2–4, we learned how to calculate derivatives of functions, which can be used tells us a rate of change and help us identify various properties and behaviors of functions. In this Chapter, we conclude our study of differentiation by examining the further properties of functions through the **second-order derivative** and exploring how derivatives can be applied to locate the **roots of functions** .

### 5.2 Second-order derivatives

In the previous Chapter, we explored the **properties of derivatives** and how to use them to identify the **stationary values** of functions. These properties are invaluable for optimising functions or processes. However, to determine whether a stationary value represents a maximum or a minimum, we relied on either (a) looking the function’s plot or (b) evaluating the original function on either side of the stationary value. There is, however, a formal method for verifying this, which involves something called the **second-order derivative** .

Up to this point, we have only differentiated functions once. For a given function _f_ ( _x_ ), its derivative is expressed as:

This is referred to as the **first-order derivative** . However, differentiation can be carried out multiple times. By differentiating a function again, we obtain the **second-order derivative** ,

Chapter 5. Second Order Derivatives & Root Finding

76

which is defined as:

The second-order derivative has some very interesting and useful properties. Previously we saw that the first-order derivative, _f_<sup>_′_</sup> ( _x_ ) tells us about the rate of change of a function, _f_ ( _x_ ). The second-order derivative, _f_<sup>_′′_</sup> ( _x_ ), goes a step further by telling us how the rate of change, _f_<sup>_′_</sup> ( _x_ ), itself is changing. This has many applications in physics, such as investigating stationary values or determining steady state, but to understand why its useful, imagine you’re driving:

1. Distance is how far you’ve traveled over time (call this _x_ = _f_ ( _t_ ))

2. Speed tells us how fast you’re traveling at any given moment. It’s the rate at which your distance changes over time. Mathematically, it’s the first-order derivative of distance:

3. Acceleration measures how quickly your speed is increasing or decreasing. It’s the rate of change of velocity over time. Mathematically, this is the second derivative of distance (or the first derivative of velocity):

### Stationary values

These properties of second-order derivative make them very useful for understanding the nature of stationary points, which are the points where _f_<sup>_′_</sup> ( _x_ ) = 0. Here’s how _f_<sup>_′′_</sup> ( _x_ ) helps us classify these points:

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_)</sup><sup>_<_0, then</sup><sup>_f_(</sup><sup>_x_) has a local maximum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_)</sup><sup>_>_0, then</sup><sup>_f_(</sup><sup>_x_) has a local minimum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_) = 0, then it is not possible to conclude anything about the point</sup><sup>_x_.It could</sup> be saddle point (neither a maximum nor a minimum) so we need to either visually inspect the stationary value or or further evaluation of _f_ ( _x_ ) is needed.

Let’s return to an example from the previous Chapter.

**Example 5.1** : Let’s consider the cubic function

This function is shown in the top panel of Figure 4.2, over the range: _−_ 10 _< x <_ 5. In the previous Chapter, we differentiated this function to find:

77

By solving the quadratic equation, we determined the stationary points at _x_ = _−_ 5 and _x_ = 1. From the graph, these points appear to be a maximum and a minimum, respectively. To confirm this, let’s examine the second derivative:

Now, we evaluate the second derivative at the stationary points:

Since _f_<sup>_′′_</sup> ( _x_ ) _<_ 0 at _x_ = _−_ 5 and _f_<sup>_′′_</sup> ( _x_ ) _>_ 0 at _x_ = 1, we can confirm these stationary values are a local maximum and minimum respectively.

### Steady state

You may not be familiar with the concept of **steady-state** . When a system is in steady-state, the key variables that describe the system’s behavior do not change over time. In a chemical system, this means that even though processes are happening that could cause change, the system’s variables stay the same. For this to happen, there must be a continuous flow of materials through the system.

Let’s look at an example using Figure 5.1. Imagine water is being poured into a container that has an outlet on the side. At first, when the water level is below the outlet, the water level in the container rises over time, as shown in (a). But once the water level reaches a certain height, the rate at which water is entering the container equals the rate at which it is leaving through the outlet. At this point, the water level stops rising and stays constant, as shown in (b). This is when the system has reached a steady state.

To describe the total volume of water in the system, let’s denote it as _w_ . In our differential equation, we aim to express how this total volume changes. We can say that the rate of change of the water volume remains constant, either with respect to time or space. This rate of change can be written as:

This equation means that the rate at which the total volume of water _w_ is a function of time and multiple sources and sinks of water which I have expressed as _x_ 1, _x_ 2. Using the above definition of steady state, here the rate of change does not change over time, we can take the derivative of the equation above:

78

Chapter 5. Second Order Derivatives & Root Finding

**Figure 5.1:** Diagram showing a system in (a) transient state and (b) steady state.

This equation tells us that the second derivative of _w_ with respect to time is zero. In other words, the rate of change of the volume of water is not changing—it remains constant. This implies that there is a steady flow, and the total amount of water in the system remains constant. Let us work through an example.

**Example 5.2** : Imagine an object moving under constant acceleration. Mathematically, we can express the fact that acceleration is constant by saying:

This means the rate of change of acceleration is zero. Since acceleration is the rate of change of velocity (see above), we can also write this as:

This tells us that the velocity is not changing in a way that would cause acceleration to vary. If we had an expression for velocity as a function of time, we could differentiate that expression and check if this is true. Take a hypothetical example where the velocity is given by

where _t_ is time (in seconds) and _a_ is a constant (in _m/s_<sup>_−_2</sup> . We can show that the secondorder derivative is 0 through the following steps:

Since _α_ is a constant, the acceleration does not change over time. Differentiating confirms that the acceleration is constant, and the second derivative of velocity with respect to time is zero, as expected and the system is in steady state.

79

**Figure 5.2:** Function that varies non-linearly with _x_ and example tangents at different points. Credit to `https://tutorial.math.lamar.edu/Classes/CalcI/NewtonsMethod.aspx`

### 5.3 Finding roots of equations: Newton-Raphson method

We’ve been discussing how derivatives help us understand change. So far, most of our examples have been a combination of hypothetical and real-world examples on using derivatives to calculate the gradient (or slope) of a line. While this is a useful concept, it can sometimes be difficult to see how it applies to real-world situations. When we start learning about integration, we’ll see that we can reverse the process of differentiation. This allows us to calculate actual values (or "absolute values") from the past and predict future values.

But derivatives have other practical uses too. For example, one important application is **finding the roots** of a function, which is where a **function equals zero** . You have encountered these when finding stationary values! Take a look at Figure 5.2, which shows a typical function _y_ = _f_ ( _x_ ). Our function line clearly shows that when _x_ = 0, _y_ has a negative value and as _x_ increases, _y_ increases. At some point, the function crosses the _x_ -axis and becomes zero. How do we find out when this occurs?

In some cases, we might be able to solve the equation directly to find the root (see above). However, consider the function:

In this case, it’s difficult to find where _f_ ( _x_ ) = 0 using simple algebra. Instead, we could iteratively insert values for _x_ and gradually work towards smaller and smaller values for _y_ . By doing this repeatedly, we could gradually get closer to the root. However, this approach

80

Chapter 5. Second Order Derivatives & Root Finding

is not only time-consuming and laborious, but also impossible to visualise for complex functions. What if there were a better way? What if we could use the information provided by the function’s gradient (or slope), that is, the tangent line to help us find the root more efficiently?

Imagine our first value for _x_ is denoted as _x_ 0. At this point, the value of the function _f_ ( _x_ 0) _>_ 0, and we can calculate the slope (or gradient) at _x_ 0, which we write as _f_<sup>_′_</sup> ( _x_ 0). This slope represents the tangent line to the curve at _x_ 0. Now, follow the tangent line from _x_ 0 until it crosses the x-axis. The tangent crosses the x-axis and arrives at another value for _x_ which we shall denote as _x_ 1. We can write the equation of the tangent line as follows:

To find where the tangent line crosses the x-axis, we set _y_ = 0:

Rearranging to get _x_ 1:

So, _x_ 1 is the new estimate for the root of the function. Next, to find _x_ 2, we repeat the same process, using _x_ 1 as the new starting point and get:

As we continue this process, the values of _x_ will get closer and closer to the true root. However, we may never reach an exact value of _y_ = 0. Instead, we define a tolerance level for what we consider as _y_ = 0 or the percentage change in _x_ . For example, we may stop the iterations if _y_ is smaller than a certain threshold (e.g., _y <_ 0 _._ 001) or if the change in _x_ is very small (e.g., less than 0.01%). This depends on the nature of the problem you are trying to solve. There is no guarantee this method will converge to a root. Indeed there are cases where each iteration will get worse and worse. However it is good and simple method for root finding in cases where we cannot easily access an analytical solution. The general formula for the Newton-Raphson method is:

This formula is used iteratively to find increasingly accurate approximations to the root of the function. Let’s consider an example.

81

**Example 5.3** : Suppose we want to find the root of this equation to an accuracy of 6 decimal places:

Since it is not feasible to solve _f_ ( _x_ ) = 0 through simple rearrangement, we employ Newton’s method. This requires the derivative of _f_ ( _x_ ), which is:

To arrive at the value for _x_ at the root, we need an initial guess. This can be important. We are told, on this occasion, the root exists somewhere between _x_ = 3 and _x_ = 4. If we start at _x_ 0 = 3 _._ 5, what is the value for _x_ 1? Using Newton’s method, the next approximation, _x_ 1, is computed as:

In the class examples, you are asked to proceed with this problem until you arrive at an approximation for the root which is _≈_ 3.275601.

82

Chapter 5. Second Order Derivatives & Root Finding

## Exercises

### Algebraic problems

**Question 5.1** : Find the second order derivative of the following functions (we have seen

two of these formulas when we practised using the product and quotient rule):

- (a) _y_ = _~~√~~ x_<sup>2</sup> + 25

- (b) _y_ =<sup>_<u>x</u>_</sup> 4<sup>5+</sup><sup>_x_3 +12</sup>

- (c) _f_ ( _x_ ) = _x_ exp ( _x_ )

- (d) _P_ ( _z_ ) = _P_ 0 exp � _− Ra_<sup>_<u>g</u>_</sup> _T_<sup>_z_</sup> � which is the same simplified form of the hydrostatic equation we have met before, where _P_ 0, _g_ , _Ra_ and _T_ are constants.

**Question 5.2** : Find the stationary values of the following functions:

- (a) _f_ ( _x_ ) =<sup>_<u>x</u>_</sup> 3<sup>3+</sup><sup>_<u>x</u>_</sup> 2<sup>2</sup><sup>_−_30</sup><sup>_x_+5</sup> (b) _f_ ( _x_ ) = _x_<sup>3</sup>

Verify whether the stationary values are maxima, minima or saddle points.

**Question 5.3** : Complete Chapter 5 Exercise 3, and use Newtons Method to find the root (accurate to 6 decimal places) of following function:

Assume the root is between _x_ = 3 and _x_ = 4. Newtons method is used for finding the root, so you need to move all terms to one side. Use a first guess of 3.5.

**Question 5.4** : Using Newtons method, find the second guess of the root (i.e. _x_ 2) for the following functions:

- (a) _f_ ( _x_ ) = _x_<sup>3</sup> _−_ 7 _x_<sup>2</sup> + 8 _x −_ 3, with _x_ 0 = 5

- (b) _f_ ( _x_ ) = _sin_ ( _x_ ) _− ln_ ( _x_ ), with _x_ 0 = 2

- (c) _f_ ( _x_ ) = _xcos_ ( _x_ ) _− x_<sup>2</sup> , with _x_ 0 = 1

**Question 5.5** : Use Newtons method to find all the roots of the following equation to 3 decimal places. You may use a starting guess of _x_ 0 = _−_ 3 _._ 5 and _x_ 0 = 4 _._ 5 to find the left and right sided roots respectively:

Take a look at Figure 5.3. We seem to have 3 roots, so use this information to confirm the values of these roots to within 3 decimal places.

83

**Figure 5.3:** Function that varies according to a cubic function

### Real-world problems

**Question 5.6** : An industrial incinerator produces a steady output of particulate matter having a concentration of _C_ 0 = 1 _._ 0 mg m<sup>_−_3</sup> of air at the chimney. 1 km away from the incinerator plant the concentration is _C_ 1 _km_ = 0 _._ 1 mg m<sup>_−_3</sup> . Some houses are a distance of 500 m away from the plant. The equation that lets us calculate the concentration as a function of distance from the incinerator is provided by the following expression.

Prove that the flux is in steady state.

**Question 5.7** : At 3km below the surface there is a hot granite bed, with a temperature of 250<sup>_◦_</sup> C. The temperature just below the surface the temperature stays relatively constant at 10<sup>_◦_</sup> C. Fourier’s law in 1-d has been used to construct the following expression.

Is the system in steady state?

**Question 5.8** : Imagine you are a business analyst for a company that sells a product. The company wants to model its gross profit, _P_ ( _x_ ), based on the number of units sold, where _x_ represents the number of units sold in thousands. The profit function is given by:

- (a) Determine the number of units sold where the gross profit is at its minimum. _HINT: You may need to apply Newton’s method to find the root of the derivative in order to locate the stationary point. Use a starting guess of x_ 0 = 3 _and find the root to 3 decimal places._

- (b) Confirm that the gross profit is minimised at this value.

84

Chapter 5. Second Order Derivatives & Root Finding

## Solutions

**Question 5.1** :

- (a) For the first-order derivative (from Chapter 3 Question 5.4(a)), we split the function and differentiated using the chain rule:

Apply the chain rule:

For the second-order derivative (from Chapter 3 Question 5.4(d)), we split the function and differentiate using the quotient rule:

Apply the quotient rule:

- (b) The first-order derivative is provided by the following expression:

Therefore the second-order derivative is provided by the following expression:

- (c) For the first-order derivative (from Chapter 3 Question 5.2(a)), we split the function and differentiated using the product rule:

85

Apply the product rule:

To compute the second-order derivative, note that the first term, _exp_ ( _x_ ), remains unchanged due to the exponential derivative rule. For the second term, _xexp_ ( _x_ ), the product rule must be applied again. Interestingly, this term is the same structure as the original function, allowing us to substitute it back and simplify further, yielding:

- (d) Our final equation is the hydrostatic equation. For the first-order derivative (from Chapter 2 Question 5.8), we that this is an exponential function with multiple constants so:

To obtain the second derivative,<sup>_<u>d</u>_2</sup><sup>_<u>P</u>_, we again recognise there are multiple constants</sup> _dz_<sup>2</sup> and retain those that multiple an expression involving z:

which we can further simplify to the following:

Alternatively, notice that we can write

so then

**Question 5.2** : Find the stationary values of the following functions:

- (a) We find the first derivative

86

Chapter 5. Second Order Derivatives & Root Finding

and solve _f_<sup>_′_</sup> ( _x_ ) = 0 to find stationary points

So we see two stationary values at _x_ = _−_ 6 and _x_ = _−_ 5. We then use the second derivative to classify the stationary values. The second derivative is:

At the stationary values, the second derivative is:

so _x_ = _−_ 6 is a maximum and _x_ = 5 is a minimum.

(b) We find the first derivative

and solve _f_<sup>_′_</sup> ( _x_ ) = 0 to find stationary points

So we see a stationary value at _x_ = 0. We then use the second derivative to classify the stationary point. The second derivative is:

At the stationary values, the second derivative is:

Since _f_<sup>_′′_</sup> (0) = 0, we cannot classify the stationary point using the second derivative test. Instead, consider the behaviour of _f_ ( _x_ ) = _x_<sup>3</sup> :

- <sup>For</sup><sup>_x <_0,</sup><sup>_f ′_(</sup><sup>_x_)</sup><sup>_>_0, indicating</sup><sup>_f_(</sup><sup>_x_) is increasing.</sup>

- <sup>For</sup><sup>_x >_0,</sup><sup>_f ′_(</sup><sup>_x_)</sup><sup>_>_0, indicating</sup><sup>_f_(</sup><sup>_x_) is still increasing.</sup>

Thus, _x_ = 0 is a saddle point.

**Question 5.3** : In this Question 5.we are asked to find a root within a specified accuracy, assuming it is between _x_ = 4 and _x_ = 6 for the following function:

87

As we saw in Chapter 5, we need to first derive our derivative function which, in this case, is:

We iterate through the Newton method:

until our only changes at an accuracy greater than 6 decimal places (i.e. we can stop at the chosen level of tolerance).

so the root of _f_ ( _x_ ) to 6 decimal places is 3.275601.

**Question 5.4** : In this Question 5.we are asked to find a root after two iterations of Newtons method. However, you may choose your own stopping criteria for practice

- (a) We need to derive the derivative of the function

which takes the form:

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 5:

so the root of _f_ ( _x_ ) after two iterations is 5.71875.

- (b) We need to derive the derivative of the function

88

Chapter 5. Second Order Derivatives & Root Finding

which takes the form:

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 2:

so the root of _f_ ( _x_ ) after two iterations is 2.219185.

(c) We need to derive the derivative of the function

To differentiate _h_ ( _x_ ) = _xcos_ ( _x_ ) we split the function and differentiate using the product rule:

Apply the product rule:

so we see that

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 1:

so the root of _f_ ( _x_ ) after two iterations is 0.744094.

89

**Question 5.5** : In this Question 5.we are asked to find all the roots to 3 decimal places for the following function:

In this problem we have been given a figure to help us decide on where to start our initial guess for each root. Since we have 3 roots (according to what we can see), it makes sense to select values near these points. We have been given _x_ 0 = _−_ 3 _._ 5 and _x_ 0 = 4 _._ 5 as starting values but there is also a root near zero so lets also use _x_ 0 = 0 as the final starting value to check this. We need to derive the derivative of _f_ ( _x_ ), which takes the form:

We then apply the Newton method:

for each starting guess until the root is accurate within 3 decimal places:

- <sup>For</sup><sup>_x_</sup> 0<sup>=</sup><sup>_−_3</sup><sup>_._5:</sup>

- <sup>For</sup><sup>_x_</sup> 0<sup>= 4</sup><sup>_._5:</sup>

so the three roots of _f_ ( _x_ ) to 3 decimal places are -3.442, 0.066 and 4.376. Please note that the following solution is dependent on the starting guess so your results may change. You may even find your value grows! So care is needed when there are multiple roots.

**Question 5.6** : We need to prove that an industrial incinerator emissions

90

Chapter 5. Second Order Derivatives & Root Finding

are in steady state. To do this we differentiate, the

which is constant, so the flux is in steady state. Verify this by taking the second derivative

As the second derivative is zero this verifies that the flux is in steady state.

**Question 5.7** : We need to prove that a system

are in steady state. To do this we differentiate, the

which is constant, so the system is in steady state. Verify this by taking the second derivative

As the second derivative is zero this verifies that the system is in steady state.

#### **Question 5.8** :

(a) We need to determine where the profit

is at its minimum, which corresponds to a stationary point. To find this, we differentiate _P_ ( _x_ ) and set the derivative equal to zero:

Since this equation cannot be solved algebraically, we use Newton’s method to approximate the root. It’s important to note that we are solving for the root of<sup>_<u>dP</u>_</sup> _dx_<sup>,</sup> not _P_ ( _x_ ). Let us define _f_ ( _x_ ) =<sup>_<u>dP</u>_</sup> _dx_<sup>, and compute its derivative:</sup>

Using Newton’s method, the iterative formula is:

91

Starting with an initial guess of _x_ 0 = 3, we iterate until the values converge to an accuracy of three decimal places:

Thus, the root of _f_ ( _x_ ) to three decimal places is _x_ = 2 _._ 833. Therefore, the profit is at its minimum when approximately 2833 units are sold.

- (b) We use the second derivative to classify stationary values. We already calculated the second derivative in the last part through Newton’s method:

so at the 2.833 the second derivative is

Since the second derivative is positive, then the profit is definitively minimised at 2.833.

# 6. Introduction to Integration

### 6.1 Overview

Throughout Chapters 1–5, we considered at differentiation as a topic. This is the process of finding a rate of change (or gradients) of functions or processes. However, there may be times where we want to do the opposite, i.e. we know the rate of change but want to know the volume or total change over an interval. For example, we might know how fast a car is traveling and we want to know how far that car has traveled over time. This is where **integration** comes in.

### 6.2 Integration as the reverse of differentiation

Integration is the **reverse** of differentiation (Figure 6.1). Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values. For example, if a derivative function tells us how much the volume of water in a tank is changing over time, integrating that function tells us how much water is in the tank at a given time or how much the volume of water has changed over a specific time period.

To integrate a differential equation therefore requires us to reverse the steps taken to get to that point. At first glance, this seems like an impossible task since it is likely we did not generate the differential equation. However you will start to recognise forms of equations and what steps you therefore need to carry out.

Let us keep the water example for now to explore this using a graph. If we consider the

94

Chapter 6. Introduction to Integration

**Figure 6.1:** Interplay between differentiation and integration throughout this course.

flow rate of water through a hole we might obtain a graph similar to Figure 6.2. The top graph plots the rate of change as a function of time, thus the derivative function. Look at the middle part, between 30 and 70 seconds. Here the rate of change is constant. So, after 1 second, the water has increased by a fixed amount. In the next second, the water increases by the same amount. Now we can consider working out the area under the curve to arrive at the total amount. Indeed, if we want to describe how the volume of water in the system changes with time, _t_ , then we can calculate it from the above graph by finding the area under the graph from _Time_ = 0 to any time, _t_ . For Fig. 6.2 we can find the area by adding up areas of triangles and rectangles.

Often flow rate curves are not as simple as in Fig. 6.2. Fig. 6.3 shows the curve _f_ ( _x_ ) = _−_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ and a schematic of how to estimate the area under the curve. Basically it shows that we can split the area into lots of smaller rectangles, with a base of length ∆ _x_ and a height equal to _f_ ( _x_ ), the value of the function at _x_ . The area of each rectangle is then _f_ ( _x_ ) _×_ ∆ _x_ and the area of the curve is the sum of all of these rectangles. This is a **numerical approximation** method, similar to central differences method for differentiation, representing a manual integration of the function.

We can use (analytical) _integration_ to find a function that describes the area under the curve. In this case the function<sup>_−_</sup><sup><u>0</u></sup><sup>_<u>.</u>_</sup><sup><u>1</u></sup><sup>_<u>x</u>_3</sup> + 5 _x_<sup>2</sup> describes the area under the curve between 3 _x_ = 0 and _x_ . This is shown in the bottom graph of Figure 6.3.

Because integration can be seen as a _summing up_ of lots of smaller rectangles we write it formally with an S-shaped symbol:

95

<!-- Start of picture text -->
300<br>250<br>200<br>150<br>100 Area=base ×  height<br>50 Area=0.5base ×  height × Area=0.5base ×  height ×<br>0<br>0 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>4<br>2  x 10<br>1.5 Area under the curve<br>1<br>0.5<br>0<br>0 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>Flow rate (milli−litres per second)<br>Total volume (milli−litres)<br><!-- End of picture text -->

**Figure 6.2:** Top shows a graph of flow rate of a substance vs time; bottom shows the volume of that substance vs time (i.e. the area under the top curve). We see that the volume increases at a non-constant rate at first, but between 30 and 70 seconds the volume increases according to a straight line. After 70 seconds the volume increases at a non-constant rate, before leveling off

**Figure 6.3:** Top shows the function _f_ ( _x_ ) = _−_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ . The schematic shows a way of estimating the area under the curve by dividing the area into lots of rectangles. Bottom shows a function describing the area from _Time_ = 0 to a later time, _t_ .

96

Chapter 6. Introduction to Integration

here the � symbol represents a ‘summing up’. The _dx_ represents the length of the base of each rectangle (i.e. ∆ _x_ ) and the sub and super-scripts on the � are known as _limits of integration_ . In this example it means find the area under the curve between 0 and _x_ .

The _integral_ of some simple functions of _x_ are shown below:

|Function|Integral|
|---|---|
|constant|_constant ×x_+_d_|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|2_x_<sup>4</sup>|2_x_<sup>5</sup><br>5 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|

where _d_ is a constant. So we see that given these simple functions of _x_ we can calculate the integral of them by **raising the power of** _x_ **by 1** and **dividing by the new power that** _x_ **is raised** . Why do we add the constant, _d_ ? Well, integration is the opposite of differentiation (remember differentiation of a constant is zero) and differentiation "loses" any constant that might have been present in the original function so we add this in. For standard integration we cannot say what the constant is: it can take on any value so we just call it a **constant** . For this reason it is called **indefinite integration** .

To find the **area under a curve** we have to perform **definite integration** between limits. This means that we calculate the integral (as in the table above) then evaluate the integral for two values of _x_ , and calculate the difference.

**Example 6.1** : Let’s find the area under the curve _y_ = _x_<sup>2</sup> from _x_ = 1 to _x_ = 2. We write the integration out as follows:

note that we calculate the integral and then evaluate the function by putting in both limits and calculating the difference.

97

Note that when calculating a difference the constant in the integration, _d_ , disappears so we do not have to consider it.

In the table below you can find a list of common integrals we will use through this course:

|Differential equation <sup>_dy_</sup><br>_dx_|Integral,_y_|
|---|---|
|constant|_constant ×x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup><br>_ax_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_ax_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_)+_d_|
|_cos_(_x_)|_sin_(_x_)+_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

### 6.3 Solving Ordinary Differential Equations (ODEs)

Now we can change our narrative a little with regards to solving problems in Physics. So far, we have been given _f_ ( _x_ ) and asked to find<sup>_d_</sup> _dx_<sup>_<u>f</u>_, but now we are starting with</sup><sup>_d_</sup> _dx_<sup>_<u>f</u>_instead.</sup> We often refer to<sup>_d_</sup> _dx_<sup>_<u>f</u>_as</sup><sup>**Ordinary Differential Equations (ODEs)**.</sup>

The theoretical base of many of the processes we are interested in are written in the form of ODEs. To predict values or properties in the past or future, we can integrate ODEs either without limits, or between specific limits. In this Chapter, we solve the ODEs that describe radioactive decay and Newtons laws of motion, following some algebraic exercises.

The radioactive decay and hydrostatic equation have the same algebraic formulation. They are both equations that describe a logarithmic change in one variable as a function of another. Why is that? By looking at the **ODE** that describes a rate of change:

then we know the solution to this general equation will take the form of the following equation:

In the following, we relate the derivative with the analytical integrals. For more information you may refer to Chapter 11 that covers all of the physical theories we cover in this course.

98

Chapter 6. Introduction to Integration

**Example 6.2: The radioactive decay equation.** For _α_ and _β_ decay we can apply the radioactive decay equations. The law states that the number of decays per unit time is proportional to the number of unstable nuclei:

where _λ_ is a constant for a specific isotope and _N_ is the number of unstable nuclei. This kind of law is quite common in physics. It is to be expected since if you have more unstable nuclei you would expect to observe more decays per second and vice versa. Another statement of this law is that the number of unstable nuclei decays away with time:

where _N_ 0 is the number of unstable nuclei at time _t_ = 0. The constant _λ_ is used to characterise how quickly the unstable nucleus decays. To get this solution, we use a technique called **separation of variables** . We rearrange the decay equation so that all _N_ ’s are on one side and all _t_ ’s are on the other and then integrate both sides:

We first divide both sides by _N_

Then multiply both sides by _dt_

Then integrate both sides

The integral � <u>1</u> _x_<sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

and if we say at _t_ = 0, _N_ = _N_ 0 we get that _c_ = ln _N_ 0, we therefore obtain

as the solution to Newton’s radioactive equations.

99

**Example 6.3: The hydrostatic equation.** The density of air depends on the pressure, _<u>P</u> P_ , and temperature of the air, _T_ , (through the ideal gas law): _ρ_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J</sup> kg<sup>_−_1</sup> K<sup>_−_1</sup> . So we can write:

We can use separation of variables and integration again to show that the solution to this ODE is:

In actual fact the assumption that the temperature is constant is not true as it usually decreases with height in the atmosphere at about 10<sup>_◦_</sup> C km<sup>_−_1</sup> (i.e. a drop of 10<sup>_◦_</sup> C for every km). When we take into account that temperature drops with altitude the hydrostatic equation becomes:

which has an analytical solution of:

but we need some fancier integration techniques, which we will see later, to be able to show this!

100

Chapter 6. Introduction to Integration

## Exercises

### Algebraic problems

**Question 6.1** : Find the following indefinite integrals:

- 2

- (a) � _x dx_

- (b) � 12 _x_ 4 _dx_

- (c) � _sin_ ( _x_ ) _dx_

- (d) � _cos_ ( _x_ ) _dx_

- _x_

- (e) � _e dx_

- 2 _x_

- (f) � _e dx_

- (g) � _x_ 2 + 2 _x_ + 3 _dx_

- (h) � _sin_ ( _x_ )+ _cos_ ( _x_ ) _dx_

- (i) � _e_ 2 _x_ + 2 _xdx_

- _x_

- (j) � _e_ + _cos_ ( _x_ ) _dx_

**Question 6.2** : Find the integrals between the limits specified:

- 10

- (a) �0<sup>_x_2</sup><sup>_dx_</sup>

- 10

- (b) � _−_ 10<sup>_x_2</sup><sup>_dx_</sup> 1

- (c) � _−_ 1<sup>_x_3</sup><sup>_dx_</sup> (d) �080 � _−_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ � _dx_ (e) �050 � _−_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ � _dx_ 1

- (f) �0<sup>exp(3</sup><sup>_x_)</sup><sup>_dx_</sup>

**Question 6.3** : Find the integrals between the limits specified:

- (a) �0 _b_ _<u>hb</u>_<sup>_xdx_(i.e. the area of a triangle with base</sup><sup>_b_and height</sup><sup>_h_)</sup> _b_

- (b) �0<sup>_hdx_</sup>

- _T_

- (c) �0<sup>exp(</sup><sup>_−λt_)</sup><sup>_dt_</sup>

_n_ _<u>axn</u>_ +1 **Question 6.4** : Use the fact that � _ax_ = _n_ +1<sup>+</sup><sup>_d_to integrate the following:</sup>

- (a) _f_ ( _x_ ) =<sup>_√_</sup> _<u>x</u>_

- (b) _f_ ( _x_ ) = _x_<sup><u>12</u></sup> <u>1</u>

- (c) _f_ ( _x_ ) = _~~√~~_ _<u>x</u>_

**Question 6.5** : Use separation of variables to integrate the following ODE:

101

### Real-world problems

**Question 6.6** : Water flows down a river at a rate<sup>_<u>dW</u>_</sup> _dt_<sup>(m3 s</sup><sup>_−_1) described by:</sup>

Determine how much water (m<sup>3</sup> ) flows down the river between _t_ = 100 and _t_ = 700 s?

**Question 6.7** : The rate (in mm/hr) that rain falls from a cloud between time _t_ = 3 _._ 5 and _t_ = 6 _._ 5 hours can be approximated by _−_ 3 _t_<sup>2</sup> + 30 _t −_ 65. Calculate the total precipitation, in mm, that falls between _t_ = 3 _._ 5 and _t_ = 6 _._ 5 hours.

**Question 6.8: The radioactive decay equation.** Solve the radioactive decay equation by separation of variables and integration. Recall that it states that the number of decays per unit time is proportional to the number of unstable nuclei:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay constant, _λ_ =<sup><u>ln2</u></sup> _t_ 1 _/_ 2<sup>where</sup><sup>_t_1</sup><sup>_/_2 is the half-life of the sample.</sup>

**Question 6.9** : Imagine a sheep was allowed to graze in a field that had been contaminated by<sup>137</sup> Cs released at Chernobyl. About a kilogram of<sup>137</sup> Cs was released, but only a small fraction of this was atomised and subsequently spread over a very wide area. The sheep had been eating grass that contained a surface density of radioactive nuclei. That density changes over time as the radioactive material decays. If we assume that the the surface density of atoms starts at a value of 2 _._ 16 _×_ 10<sup>9</sup> _m_<sup>_−_2</sup> , and the surface area _A_ is 7.47 _m_<sup>2</sup> , integrate the following equation to calculate the number of atoms ingested over 1 year:

where _N_ ( _t_ ) is the radioactive decay equation. Note that,<sup>137</sup> Cs is a beta emitter with a half life of 30 years (it decays to<sup>137</sup> Ba).

**Question 6.10: The hydrostatic equation.** Solve the hydrostatic equation by separation of variables and integration. Recall that it states the density of air at altitude _z_ depends on _<u>P</u>_ the pressure, _P_ , and temperature of the air, _T_ , (through the ideal gas law): _ρ_ = _RaT_<sup>, where</sup> _Ra_ = 287 J kg<sup>_−_1</sup> K<sup>_−_1</sup> :

102

Chapter 6. Introduction to Integration

## Solutions

**Question 6.1** :

- (c) � _sin_ ( _x_ ) _dx_ = _−_ cos( _x_ )+ _d_

- (d) � _cos_ ( _x_ ) _dx_ = sin( _x_ )+ _d_

- _x x_

- (e) � _e dx_ = _e_ + _d_

- 2 _x_ _<u>e</u>_ 2 _x_

- (f) � _e dx_ = 2<sup>+</sup><sup>_d_</sup> 3

- (g) � _x_ 2 + 2 _x_ + 3 _dx_ = _<u>x</u>_ 3<sup>+</sup><sup>_x_2 +3</sup><sup>_x_+</sup><sup>_d_</sup> (h) � _sin_ ( _x_ )+ _cos_ ( _x_ ) _dx_ = _−_ cos(( _x_ )+ (i) � _e_ 2 _x_ + 2 _xdx_ = _<u>e</u>_ 22 _x_<sup>+</sup><sup>_x_2 +</sup><sup>_d_</sup> _x x_

- (j) � _e_ + _cos_ ( _x_ ) _dx_ = _e_ + sin( _x_ )+ _d_

- (h) � _sin_ ( _x_ )+ _cos_ ( _x_ ) _dx_ = _−_ cos(( _x_ )+ sin( _x_ )+ _d_

**Question 6.2** :

**Question 6.3** : Find the integrals between the limits specified:

**Question 6.5** :We rearrange the decay equation so that all _N_ ’s are on one side and all _t_ ’s are on the other and then integrate both sides:

103

We first multiply both sides by _N_

Then multiply both sides by _dt_

Then integrate both sides

2 _<u>x</u>_ The integral � _x dx_ is equal to 2<sup>so we have</sup>

Rearranging this equation gives us

as the solution to the ODE.

**Question 6.6** : Perform definite integration of the function to get (and using Question 6.4(b)):

**Question 6.7** : Perform definite integration of the function to get:

**Question 6.8** : We use a technique called _Separation of variables_ . We rearrange the decay equation so that all _N_ ’s are on one side and all _t_ ’s are on the other and then integrate both sides:

104

Chapter 6. Introduction to Integration

We first divide both sides by _N_

Then multiply both sides by _dt_

Then integrate both sides

The integral � <u>1</u> _x_<sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

and if we say at _t_ = 0, _N_ = _N_ 0 we get that _c_ = ln _N_ 0, we therefore obtain

as the solution to Newton’s radioactive equations.

**Question 6.9** : We want to perform the integral

where

We integrate this equation we follow the steps below:

Plugging in that _t_ 1 _/_ 2 = 30, _λ_ =<sup>ln</sup> _t_ 1<sup><u>(</u></sup> _/_<sup>2</sup> 2<sup><u>)</u>=ln</sup> 30<sup><u>(2)</u>= 0</sup><sup>_._0231,</sup><sup>_A_= 7</sup><sup>_._47,</sup><sup>_N_0 = 2</sup><sup>_._16</sup><sup>_×_109 we see</sup> that:

105

so 1 _._ 595 _×_ 10<sup>10</sup> atoms we eaten in that time.

**Question 6.10** : We use a technique called _Separation of variables_ . We rearrange the hydrostatic equation so that all _P_ ’s are on one side and all _z_ ’s are on the other and then integrate both sides:

We first divide both sides by _P_

Then multiply both sides by _dz_

Then integrate both sides

The integral � <u>1</u> _x_<sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

and if we say at _t_ = 0, _P_ = _P_ 0 we get that _c_ = ln _P_ 0, we therefore obtain

as the solution to the hydrostatic equation.

# 7. Integration using Newton’s Laws

### 7.1 Overview

In Chapter 6, we presented Integration as the reverse of differentiation. We discussed **definite** and **indefinite** integration and solving **ordinary differential equations (ODEs)** . We continue that here but focus on Newtons laws of motion as a special case.

### 7.2 Newtons laws of motion

Before the 20th century, our understanding of the physical world was built entirely on classical mechanics. More specifically - **Newtonian Physics** . This framework emerged from the collective efforts of the "Scientific Revolution", spanning figures like Nicolaus Copernicus, Galileo Galilei, and Isaac Newton.

Newton’s laws of motion, a cornerstone of classical mechanics, were first presented in `Philosophiae Naturalis Principia Mathematica (1687)` , commonly known as the `Principia` . In 1543, Nicolaus Copernicus proposed a heliocentric model of the universe, placing the Sun rather than Earth at its center. This radical idea laid the groundwork for subsequent contributions by Galileo, Johannes Kepler, and René Descartes, who collectively challenged and replaced the Aristotelian worldview.

In the `Principia` , Newton formulated **three laws** to explain planetary motion, in order to explain why the orbits of the planets are ellipses rather than circles. These laws, however, extend far beyond planetary motion, offering a universal framework for understanding force and motion. Newton’s laws are as follows:

108

Chapter 7. Integration using Newton’s Laws

1. **Law of Inertia:** A body at rest or moving at a constant speed in a straight line will remain in that state unless acted upon by an external force.

2. **Law of Force and Momentum:** The rate of change of a body’s momentum is directly proportional to the force applied, with the change occurring in the same direction as the force (i.e. if a force acts on a body, that body will experience a change in momentum). This is captured in equations you see throughout this course.

3. **Law of Action and Reaction:** When two bodies interact, they exert forces on each other that are equal in magnitude and opposite in direction. You will have likely come across this law before; also known as the law of action and reaction.

In a number of our problems, we solve Newtons second law to predict how fast or far a body will travel down an incline. Since gravity is pulling the body downwards, why doesn’t the body move through the surface? Well, in very simplistic terms the surface applies an equal and opposite force to the body resting on it. In reality, molecular forces that dictate the properties of both the object and surface also play a role but these laws are adequate to explain our observed motion.

### 7.3 Newtons second law of motion

For the remainder of this Chapter, we focus on Newton’s second laws. In this law, we see that acceleration of an object depends on the mass of the object and the amount of force applied. This concerns a change in momentum. Newton’s second law of motion is given by the following equation:

where _F_ is the net force acting on a body that has a mass _m_ and therefore acceleration _a_ .

In Chapter 5, we discussed second-order derivatives and observed that acceleration ( _a_ ) is the rate of change of velocity ( _v_ ), while velocity ( _v_ ) is the rate of change of position or distance ( _x_ ).Newton’s second law can therefore be expressed as an ordinary differential equation:

where these expressions are equal, and we use the fact that _a_ = _v dx_<sup>_<u>dv</u>_for the final expression</sup> (because _v_ =<sup>_<u>dx</u>_</sup> _dt_<sup>, so</sup><sup>_v_</sup> _dx_<sup>_<u>dv</u>_=</sup><sup>_<u>dv</u>_</sup> _dt_<sup>, which is equal to</sup><sup>_a_).</sup>

To help understand how this works, imagine a plane moving through the atmosphere. The plane has a constant mass _m_ and its momentum depends on its velocity _V_ , which is controlled solely by the plane (i.e., there are no external forces acting on it). The change in velocity between any two time points is _m_ ( _V_ 1 _−V_ 0). If we define force as the rate of

109

change of momentum with respect to time, then:

This resembles the calculation of a gradient from Chapter 1! As seen in Chapters 2, taking the limit as _t_ 1 _− t_ 0 _→_ 0, this becomes us the derivative:

By formulating the total forces acting on an object, we can then solve the ODE to as a function of time to tell us something about the processes.

In multiple cases we are presented with problems where an object experiences multiple forces, acting in multiple directions. We will always need to ensure we understand the balance of each for as an algebraic formulation. Let’s work through two examples which you can see Figure 7.1.

**Figure 7.1:** Schematic illustrating forces acting on a body (left) falling downwards and (right) placed on an incline

**Example 7.1: Object Falling in a Vacuum .** Consider an object falling in a vacuum, as shown on the left side of Figure 7.1. In this scenario, the object experiences only Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center. If we assume an object is falling in a vacuum, can we prove that a brick fall the same distance as a feather in the same amount of time? Yes! In a vacuum, there is no air resistance, so the only force acting on the object is gravity, proportional to its mass ( _mg_ ). This allows us to model the motion using a first-order ordinary differential equation (ODE) for velocity:

Canceling the mass ( _m_ ) gives:

Using separation of variables, we can re-write our expression as an integral so we can calculate velocity as a function of time. We integrate to find the velocity, assuming the

110

Chapter 7. Integration using Newton’s Laws

object starts from rest ( _v_ = 0) at _t_ = 0:

Thus, the velocity of any object in a vacuum increases linearly with time, regardless of its mass, therefore, all objects fall at the same velocity with respect to time. However, we want to show that all objects fall the same distance with respect to time. Remember that, velocity is the rate of change for the distance

Integrating again, and assuming the object starts from _x_ = 0 at _t_ = 0, we get:

This final expression for distance shows that all objects fall the same distance (quadratically) in the same amount of time in a vacuum, regardless of their mass.

**Example 7.2: Object on an Incline.** Consider an object resting on an incline, as shown on the right side of Figure 7.1. Again, the object experiences only Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center. Assuming the triangle is a hard object, the forces can be resolved into two components: (i) the force dragging the block down the slope (labeled as _F_ 2) and (ii) the force acting perpendicular to the slope known as the normal force (labeled as _F_ 1). If the gravitational force is given by _mg_ (where _m_ is the object’s mass and _g_ is the gravitational constant), what is the magnitude of both _F_ 1 and _F_ 2? Using trigonometry, we can write these as follows:

We can see that there is an obvious directional component to the motion of this object ( _F_ 2). Assuming that there is no friction acting against the object, we expect the block to travel down the incline. This means the force _F_ 2 can be used to formulate our ODE:

Canceling the mass ( _m_ ) gives:

Using separation of variables, we can re-write our expression as an integral so we can calculate velocity as a function of time. We integrate to find the velocity, assuming the object starts from rest ( _v_ = 0) at _t_ = 0:

111

Thus, the velocity of an object on an incline increases linearly with time. The rate of increase depends on the incline’s angle ( _θ_ ) but is independent of the object’s mass.

Both of these examples are simplified. We could derive a general expression for _v_ as a function of _t_ ? What if the object was moving at _t_ = 0? What if there was another force acting in the opposite direction? You will see examples of this in the exercises.

**Example 7.3: Drag forces on a droplet.** We can apply Newton’s second law of motion to a case where we have an object moving through a fluid. As that object moves and displaces the fluid, the object will experience varying drag forces that can reduce the objects velocity. We experience this ourselves as we move faster through the air. Fluid dynamics is a very large area of research in itself, but we can at least use some suggested formulations that capture this drag as a function of velocity and environmental conditions. Figure 7.2 shows streamlines of fluid flow around a sphere as it moves through a fluid. As the difference in speed between the object and fluid increases, so will the nature of the forces that dictate motion. These forces include contributions from shear viscosity, eddy viscosity and stagnation pressure. In Physics, we often use dimensionless variables that give us an idea of when these change and by how much. In fluid dynamics, the Reynolds number (often denoted _Re_ ), captures this change. We do not cover that in our course. For now we can assume that, for a droplet moving through the atmosphere, the drag force on a sphere which is moving through air is approximately equal to

where _r_ is the sphere’s radius, _vrel_ is the velocity it is moving through the air and _ρ_ = 1 _._ 2 kg m<sup>_−_3</sup> is the density of air. How might we balance this force with the force acting on the droplet due to gravity?

**Figure 7.2:** Schematic illustrating forces acting on a a sphere moving through a fluid with varying velocity and thus Reynolds number. Taken from `https://cfdflowengineering.com/ cfd-modeling-of-flow-over-a-cylinder/`

112

Chapter 7. Integration using Newton’s Laws

## Exercises

In some of the following questions, an object resting on an incline, as shown on the right side of Figure 7.1. The object experiences Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center. Assuming the triangle is a hard object, the forces can be resolved into two components: (i) the force dragging the block down the slope (labeled as _F_ 2) and (ii) the force acting perpendicular to the slope known as the normal force (labeled as _F_ 1). If the gravitational force is given by _mg_ (where _m_ is the object’s mass and _g_ is the gravitational constant), what the magnitude of _F_ 1 and _F_ 2 are as follows:

_F_ 1 = _mg_ cos( _θ_ ) _F_ 2 = _mg_ sin( _θ_ )

We can also write Newtons second law using three ordinary differential equations (ODE) as follows:

All are equal but allow you to calculate speed as a function of time OR speed as a function of distance.

**Question 7.1** : An object, mass _m_ , is at rest on a plane, which is inclined at 30<sup>_◦_</sup> to the horizontal. Assuming there is no friction how fast will the object be moving after it has moved down the slope a distance of 10 metres? HINT: Use an ODE that relates both distance and velocity.

**Question 7.2** : An object, mass _m_ , is at rest on a plane, which is inclined at 30<sup>_◦_</sup> to the horizontal. Assuming friction is equal to 0 _._ 1 times the contact force (i.e. the force of gravity perpendicular to the slope) how fast will the object be moving after it has slid down the slope distance of 10 metres? HINT: Alter the total forces acting on the object.

**Question 7.3** : An object, mass _m_ , is at rest on a plane, which is inclined at 30<sup>_◦_</sup> to the horizontal. Assuming friction is equal to 0 _._ 1 times the contact force (i.e. the force of gravity perpendicular to the slope) how fast will the object be moving after it has slid down the slope after 10 seconds? HINT: Alter the ODE to relate velocity and time.

**Question 7.4** : An object, mass _m_ , is on on a plane, which is inclined at 30<sup>_◦_</sup> to the horizontal. Assuming there is no friction and and an initial velocity of 2 _m/s_ , how fast will the object be moving after it has moved down the slope a distance of 10 metres? HINT: Use an ODE that relates both distance and velocity. For this question, as you integrate the appropriate form of Newtons law, think about how to set your limits of integration. You can pair the starting speed and distance with the end speed and distance. Once you integrate with these

113

limits, you re-arrange to access the final distance.

**Question 7.5** : The drag force on a sphere which is moving through air is approximately equal to

where _r_ is the sphere’s radius, _vrel_ is the velocity it is moving through the air and _ρ_ = 1 _._ 2 kg m<sup>_−_3</sup> is the density of air. A sphere, radius 0 _._ 5 m, and mass _m_ = 1 kg, is pushed along a horizontal plane at an initial velocity of _v_ = 10 _m/s_ ; the wind speed is zero. How far does the sphere move before slowing down to 0.01 _m/s_ ?

**Question 7.6** : Derive an equation for the velocity versus distance of an object moving with an initial velocity _v_ 0 and end velocity _v_ 1, starting position _x_ = 0 and experiencing a constant acceleration. Start by using the following form of Newtons law:

noting that you can separate terms _dv_ and _dx_ and then integrate.

**Question 7.7** : Derive an equation for the velocity versus time if an object moving at an initial velocity _v_ 0 is experiencing a constant acceleration. Start by using the following form of Newtons law:

**Question 7.8** : A ball is thrown into the air with an initial velocity of 10 _m/s_ . It’s acceleration due to gravity (ignoring air resistance) is -9.8 _m/s_<sup>2</sup> . How high will the ball reach before falling back to earth?

**Question 7.9** : A ball is thrown into the air with an initial velocity of 10 _m/s_ . It’s acceleration is as before. How long does it take to reach it’s maximum height?

Chapter 7. Integration using Newton’s Laws

114

## Solutions

**Question 7.1** : Assuming that there is no friction acting against the object, the component of force parallel to the plane ( _F_ 2) is the only force acting on the object, which is _mg_ sin(30). As we want to estimate the velocity after it has moved 10 _m_ down the incline, we use ODE (ii) from above:

Cancel the mass ( _m_ ) and use separation of variables to integrate. In terms of the limits, we want to see estimate the velocity after it has rolled 10 _m_ down the incline from rest so we integrate _x_ between 0 and 10, and integrate _v_ from 0 to _v_ :

So the object was moving at 9.9 _m/s_ after it had moved a distance of 10 metres.

**Question 7.2** : This one is very similar to the above question, but now we have some force of friction. The force parallel to the plane ( _F_ 2) is acting on the object and friction of 0.1 times the normal force ( _F_ 1) so the total forces acting on the object is:

Again, as we want to estimate the velocity after it has moved 10 _m_ down the incline, we use ODE (ii) from above:

Cancel the mass ( _m_ ) and use separation of variables to integrate _x_ between 0 and 10, and integrate _v_ from 0 to _v_ (since it was at rest at _x_ = 0):

115

So the object was moving at 9.0 _m/s_ after it had moved a distance of 10 metres.

**Question 7.3** : This one is very similar to the above question, but we need to calculate velocity in terms of time instead of distance. Like the last question, the force parallel to the plane ( _F_ 2) is acting on the object and friction of 0.1 times the normal force ( _F_ 1) so the total forces acting on the object is:

As we want to estimate the velocity 10 seconds after it moved down the incline, we use ODE (i) from above:

Cancel the mass ( _m_ ) and use separation of variables to integrate. In terms of the limits, we want to estimate the velocity 10 seconds after it has moved down the incline from rest so we integrate _t_ between 0 and 10, and integrate _v_ from 0 to _v_ :

So the object was moving at 40.51 _m/s_ after 10 seconds.

**Question 7.4** : This Question 7.is similar to Question 7.1 but instead of starting from rest the object is moving at 2 _m/s_ . As we want to estimate the velocity after it has rolled 10 _m_ down the incline, we use ODE (ii) from above:

Cancel the mass ( _m_ ) and use separation of variables to integrate. In terms of the limits, we want to estimate the velocity of the object which had an initial velocity of 2 _m/s_ after it has rolled 10 _m_ down the incline from rest so we integrate _x_ between 0 and 10, and integrate _v_ from 2 to _v_ :

Chapter 7. Integration using Newton’s Laws

116

So the object with an initial velocity of 2 _m/s_ was travelling at 10.1 _m/s_ after it had rolled down a distance of 10 metres.

**Question 7.5** : Since the sphere is moving horizontally, there is no force acting on the object in the direction of travel. As the wind speed is zero, the total forces on the object is:

We want to estimate the distance the sphere with an initial velocity of 10 _m/s_ travels before slowing down to 0.01 _m/s_ , we use ODE (ii) from above:

Using separation of variables we can integrate this ODE. In terms of the limits, we want to estimate the distance travelled as the sphere goes from 10 _m/s_ and 0.01 _m/s_ , so we integrate _x_ between 0 and _x_ , and integrate _v_ from 10 to 0.01:

So the sphere with an initial velocity of 10 _m/s_ had moved 14.66 _m_ when it reached a velocity of 0.01 _m/s_ .

**Question 7.6** : We can relate an object moving with initial velocity _v_ 0 and end velocity _v_ 1 and a starting position _x_ = 0 through:

Since the object is moving with constant acceleration then we can just use separation of variables and integrate. In terms of the limits we integrate _x_ between 0 and _x_ and integrate

117

_v_ between _v_ 0 and _v_ 1:

**Question 7.7** : We can relate an object moving with initial velocity _v_ 0 at time _t_ = 0 through:

Since the object is moving with constant acceleration then we can just use separation of variables and integrate. In terms of the limits we integrate _t_ between 0 and _t_ and integrate _v_ between _v_ 0 and _v_ 1:

**Question 7.8** : We need to find the highest point a ball thrown into the air reaches. The ball has an initial velocity of 10 _m/s_ and will reach its highest point where it has a velocity of 0 _m/s_ . Since the object has constant acceleration we can use the general formula we developed in Question 7.7 with _v_ 0 = 10, _v_ 1 = 0, and _a_ = _−_ 9 _._ 8 we see that

so the ball reached 5.1 _m_ high.

**Question 7.9** : This is similar to the last question, but we need to find the time it takes to find its maximum height. The ball has an initial velocity of 10 _m/s_ and will reach its highest point where it has a velocity of 0 _m/s_ . Since the object has constant acceleration

118

Chapter 7. Integration using Newton’s Laws

we can use the general formula we developed in Question 7.8 with _v_ 0 = 10, _v_ 1 = 0, and _a_ = _−_ 9 _._ 8 we see that

so the ball reached its maximum height after 1.02 _s_ .

# 8. Integration by Substitution

### 8.1 Overview

In Chapters 6 and 7, we introduced rules that allow us to directly integrate certain basic functions if we can recognize their forms. These can be found in this table:

|Differential equation <sup>_dy_</sup><br>_dx_|Integral,_y_|
|---|---|
|constant|_constant ×x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup><br>_ax_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_ax_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_)+_d_|
|_cos_(_x_)|_sin_(_x_)+_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

There may be a need to rearrange the equation, often by using techniques like separation of variables (e.g., rearranging _N_ and _t_ ) before we can use them, but they are there for us to use. Furthermore, like differentiation for a sum of functions, the **integral of a sum** is equal to the **sum of the integrals** of the individual functions.

120

Chapter 8. Integration by Substitution

In some cases, we cant directly integrate by using these rules, as we are faced with more complicated combinations of functions such as **functions of functions** . For example, what happens if we want to integrate

#### This is where **integration by substitution** comes in.

### 8.2 Integration by substitution

**Integration by substitution** is essentially the reverse process of the **chain rule** in differentiation. Let’s return to the example where we want to evaluate

At first glance, it may appear that this resembles the derivative of some function, allowing us to integrate directly. What if we replace the expression in the brackets with another variable such that we can integrate using the rules we already know? Making a **substitution** can often simplify things and enables us to perform what seems to be an otherwise difficult integration.

Lets use _u_ = 3 _x_ + 2 so the integral becomes

Now, the integral is expressed in terms of _u_ , but we need to address the _dx_ . This is asking us to integrate _u_ with respect to _x_ . Since _dx_ relates to _x_ , we need to rewrite it in terms of _u_ . This step ensures that the integral is entirely in terms of the new variable. When the integral contains a factor like _ax_ + _b_ , substituting _u_ = _ax_ + _b_ often simplifies the problem. Along with the substitution, we must also determine _dx_ in terms of _u_ to complete the process.

Let’s show how **integration by substitution** works in full:

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

121

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Make the substitution in the original integral

7. Integrate as usual:

8. Substitute the original expression back in to get the final expression:

Let’s see some more examples of this.

**Example 8.1** : Lets evaluate the integral

Let’s use _u_ = _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = _x_ + 4 back in gives us:

You can differentiate using the chain rule to verify that this works.

**Example 8.2** : Lets evaluate the integral

122

Chapter 8. Integration by Substitution

Let’s use _u_ = 3 _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 3 _x_ + 4 back in gives us:

You can differentiate using the chain rule to verify that this works.

So we see that we can integrate more complicated functions using substitution. We want to use a substitution so that the integration becomes something we can use our table of standard integrals for. However, this is integration by substitution for **indefinite integrals** . In many cases, we want to find the **area under a curve** so the integral has limits. For example,

therefore we have to perform **definite integration** . This means that we calculate the integral (using integration by substitution) then evaluate the integral but for the new limits calculated under the substitution.

Let’s show how definite **integration by substitution** works in full:

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

123

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Find the new limits of the integral:

7. Make the substitution in the original integral

8. Integrate as usual:

Let’s see some more examples of this.

**Example 8.3** : Lets evaluate the integral

Let’s use _u_ = _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits:

Use these to make the substitution:

124

Chapter 8. Integration by Substitution

Now we can evaluate using the basic laws of integration:

**Example 8.4** : Lets evaluate the integral

Let’s use _u_ = _x_ + 10 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits:

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

125

## Exercises

### Algebraic problems

- **Question 8.1** : Using _integration by substitution_ , find the indefinite integral of the following: 3

- (a) � 4 (5 _x_ + 6) _dx_

- (b) � ( _x −_ 2)3 _dx_

- 4

- (c) � ( _x_ + 5) _dx_

- (d) � (1 _−_ 2 _x_ )7 _dx_

- **Question 8.2** : Using _integration by substitution_ , find the definite integral of the following: 1

- (a) �0<sup>4(5</sup><sup>_x_+6)3</sup><sup>_dx_</sup> 1

- (b) �0<sup>(</sup><sup>_x−_2)3</sup><sup>_dx_</sup>

- 1

- (c) �0<sup>(</sup><sup>_x_+5)4</sup><sup>_dx_</sup>

- 1

- (d) � _−_ 1<sup>(1</sup><sup>_−_2</sup><sup>_x_)7</sup><sup>_dx_</sup>

- **Question 8.3** : Using _integration by substitution_ , find the indefinite integral of the following: (a) � sin (7 _x −_ 3) _dx_

- (b) � exp (5 _x_ + 2) _dx_

- (c) � cos (1 _− x_ ) _dx_

- (d) � 7 _x_ <u>1+5</u><sup>_dx_</sup>

- **Question 8.4** : Using _integration by substitution_ , find the definite integral of the following: (a) �0 _π/_ 2 sin (7 _x −_ 3) _dx_

- 1

- (b) �0<sup>exp(5</sup><sup>_x_+2)</sup><sup>_dx_</sup> _π/_ 4

- (c) � _−π/_ 4<sup>cos(1</sup><sup>_−x_)</sup><sup>_dx_</sup> (d) �01 7 _x_ <u>1+5</u><sup>_dx_</sup>

**Question 8.5** : Using _integration by substitution_ , find the definite integral of the following:

**Question 8.6** : We can see that from the table of basic integration laws that

Use integration by substitution to find a general expression for _y_ when

where _a_ , _b_ and _n_ are constants.

126

Chapter 8. Integration by Substitution

### Real-world problems

**Question 8.7** : The density of air changes with pressure and temperature (because of the _<u>P</u>_ ideal gas law). Density is equal to _ρ_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J kg</sup><sup>_−_1K</sup><sup>_−_1 is the gas constant</sup> for air and gravity is equal to _g_ = 9 _._ 8.. So the differential equation becomes:

We saw that in Chapter 6 that the solution to this problem is:

However, for simplicity, we assumed that temperature was constant which isn’t a very good assumption. Temperature _T_ is actually a function of height in the atmosphere: _T_ ( _z_ ) = _Tsur face −_ 0 _._ 01 _×z_ , where _Tsur face_ is the surface temperature. So the final differential equation to solve can be written:

During a day in the summer, the surface temperature at sea level over Tenerife is 290 K and the surface pressure is 100000 Pa. Clouds are observed to form at a height of 1000 m. What are the pressure and temperature at this height? HINT: Rearrange this ODE and use integration by substitution.

**Question 8.8** : The density of air changes with pressure and temperature (because of the _<u>P</u>_ ideal gas law). Density is equal to _ρ_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J kg</sup><sup>_−_1K</sup><sup>_−_1 is the gas constant</sup> for air and gravity is equal to _g_ = 9 _._ 8.Use integration by substitution to show that the general solution of the hydrostatic equation:

is of the form

where _P_ 0 is the pressure at _z_ = 0.

**Question 8.9** : In the previous Chapter, we saw the drag force on a sphere which is moving through air is approximately equal to

where _r_ is the sphere’s radius, _v_ is the velocity it is moving through the air and _ρ_ = 1 _._ 2 kg m<sup>_−_3</sup> is the density of air. A sphere, radius 0 _._ 5 m, and mass _m_ = 1 kg, is pushed along a

127

horizontal plane at an initial velocity of _v_ = 10 m s<sup>_−_1</sup> . However, this time the wind speed is 10 _m/s_ in the opposite direction of the motion of the sphere. We need to re-write out the above equation slightly to account for the wind speed. If we let _w_ be the wind speed, then the drag force

How far does the sphere move before slowing down to 0.01 m s<sup>_−_1</sup> ? HINT: You will need to use the appropriate version of Newtons second law and then use integrate by substitution to do this.

128

Chapter 8. Integration by Substitution

## Solutions

### Algebraic problems

**Question 8.1** :

- (a) Let’s use _u_ = 5 _x_ + 6 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 5 _x_ + 6 back in gives us:

You can differentiate using the chain rule to verify that this works.

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = _x −_ 2 back in gives us:

You can differentiate using the chain rule to verify that this works.

- (c) Let’s use _u_ = _x_ + 5 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

129

Now we can evaluate using the basic laws of integration:

and substituting _u_ = _x_ + 5 back in gives us:

You can differentiate using the chain rule to verify that this works.

- (d) Let’s use _u_ = 1 _−_ 2 _x_ as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 1 _−_ 2 _x_ back in gives us:

You can differentiate using the chain rule to verify that this works.

#### **Question 8.2** :

- (a) Let’s continue from Question 8.1(a) where we used a substitution of _u_ = 5 _x_ + 6. Find the new limits:

Make the substitution with limits and integrate:

130

Chapter 8. Integration by Substitution

- (b) Let’s continue from Question 8.1(b) where we used a substitution of _u_ = _x −_ 2. Find the new limits:

Make the substitution with limits and integrate:

- (c) Let’s continue from Question 8.1(c) where we used a substitution of _u_ = _x_ + 5. Find the new limits:

Make the substitution with limits and integrate:

- (d) Let’s continue from Question 8.1(d) where we used a substitution of _u_ = 1 _−_ 2 _x_ . Find the new limits:

Make the substitution with limits and integrate:

131

- **Question 8.3** : Using _integration by substitution_ , find the indefinite integral of the following:

   - (a) Let’s use _u_ = 7 _x −_ 3 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 7 _x −_ 3 back in gives us:

You can differentiate using the chain rule to verify that this works.

- (b) Let’s use _u_ = 5 _x_ + 2 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 5 _x_ + 2 back in gives us:

You can differentiate using the chain rule to verify that this works.

- (c) Let’s use _u_ = 1 _− x_ as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

132

Chapter 8. Integration by Substitution

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 1 _− x_ back in gives us:

- (d) Let’s use _u_ = 7 _x_ + 5 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 7 _x_ + 5 back in gives us:

- **Question 8.4** : Using _integration by substitution_ , find the definite integral of the following:

   - (a) Let’s continue from Question 8.3(a) where we used a substitution of _u_ = 7 _x −_ 3. Find the new limits:

Make the substitution with limits and integrate:

- (b) Let’s continue from Question 8.3(b) where we used a substitution of _u_ = 5 _x_ + 2. Find the new limits:

133

Make the substitution with limits and integrate:

- (c) Let’s continue from Question 8.3(c) where we used a substitution of _u_ = 1 _− x_ . Find the new limits:

Make the substitution with limits and integrate:

- (d) Let’s continue from Question 8.3(d) where we used a substitution of _u_ = 7 _x_ + 5. Find the new limits:

Make the substitution with limits and integrate:

**Question 8.5** : Let’s use _u_ = 2 _x_ + 1 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits:

134

Chapter 8. Integration by Substitution

Make the substitution with limits and integrate:

**Question 8.6** : We want to integrate the following:

Let’s use _u_ = _ax_ + _b_ as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = _ax_ + _b_ back in gives us:

You can differentiate using the chain rule to verify that this works.

### Real-world problems

**Question 8.7** : We want to solve the hydrostatic equation to find the pressure _P_ at _z_ = 1000 when the surface pressure is 100 _,_ 000Pa (i.e. _z_ = 0) and _Tsur face_ = 290. We rearrange and integrate pressure, _P_ , between 100000 and _P_ and _z_ between 0 and 1000:

Let’s use _u_ = 290 _−_ 0 _._ 01 _z_ as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

135

Find the new limits

Make the substitution with limits and integrate:

Rearranging this and substituting in _g_ = 9 _._ 8 and _R_ = 287, gives us

and thus the pressure at 1000m is 88708Pa.

**Question 8.8** : We can also demonstrate how to integrate the hydrostatic equation between general limits:

Let’s use _u_ = _Tsur face −_ 0 _._ 01 _z_ as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits

136

Chapter 8. Integration by Substitution

Make the substitution with limits and integrate:

Rearranging this and substituting in _g_ = 9 _._ 8 and _R_ = 287, gives us

the desired expression.

**Question 8.9** : This Question 8.extends Question 8.6 from Chapter 7, however, the sphere has wind speed as well as the speed of the object. This makes the integration a little more difficult. The total forces on the object are

We want to estimate the distance the sphere with an initial velocity of 10 _m/s_ travels before slowing down to 0.01 _m/s_ with a wind speed of _w_ = 10:

Using integration by substitution we can integrate this ODE. In terms of the limits, we want to estimate the distance travelled as the sphere goes from 10 _m/s_ and 0.01 _m/s_ , so we integrate _x_ between 0 and _x_ , and integrate _v_ from 10 to 0.01:

Let’s use _z_ = _v_ + 10 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

137

Find the new limits:

Make the substitution with limits and integrate:

Substituting _m_ = 1, _ρ_ = 1 _._ 2, and _r_ = 0 _._ 5 gives us:

So we see that the total distance travelled has reduced from 14.66 to 0.41m by adding in wind speed, so the wind causes the sphere to slow down much quicker.

# 9. Integration by Parts

### 9.1 Overview

In Chapters 6 and 7„ we introduced rules for directly integrating certain basic functions by recognising their forms. However, techniques like separation of variables are often insufficient when dealing with more complex combinations of functions, such as **functions of functions** and thus we introduced **integration by substitution** in Chapter 8. In this Chapter, we look at we focus on more difficult combinations, particularly **products of functions** . For example, what happens if we want to integrate:

This is where **integration by parts** comes in.

### 9.2 Integration by parts

**Integration by parts** is essentially the reverse process of the **product rule** in differentiation. The product rule states that when we have a product of two functions _u_ ( _x_ ) _v_ ( _x_ ) then we can differentiate this as follows:

Let’s integrate this expression:

140

Chapter 9. Integration by Parts

Simplifying this gives us

and doing a final rearranging gives

This is the formula we need to use to perform integration by parts! It may look counterintuitive, as this would involve splitting the function, integrating one part and differentiating another, but it does indeed work!

To prove that it does, let’s return to the integral

to show how **integration by parts** works in full:

1. Write out the integral in its simplest form.

2. Identify and assign _u_ and differentiate to get<sup>_<u>du</u>_</sup> _dx_<sup>.You should select the term that</sup> simplifies upon differentiation, so lets choose _u_ ( _x_ ) = _x_ here:

3. Identify the other term and assign _dx_<sup>_<u>dv</u>_and integrate to get</sup><sup>_v_.</sup>

4. Substitute these values into the integration by parts formula:

5. Integrate the remaining term:

6. Simplify to get the final expression:

141

#### **Example 9.1** :

#### **Example 9.2** :

So we see that we can integrate products of functions using integration by parts. However, this is integration by substitution for **indefinite integrals** . In many cases, we want to find the **area under a curve** so the integral has limits. For example,

therefore we have to perform **definite integration** . This means that we calculate the integral (using integration by parts) then evaluate the integral but for the new limits calculated under the substitution.

Let’s show how definite **integration by parts** works in full:

1. Write out the integral in its simplest form.

2. Identify and assign _u_ and differentiate to get<sup>_<u>du</u>_</sup> _dx_<sup>.You should select the term that</sup> simplifies upon differentiation.

3. Identify the other term and assign _dx_<sup>_<u>dv</u>_and integrate to get</sup><sup>_v_.</sup>

4. Substitute these values into the integration by parts formula:

5. Integrate the remaining term:

**Example 9.3** :

**Example 9.4** :

142

Chapter 9. Integration by Parts

## Exercises

Algebraic problems Real-world problems

## Solutions

Algebraic problems Real-world problems

<!-- Start of picture text -->
10. Second-Order Ordinary Differential<br>Equations<br><!-- End of picture text -->

### 10.1 Overview

In Chapters 6–8, we explored the process of integration, which is the inverse of differentiation and a powerful tool for calculating the area under curves. This has been really useful in understanding various properties and behaviors of systems, such as those described by Newton’s Laws of Motion. However, our focus so far has been primarily on first-order derivatives (i.e., _dx_<sup>_dy_).In this Chapter, we conclude our study of integration by examining</sup> **second-order ordinary differential equations** .

### 10.2 Second-order Differential Equations

_S_ econd-order ordinary differential equations are ordinary differential equations (ODEs) that involve a _second-order derivative_ . We could devote an entire course looking at solving different types of second-order ODEs, a general form is given by:

Here, _a_ ( _x_ ), _b_ ( _x_ ), _c_ ( _x_ ) and _d_ ( _x_ ) are general functions of the variable _x_ , referred to as coefficients. In fact, we can simplify the above expression by writing _a_ ( _x_ ), _b_ ( _x_ ) and _c_ ( _x_ ) as constant coefficients (which we will only ever look at in this course):

This equation is classified as a **linear second-order ODEs** because the second derivative, _d_<sup>2</sup> _<u>y</u>_<sup>If the value of</sup><sup>_d_(</sup><sup>_x_) = 0 we can also say the equation is</sup> _dx_<sup>2, is raised to the power of 1.</sup> **homogeneous** , whilst if _d_ ( _x_ ) = 0 the equation is calles **non-homogeneous** . In this course

Chapter 10. Second-Order Ordinary Differential Equations

144

we will briefly look at methods for solving **homogeneous, linear, second-order ODEs** which resemble the following expression:

Please note that we can write the exact same expression using alternative ODE notation as per the following equation:

where _a_ , _b_ and _c_ remain the same constants. In every problem so far, we have wanted to arrive at a general analytical solution from integrating a differential equation. How do we deal with a second-order ODE as above?

Fortunately, there is a general form we can use if the equation to be solved has the same form. Notice how it looks like we might be able to use the approach to solving quadratic equations, but how do we find a value for _y_ . Lets just jump to an educated guess and assume the expression for _y_ is going to be:

where _λ_ is a constant with an unknown value. If we differentiate (twice) this expression we can arrive at two expressions:

Lets now substitute these expressions back into our general differential equation as follows:

Because _e_<sup>_λx_</sup> cant be zero, it is safe to divide through to acquire a quadratic in _λ_ :

This is called the **auxiliary** equation or **characteristic** equation. When you encounter a **homogeneous second-order ODE** , you can jump straight to this point and follow the procedure below.

Looks like we have a quadratic equation. If can solve this, we can get to a value of _λ_ which we can use to find a solution to the second-order ODE. Remember that we can solve (or find roots of) quadratic equations using the following formula:

145

When we solve a quadratic expression we will arrive at 2 roots, which we can call _λ_ 1 and _λ_ 2.

Since there are two roots to the auxiliary equation, the general solution to the second-order ODE will be a combination of the two function. If _λ_ 1 and _λ_ 2 are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _−_ 4 _ac <_ 0) in this course. In both general solutions, we have added two new constants _A_ and _B_ as we are combining multiple solutions we need to know how much each will contribute to the final solution. To calculate their values, we need some initial conditions or boundary conditions in _y_ (we’ll see this later).

**Example 9.1** : Imagine we are asked to solve the following equation:

We can see that this is a linear, homogeneous, second-order ODE. Firstly, we write out the auxiliary equation:

Secondly, we need to check what the values for _λ_ 1 and _λ_ 2 are to understand what solution is needed. To do this, by using the **auxiliary** equation we know we have a quadratic as follows. Find the roots ( _λ_ 1 and _λ_ 2) of this equation:

so we have roots _λ_ 1 = 1 and _λ_ 2 = 5. Since they are real and distinct then the solution will have form

Chapter 10. Second-Order Ordinary Differential Equations

146

Thirdly, we plug the values of _λ_ 1 and _λ_ 2

and this is our general solution to the problem.

The next question is how to calculate the values for constants _A_ and _B_ ? We need more information to constrain these values such as _y_ = 0 and _y_ = 1 when _x_ = 0. These are called **initial conditions** , and they tell us the value of the solution and/or its derivatives at a specific point, allowing for a unique solution to the differential equation. For example, for<sup>_dyf_(</sup><sup>_x_), an initial condition might be</sup><sup>_y_=</sup><sup>_y_0 at</sup><sup>_x_=</sup><sup>_x_0.You will have seen examples</sup> _dx_<sup>=</sup> when solving the radioactive decay equation, hydrostatic equation and Newton’s Laws of Motion. This will lead us to solving simultaneous equations. Do you recall how you solve simultaneous equations? If we want to calculate two unknowns we need to formulate two expressions that provide us with an ability to re-arrange and isolate.

**Example 9.2** : Let’s return to the previous example:

We wrote out the auxiliary equation and found the roots to arrive at the general solution our general solution to the problem:

Suppose that we are told that _y_ = 0 and _y_<sup>_′_</sup> = 1 when _x_ = 0 then we use this information to find _A_ and _B_ . Write out _y_ and _y_<sup>_′_</sup> :

Plug in the initial conditions in to _y_ and _y_<sup>_′_</sup> to get:

This leaves us with a system of simultaneous equations which we can solve. Take Equation 10.1 from Equation 10.2 gives us:

Substitute _B_ =<sup><u>1</u></sup> 4<sup>into Equation 10.1 gives us:</sup>

Then the full general solution is given by:

147

### 10.3 Applied boundary value problems and steady-state

In the last section, we dived into finding general solutions of second-order ODEs and captured some definitions and an approach to solve special cases. In this section, we can ground some of this is reality and take a look look at how these types of equations are used in real-world physical theories, therefore, then when we solve second-order ODEs, it tells us about the state of the system we are interested in. We also get back to the process of integration rather than working through a known solution as the previous section.

Examples of second-order ordinary differential equations are:

- <sup>**Kinematics**:Acceleration (</sup><sup>_a_) as the rate of change of the rate of change of location</sup> ( _x_ ) in time ( _t_ ),<sup>_<u>d</u>_</sup> _dt_<sup>22</sup><sup>_<u>x</u>_.</sup>

- <sup>**Forces and motion**:Newton’s second law of motion:</sup><sup>_F_=</sup><sup>_ma_.</sup>

- <sup>**Fick’s law**:Steady-state mass diffusion:</sup><sup>_<u>d</u>_</sup> _dt_<sup>2</sup><sup>_<u>C</u>_2= 0.</sup>

- <sup>**Fourier’s law**:Steady-state heat transfer:</sup><sup>_<u>d</u>_</sup> _dt_<sup>2</sup><sup>_<u>T</u>_2= 0.</sup>

These equations look different to the previous section. In some ways, they look easier because they offer us a starting point to begin the process of integration. Indeed, to solve second-order ODEs as we have here, we often have to integrate the equation twice. Firstly to get the first gradient and secondly to get the solution. Let’s look at some examples.

**Example 9.3** : Suppose we want to use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_◦_</sup> , starting with velocity _v_ = 0. We will not consider air resistance or friction. Remember that (see Chapter 7 Example 2) if the gravitational force is given by _mg_ (where _m_ is the object’s mass and _g_ is the gravitational constant) then the force dragging the block down the slope ( _F_ 2) and the normal force ( _F_ 1) can be written as:

Furthermore, remember that when using Newton’s second law of motion, we need to determine the net forces that pull or push a body along a surface. Why are second-order ODEs relevant here? Remember, we can write Newtons second law of motion as follows:

Each expression is equivalent to the other. If we integrate the second equation ( _F_ = _m_<sup>_<u>dv</u>_</sup> _dt_<sup>),</sup> we can arrive at an expression of velocity ( _v_ ) as a function of time ( _t_ ). However, we have been asked to derive an expression of distance ( _x_ ) as a function of time. This means we

148 Chapter 10. Second-Order Ordinary Differential Equations

would need to integrate our expression for _v_ again, given that _v_ =<sup>_<u>dx</u>_</sup> _dt_<sup>.To solve this problem</sup> we have to integrate twice. Lets see this in action. As there is no friction acting on object the total forces on the object are _F_ = _mg_ sin (30<sup>_◦_</sup> ). We integrate to get the velocity ( _v_ ) of this object ( _v_ from 0 to _v_ and _t_ from 0 to _t_ ):

We integrate again to get the distance travelled ( _x_ ) of this object ( _x_ from 0 to _x_ and _t_ from 0 to _t_ ):

So the velocity increases linearly and the distance quadratically in this problem.

The ODEs that have been covered so far are called **initial value problems** . This is where we specify some initial values (i.e. when _x_ = 0, _v_ = 0, _t_ = 0), and we solve the ODE to find something about our process in the future or a certain distance away. Other kinds of ODEs are called **boundary value problems** , where upper and lower boundary conditions are specified (i.e, when _x_ = _x_ 0 and _x_ = _x_ 1). This gives us more information this means that we have to make the solution meet at both points. The two we will cover are Fick’s and Fourier’s laws, which are laws of mass diffusion and heat conduction.

**Example 9.4: Fourier’s Law.** Fourier stated that the flux of heat through a substance is proportional to the negative gradient of temperature in the substance (i.e. heat flows from hot to cold). We can express this, known as Fouriers law, as a differential equation:

where _T_ is the temperature and _x_ the distance variable.

**Example 9.5: Fick’s Law.** Fick also found that the law that governs transport of mass by _Brownian motion_ (i.e. random thermal motion) moves from high concentrations to low concentrations. We can express this, known as Fick’s law, as a differential equation:

where _J_ is the mass flux, _C_ is the concentration of mass (e.g. mass of pollutant / gas or particulate) and _D_ is a diffusion coefficient which depends on the properties of the substance that is diffusing.

149

For both of these equations, we assume steady state conditions. Remember from Chapter 5, a system is in steady-state when the key variables that describe the system’s behavior do not change over time (i.e. _f_ ( _x_ ) = _c_ where _c_ is constant). See Figure 10.1, consider the situation where water is poured into a container which has an outlet part on the side of the container. At first when the water level is below the outlet, the water level in the container rises with time. However, when the water level reaches a certain height, the amount of water entering the tank and the amount of discharged water are balanced and the water level remains constant. The system has reached a steady state. If the system is in steady state, we can differentiate again to get a derivative equal to zero (i.e.<sup>_d_</sup> _dx_<sup>_<u>f</u>_= 0.In Fick’s and</sup> Fourier’s Law, we specify that the rate of change remains constant, either over space or time, we can rewrite them as:

These are **second-order ODEs** . Similar to Exercise 3, we will need to integrate them twice to arrive at expressions for concentrations and temperatures as a function of distance, however as you will see in the exercises, we will specify boundary conditions rather than intial conditions.

**Figure 10.1:** Diagram showing a system in (a) transient state and (b) steady state.

150

Chapter 10. Second-Order Ordinary Differential Equations

## Exercises

### Algebraic problems

For this section we are concerned with **homogeneous, linear, second-order ODEs** which resemble the following expression:

To find a general solution for _y_ we first write out the **auxiliary** equation

and solve it to find the roots. If the roots are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _−_ 4 _ac <_ 0) in this course.

**Question 9.1** : For the following second-order ordinary differential equations, write out the auxiliary questions, find the roots and express the general solution:

- (a)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>_+6</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>−_16</sup><sup>_y_= 0</sup> (b) 8<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_2</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>−y_= 0</sup> (c) 4<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_24</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>_+27</sup><sup>_y_= 0</sup> (e)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_4</sup><sup>_y_= 0</sup>

**Question 9.2** : Return to the general solutions found in Question 9.1 and use the following

- initial or boundary conditions to find the constants _A_ and _B_ and then state the full solution. (a)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>_+6</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>−_16</sup><sup>_y_= 0 using</sup><sup>_y_= 2 and</sup> _dx_<sup>_dy_=</sup><sup>_−_6 when</sup><sup>_x_= 0.</sup> (b) 8<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_2</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>−y_= 0 using</sup><sup>_y_= 10 and</sup> _dx_<sup>_dy_= 2 when</sup><sup>_x_= 0.</sup> (c) 4<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_24</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>_+27</sup><sup>_y_= 0 using</sup><sup>_y_= 0 and</sup> _dx_<sup>_dy_= 12 when</sup><sup>_x_= 0.</sup> (d)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>−_4</sup><sup>_y_= 0 using</sup><sup>_y_=</sup><sup>_−_4 and</sup> _dx_<sup>_dy_= 0 when</sup><sup>_x_= 0.</sup>

**Question 9.3** : Solve the following differential equation given the associated initial conditions associated with both the function value for _y_ and gradient<sup>_dy_.</sup>

151

where

**Question 9.4** : For the following second-order ordinary differential equations, write out the auxiliary questions, find the roots and express the general solution:

### Real-world problems

**Question 9.5: Newtons laws of motion (as 2nd Order ODEs)** : We can write Newtons second law of motion as follows:

- (a) Use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_◦_</sup> , starting with velocity _v_ = 0. Do not consider air resistance or friction.

- (b) Use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_◦_</sup> , starting with velocity, _v_ = 0. Do not consider air resistance but consider the frictional force to be equal to _µ × N_ , where _N_ is the magnitude of the contact force and _µ_ = 0 _._ 1. Solve this for initial velocity = 0 to get the position _x_ vs time.

**Question 9.6: Fick’s Law of diffusion (as 2nd Order ODEs)** : An industrial incinerator produces a steady output of particulate matter having a concentration of _C_ 0 = 1 _._ 0 mg m<sup>_−_3</sup> of air at the chimney. 1 km away from the incinerator plant the concentration is _C_ 1 _km_ = 0 _._ 1 mg m<sup>_−_3</sup> . Some houses are a distance of 500 m away from the plant. Using Fick’s law of 1-d diffusion,<sup>_<u>d</u>_</sup> _dx_<sup>2</sup><sup>_<u>C</u>_2= 0, what is the concentration of pollutant where the houses are?Note</sup> that you have been told the limit for particulate matter is 0 _._ 5 mg m<sup>_−_3</sup> . Is the concentration at the location of the houses above 0 _._ 5 mg m<sup>_−_3</sup> ?

**Question 9.7: Fouriers law of heat transfer (as 2nd Order ODEs)** : 3 km below the surface there is a hot granite bed, with a steady-state temperature of 250<sup>_◦_</sup> C. The temperature just below the surface the temperature stays relatively constant at 10<sup>_◦_</sup> C, use the steady-state Fouriers law in 1-d,<sup>_<u>d</u>_</sup> _dx_<sup>2</sup><sup>_<u>T</u>_2= 0 to derive an equation that describes the temperature profile</sup> between the surface and the hot granite.

152 Chapter 10. Second-Order Ordinary Differential Equations

**Question 9.8: Newtons laws of motion (as 2nd Order ODEs)** : Derive an equation for the displacement with time if an object moving at an initial velocity is experiencing a constant acceleration. In other words, we know that we can write Newtons second law as a second order ODE):

where _a_ is now a constant. Proceed with integrating this expression by assuming that the starting position is _x_ = 0 and initial velocity is _v_ 0 m/s.

153

## Solutions

### Algebraic problems

#### **Question 9.1** :

- (b) Write out the auxiliary equations:

Find the roots of the equation:

so the roots are _λ_ 1 =<sup><u>1</u></sup> 2<sup>and</sup><sup>_λ_2 =</sup><sup>_−_</sup><sup><u>1</u></sup> 4<sup>.So as the roots are real and distinct the general</sup> solution is:

_<u>t</u> y_ ( _t_ ) = _Ae_ 2 + _Be_<sup>_−_</sup> 4<sup>_<u>t</u>_</sup>

- (c) Write out the auxiliary equations:

Find the roots of the equation:

so the roots are _λ_ 1 = 2<sup><u>9</u>and</sup><sup>_λ_2 =</sup><sup><u>3</u></sup> 2<sup>.So as the roots are real and distinct the general</sup> solution is:

- (d) Write out the auxiliary equations:

Find the roots of the equation:

so the roots are _λ_ 1 = _−_ 2 and _λ_ 2 = 2. So as the roots are real and distinct the general solution is:

**Question 9.2** :

Chapter 10. Second-Order Ordinary Differential Equations

154

- (a) From Question 9.1(a), the general solution is:

We know that _y_ = 2 and _dx_<sup>_dy_=</sup><sup>_−_6 when</sup><sup>_x_= 0.Write out</sup><sup>_y_and</sup> _dx_<sup>_dy_:</sup>

Plug in the initial conditions into _y_ and _dx_<sup>_dy_:</sup>

This leaves a system of simultaneous equations which we can solve:

Then the full general solution is given by:

- (b) From Question 9.1(a), the general solution is:

Plug in the initial conditions into _y_ and _dx_<sup>_dy_:</sup>

This leaves a system of simultaneous equations which we can solve:

Then the full general solution is given by:

155

#### (c) From Question 9.1(a), the general solution is:

We know that _y_ = 0 and _dx_<sup>_dy_= 12 when</sup><sup>_x_= 0.Write out</sup><sup>_y_and</sup> _dx_<sup>_dy_:</sup>

Plug in the initial conditions into _y_ and _dx_<sup>_dy_:</sup>

This leaves a system of simultaneous equations which we can solve:

Then the full general solution is given by:

- (d) From Question 9.1(a), the general solution is:

Plug in the initial conditions into _y_ and _dx_<sup>_dy_:</sup>

This leaves a system of simultaneous equations which we can solve:

Then the full general solution is given by:

Chapter 10. Second-Order Ordinary Differential Equations

156

**Question 9.3** : Write out the auxiliary equations:

Find the roots of the equation:

so the roots are _λ_ 1 = 3<sup><u>4</u>and</sup><sup>_λ_2 =</sup><sup>_−_2.So as the roots are real and equal the general solution</sup> is:

We know that _y_ = _−_ 6 and _dx_<sup>_dy_=</sup><sup>_−_18 when</sup><sup>_x_= 0.Write out</sup><sup>_y_and</sup> _dx_<sup>_dy_:</sup>

Plug in the initial conditions into _y_ and _dx_<sup>_dy_:</sup>

Substitute to solve:

Then the full general solution is given by:

**Question 9.4** : Write out the auxiliary equations:

Find the roots of the equation:

so the roots are _λ_ 1 = _λ_ 2 = 2. So as the roots are real and equal the general solution is:

157

### Real-world problems

**Question 9.5: Newtons laws of motion (as 2nd Order ODEs)** :

- (a) The total forces on the object are _F_ = _mg_ sin (30<sup>_◦_</sup> ). We integrate to get the velocity ( _v_ ) of this object ( _v_ from 0 to _v_ and _t_ from 0 to _t_ ):

We integrate again to get the distance travelled ( _x_ ) of this object ( _x_ from 0 to _x_ and _t_ from 0 to _t_ ):

So the velocity increases linearly and the distance quadratically in this problem.

- (b) The total forces on the object are _F_ = _mg_ sin(30<sup>_◦_</sup> ) _− mg_ cos(30<sup>_◦_</sup> ). We integrate to get the velocity ( _v_ ) of this object ( _v_ from 0 to _v_ and _t_ from 0 to _t_ ):

We integrate again to get the distance travelled ( _x_ ) of this object ( _x_ from 0 to _x_ and _t_ from 0 to _t_ ):

Again, the velocity increases linearly and the distance quadratically in this problem.

#### **Question 9.6: Fick’s Law of diffusion (as 2nd Order ODEs)** : We need to solve:

Differentiating once gives us:

158

Chapter 10. Second-Order Ordinary Differential Equations

Differentiating twice gives us:

In general, the boundary conditions that _C_ (0) = _C_ 0 and _C_ (1000) = _C_ 1 _km_ means that

Therefore the solution to Fick’s law is:

Using _C_ 0 = 1 and _C_ 1 _km_ = 0 _._ 1, houses 500m away have concentration

So the concentration is 0 _._ 55mg/m<sup>_−_3</sup> , which is above the 0 _._ 5 limit.

**Question 9.7: Fouriers law of heat transfer (as 2nd Order ODEs)** : This is similar to Question 9.6. We need to solve:

Differentiating once gives us:

Differentiating twice gives us:

In general, the boundary conditions that _T_ (0) = _T_ 0 and _T_ (3000) = _T_ 3 _km_ means that

Therefore the solution to Fick’s law is:

Plugging in _T_ 0 = 10 and _T_ 3 _km_ = 250 gives

159

**Question 9.8: Newtons laws of motion (as 2nd Order ODEs)** : Integrate once

When _t_ = 0 we know that _v_ = _v_ 0 so then we see that _B_ = _v_ 0 then

Integrate a second time:

When _t_ = 0 we know that _x_ = 0 so then we see that _C_ = 0 then

# 11. Vectors and Partial Differentiation

### 11.1 Overview

Now that we have concluded the topics Differentiation (Chapters 1–5) and Integration (Chapters 6–10) , we should note that these topics have been centred around a function in one variable or dimension (i.e. _y_ = _f_ ( _x_ )). We differentiated or integrated in terms of that one variable:

In many cases, we may need to work in more than one dimension (e.g. in space) such as _f_ ( _x, y_ ) = _x_<sup>2</sup> + _y_<sup>2</sup> , therefore, in this Chapter we look at **scalar fields** , **vectors** and **partial differentiation** .

### 11.2 Scalar fields

In mathematics and physics, a **scalar field** is a function of two or more variables (i.e. _f_ ( _x, y_ )) that assigns a single scalar value (a number) to every point in a space. Scalar fields represent a single value at different positions. They have magnitude but no direction and can be represented with a colour plot (e.g. temperature over a city, or for example wind speed – but not direction). In essence, they are functions in higher dimensions than we have seen thus far (i.e. _f_ ( _x_ )). Take a look at the 2-D scalar fields displayed in Figure 11.1.

These figures show three scalar fields: _f_ ( _x, y_ ) = _x_<sup>2</sup> , _f_ ( _x, y_ ) = _xy_ , and _f_ ( _x, y_ ) =<sup><u>1</u></sup> 2 � _x_<sup>2</sup> + _y_<sup>2�</sup> . Which ones are which? Try to explain why. In the plots white represents high values and black low values. Where are the maximum and minimum values for each scalar field?

162

Chapter 11. Vectors and Partial Differentiation

**Figure 11.1:** Three scalar fields: _f_ ( _x, y_ ) = _x_<sup>2</sup> , _f_ ( _x, y_ ) = _xy_ , and _f_ ( _x, y_ ) = 2<sup><u>1</u></sup> � _x_<sup>2</sup> + _y_<sup>2�</sup>

### 11.3 Vectors

Now take a look at the plots in Figure 11.2 which represent **vector fields** . Can you see the similarity? Imagine these are wind fields, as you might see on a weather forecast. In the vector fields we can determine there is a direction, or flow. The magnitude of that direction can either be taken from the length of the arrow, or by referring to the scalar fields from the plots above. Which vector fields can be aligned to the scalar fields in Figure 11.1?

The left and middle vector field could both relate to the left hand scalar field. So you see here, these vector fields given opposite flow but have the same magnitude as a function of distance. SO how do we represent a vector field algebraically?

<!-- Start of picture text -->
10<br>10 10<br>5<br>5 5<br>0 0 0<br>−5 −5<br>−5<br>−10 −10<br>−10<br>−10 −5 0 5 10 −10 −5 0 5 10 −10 −5 0 5 10<br>x x x<br>y y y<br><!-- End of picture text -->

**Figure 11.2:** Vector fields, from which we can determine there is a direction, or flow. The magnitude of that direction can either be taken from the length of the arrow, or by referring to the scalar fields from the plots in Figure 11.1.

#### Vector notation

**Vectors** have **magnitude** and **direction** . We can use a simply graph to illustrate the concept. Consider Figure 11.3. Each line in this figure represents the same vector, but a different starting position. Wherever the starting position is, each vector moves 2 units to the left and 5 units up. If we write this procedure in vector form we write:

163

**Figure 11.3:** Vector fields. In this figure we use the same vector to draw a line but vary the starting position in each case.

Notice the distinction in style between the variable and the brackets. Specifically, the notation _⟨−_ 2 _,_ 5 _⟩_ is fundamentally different from writing ( _−_ 2 _,_ 5). The former conveys information about the magnitude and direction of a vector, while the latter represents a point in space defined by coordinates. A vector can be written more generally as:

where the constants _a_ 1 and _a_ 2 describe shifts along the horizontal and vertical axes, respectively, based on the assumed coordinate system.

Now, imagine this vector represents movement from point _A_ to _B_ . In this case, we write the vector as _AB_ . In two-dimensional space, if point _A_ has coordinates _A_ = ( _x, y_ ) and point _B_ has coordinates _B_ = ( _x_ + _a_ 1 _, y_ + _a_ 2), the vector _AB_ describes the displacement. Note the difference in notation between vectors and coordinates. The same principle extends to three-dimensional systems. If the vector becomes:

then the coordinates of points _A_ and _B_ can be written as _A_ = ( _x, y, z_ ) and _B_ = ( _x_ + _a_ 1 _, y_ + _a_ 2 _, z_ + _a_ 3), respectively, representing the vector _AB_ .

More generally, the direction indicated by the arrow over the vector, as in _AB_ , specifies movement from point _A_ to _B_ along a straight line. If the coordinates of _A_ and _B_ are given as _A_ = ( _a_ 1 _, a_ 2 _, a_ 3) and _B_ = ( _b_ 1 _, b_ 2 _, b_ 3), the vector _v_ describing _AB_ is:

Chapter 11. Vectors and Partial Differentiation

164

Conversely, if our vector now starts at _B_ and moves to _A_ , thus _BA_ , then we can write:

Using a **start minus end** approach. You can practice these operations in the exercises.

#### Unit vectors and vector magnitude

In our set of problems we consider vectors in Cartesian form, that is broken down into components along _x_ , _y_ and _z_ of a Cartesian domain. The component along _x_ is component _i_ ˆ, along _y_ is component _j_ ˆ and along _z_ is component _k_ ˆ. _i_ ˆ, _j_ ˆ and _k_ ˆ are all called unit vectors and have length equal to 1.For example, take a look at the following vector:

This tells us that, whatever process is described using this vector, for every movement 4 units along the x axis there is 3 units of movement along the y axis. In our example, _i_<sup>ˆ</sup> and _j_ ˆ represent what we call a unit vector so has a magnitude of 1. Note that this is equivalent to writing

from above.

The size of a vector (or its magnitude) can be calculated by taking the square root of all of the square its components (i.e. Pythagoras’ theorem). So if _a_ ¯ = _a_ 1 _i_<sup>ˆ</sup> + _a_ 2 _j_<sup>ˆ</sup> + _a_ 3 _k_<sup>ˆ</sup> , then the magnitude, _|a_ ¯ _|_ :

A vector that has length that points in the same direction as a general vector _a_ ¯ is called the unit vector of _a_ ¯. It is calculated by dividing all components of _a_ ¯ by the magnitude of _a_ ¯.

#### Vector arithmetic

Vectors can be added or subtracted (add or subtract by component) or multiplied by a scalar (constant). For example, Figure 11.4 demonstrates adding two vectors _a_ and _b_ to create a new vector. When adding vectors, you simply add the components for _i_<sup>ˆ</sup> and _j_<sup>ˆ</sup> .

Given the vectors _a_ = _⟨a_ 1 _, a_ 2 _, a_ 3 _⟩_ and _b_ = _⟨b_ 1 _, b_ 2 _, b_ 3 _⟩_ the addition of the two vectors is given by the following formula:

Subtraction is similar. Given the vectors _a_ = _⟨a_ 1 _, a_ 2 _, a_ 3 _⟩_ and _b_ = _⟨b_ 1 _, b_ 2 _, b_ 3 _⟩_ the subtraction of the two vectors is given by the following formula:

165

**Figure 11.4**

This can be harder to visualise. In Figure 11.5 you can see that if we consider we are adding the negative version of vector _b_ to _a_ (thus _a_ +( _−b_ ) since we are performing an extraction), then you can visualise the net direction of travel:

**Figure 11.5:** Visualisation of vector addition. Credit to `https://tutorial.math.lamar.edu/ Classes/CalcII/VectorArithmetic.aspx`

We can finish on the ability to multiple vectors by a constant. Imagine a situation where a unit vector described the direction of travel every second across a two dimensional grid. If we knew the object was travelling at 15 metes per second, how might we find the absolute position over 1 second? We would multiple the unit vector by the speed. Combined, this new vector represents the velocity of the object. Take a look at Figure 11.6. We have 3

Chapter 11. Vectors and Partial Differentiation

166

vectors that have been derived from the vector _a_ = _⟨_ 2 _,_ 4 _⟩_

**Figure 11.6:** Visualisation of vector and scalar multiplication. Credit to `https://tutorial. math.lamar.edu/Classes/CalcII/VectorArithmetic.aspx`

These lines can be written as the following scalar multiplications:

Noting that when we multiply our original vector by a negative number, we simply reverse the direction of travel.

### 11.4 Partial Differentiation

For the vast majority of this course, we have dealt with differentiation of functions in one dimension, or of one variable (i.e. _y_ = _f_ ( _x_ )). We now think about differentiation of functions of two (or more) variables (i.e. scalar field), _z_ = _f_ ( _x, y_ ), which now depend on _x_ and _y_ .

For a one dimensional curve the gradient _dx_<sup>_dy_is fairly straight forward.When there are more</sup> than one dimension we have to use something else to denote the gradient. The standard that is used is called ‘grad’, which is defined for a scalar field and can be written _grad_ ( _f_ ) or also written ∇ _f_ . We note that ∇ _f_ (where _f_ = _f_ ( _x, y, z_ ) is a scalar field) is actually a vector. In Cartesian coordinates it is:

So the gradient has magnitude and direction. To describe the movement of mass, for example, this is important information. Notice the change in the derivative symbol. Specifically, let us highlight the gradient along the x axis:

Up to this point in our course, we have been using the expression:

_d f dx_

167

The change is important. The new expression is called a _partial differential equation_ . When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant. We are only interested in information along the axis given by the variable in the denominator. We can get a feel for this through the exercises and solutions provided in the later stages of today’s material.

Even when we do not use vector notation, the partial derivatives of a function can be derived. Take the following example:

where we have defined a function that varies with respect to both _x_ and _y_ . We have been asked to find the rate of change of the function at a set of coordinates given by ( _a, b_ ). Conceptually we will need to hold _y_ constant and vary _x_ to determine the gradient along the _x_ axis a vice versa. Indeed, if we were using the method of finite difference, we could use the following assumption:

Of course, we don’t need to use finite difference in this instance since we can apply one of our rules of differentiation.

**Example 10.1** : Let’s find the partial derviatives of the following function:

If we take _y_ as constant then we can derive the following expression for the partial derivative of _f_ with respect to _x_ :

Note that the second term disappears here as it has no _x_ within it. For the partial derivative of _f_ with respect to _y_ , we arrive at the following:

Putting this into vector form gives us:

168

Chapter 11. Vectors and Partial Differentiation

or in the form:

We can use this to calculate the magnitude of the gradient at any given point.

We could go even further and take second partial derivatives of _f_ to obtain get ∇<sup>2</sup> _f_ which would mean partial differentiating with respect to _x_ and _y_ :

as we are differentiating twice with respect to all combinations of the variables, ∇<sup>2</sup> _f_ becomes a matrix which has amazing properties in mathematics and physics, but this is outside the remit of this course!

Furthermore, integrating partial differential equations analytically can only be done for simple cases and requires knowledge of Fourier methods, which are outside of the remit of this course. Nearly all modern weather forecast models use approximate methods to find solutions of **partial differential equations** .

169

## Exercises

**Question 10.1** : Find the magnitude of the following vectors:

(a) _a_ ¯ = 4 _i_<sup>ˆ</sup> + 3 _j_<sup>ˆ</sup>

- (b) _b_<sup>¯</sup> = 4 _i_<sup>ˆ</sup> _−_ 3 _j_<sup>ˆ</sup>

- (c) _c_ ¯ = 3 _i_<sup>ˆ</sup> + 4 _j_<sup>ˆ</sup> + 5 _k_<sup>ˆ</sup>

**Question 10.2** : What is the unit vector that points in the same direction as the vector 3 _i_<sup>ˆ</sup> + 4 _j_<sup>ˆ</sup> + 5 _k_<sup>ˆ</sup> ? A unit vector has a magnitude [length] of 1. Therefore you need to calculate the magnitude of this vector and then divide the vector by this value.

**Question 10.3** : Provide the vector of each of the following:

- (a) The vector that represents a line from _a_ = (2 _, −_ 7 _,_ 0) to _b_ = (1 _, −_ 3 _, −_ 5)

(b) The vector that represents a line from _a_ = (1 _, −_ 3 _, −_ 5) to _b_ = (2 _, −_ 7 _,_ 0)

**Question 10.4** : Determine the magnitude of the following vectors:

(a) _a_ = _⟨_ 3 _, −_ 5 _,_ 10 _⟩_ <u>1</u> (b) _p_ = � _~~√~~_ 5<sup>_,−_</sup> _~~√~~_<sup><u>2</u></sup> 5 �

**Question 10.5** : At time _t_ = 0 two cars are at the origin of a set of x-y coordinates (i.e. 0 = (0 _,_ 0)). Starting at _t_ = 0, car A travels along the x-axis at 30 mph. At the same time car B travels in the direction 3 _i_<sup>ˆ</sup> + 4 _j_<sup>ˆ</sup> with a speed of 60 mph. After 3 hours, what is the distance between the two cars in miles? This requires some thought which may be helped by drawing a diagram.

**Question 10.6** : Calculate the gradient, _grad_ of the following scalar fields:

- (a) _f_ ( _x, y_ ) = _x_<sup>2</sup> sin (5 _y_ )

- (b) _f_ ( _x, y, z_ ) = _z_ exp ( _−xy_ )

(c) _f_ ( _x, y_ ) = 1 _×_ 10<sup>_−_3</sup> ( _x −_ 400)<sup>2</sup> + 1 _×_ 10<sup>_−_3</sup> _y_<sup>2</sup>

**Question 10.7** : For the surface / scalar field: _f_ ( _x, y_ ) = 1 _×_ 10<sup>_−_3</sup> ( _x −_ 400)<sup>2</sup> + 1 _×_ 10<sup>_−_3</sup> _y_<sup>2</sup> , calculate the magnitude of the gradient vector for all _x_ and _y_ . What is the magnitude of the gradient vector at ( _x, y_ ) = (800 _,_ 400)? For this problem you will need to calculate the partial derivatives with respect to _x_ and _y_ and then create a vector, before arriving at an expression for the magnitude of that vector.

**Question 10.8** : Find all of the first order partial derivatives for the following functions. This means we are asking you to to find all of the partial derivatives with respect to each

170

Chapter 11. Vectors and Partial Differentiation

variable.

- (a) _f_ ( _x, y_ ) = _x_<sup>4</sup> + 6<sup>_~~√~~_</sup> _<u>y</u> −_ 10

- <u>4</u>

- (b) _f_ ( _x, y_ ) = _cos_ � _x_ � _e_<sup>_x_2</sup><sup>_y−_5</sup><sup>_y_3</sup>

<u>9</u> _<u>u</u>_ (c) _z_ = _u_<sup>2</sup> +5 _v_

**Question 10.9** : An equation describing a bowl shaped hill is _f_ ( _x, y_ ) = 100exp � _−_ 1 _×_ 10<sup>_−_5 �</sup> _x_<sup>2</sup> + _y_<sup>2��</sup> . You decide to walk along the line _y_ = 0. What is the gradient<sup>_∂_</sup><sup>_<u>f</u>_</sup> _∂_<sup><u>(</u></sup><sup>_x_</sup> _x_<sup>_<u>,y</u>_</sup><sup><u>)</u></sup> ?

171

## Solutions

**Question 10.1** :

**Question 10.2** : For a vector to be a unit vector, we need _||v_ ¯ _||_ = 1 so we need to normalise the _v_ ¯ = _~~√~~_ 3<sup>2</sup> + 4<sup>2</sup> + 5<sup>2</sup> which is _||v_ ¯ _||_ = _√_ 50. Therefore the unit vector is

**Question 10.3** : Provide the vector of each of the following:

- (a) To construct this vector we subtract coordinates of the starting point from the ending point.

- (b) To construct this vector we subtract coordinates of the starting point from the ending point.

**Question 10.4** :

#### **Question 10.5** :

- <sup>Car A will have moved 30</sup><sup>_×_3 = 90 miles along the x-axis.</sup>

- <sup>Car B will have moved 60</sup><sup>_×_3 = 180 miles along the direction of 3ˆ</sup><sup>_i_+4 ˆ</sup><sup>_j_) which has</sup> magnitude 5.

- <sup>So it will have moved to 180</sup><sup>_×_</sup><sup><u>3</u></sup>

   - <sup><u>3</u></sup> 5<sup>_i_ˆ+180</sup><sup>_×_</sup><sup><u>4</u></sup> 5<sup>_j_ˆ.</sup>

- <sup>To find the distance between the two subtract one vector from the other, i.e. 90ˆ</sup><sup>_i−_</sup> 108 _i_<sup>ˆ</sup> _−_ 144 _j_<sup>ˆ</sup> .

- <sup>The magnitude of this vector is</sup>

- _~~√~~_ 18<sup>2</sup> + 144<sup>2</sup> = 145 _._ 1 miles.

#### **Question 10.6** :

- (a) Take partial derivatives of _f_ ( _x, y_ ) = _x_<sup>2</sup> sin (5 _y_ ) (remember to treat the other variables as constant):

172

Chapter 11. Vectors and Partial Differentiation

Then the gradient vector (∇ _f_ ) can be constructed as follows:

- (b) Take partial derivatives of _f_ ( _x, y, z_ ) = _z_ exp ( _−xy_ ) (remember to treat the other variables as constant):

Then the gradient vector (∇ _f_ ) can be constructed as follows:

- (c) Take partial derivatives of _f_ ( _x, y_ ) = 1 _×_ 10<sup>_−_3</sup> ( _x −_ 400)<sup>2</sup> + 1 _×_ 10<sup>_−_3</sup> _y_<sup>2</sup> (remember to treat the other variables as constant):

Then the gradient vector (∇ _f_ ) can be constructed as follows:

**Question 10.7** : Take partial derivatives of _f_ ( _x, y_ ) = 1 _×_ 10<sup>_−_3</sup> ( _x −_ 400)<sup>2</sup> + 1 _×_ 10<sup>_−_3</sup> _y_<sup>2</sup> (remember to treat the other variables as constant):

Then the gradient vector (∇ _f_ ) can be constructed as follows:

At ( _x, y_ ) = (800 _,_ 400) the gradient vector is:

173

Calculate the magnitude of the vector field:

#### **Question 10.8** :

- (a) Take partial derivatives of _f_ ( _x, y_ ) = _x_<sup>4</sup> + 6<sup>_~~√~~_</sup> _<u>y</u> −_ 10. By taking the derivative with respect to _x_ we hold other variables constant. In this case we hold _y_ as a constant. The partial derivative with respect to _x_ is then:

The second and third term in the expression always differentiate to 0 for _x_ . To arrive at the partial derivative with respect to _y_ we treat _x_ as constant and thus:

- <u>4</u>

- (b) Take partial derivatives of _f_ ( _x, y_ ) = _cos_ � _x_ � _e_<sup>_x_2</sup><sup>_y−_5</sup><sup>_y_3</sup> . By taking the derivative with respect to _x_ we hold other variables constant. Well lets start with our partial derivative with respect to _x_ . We need to use the product rule as we have two expressions multiplied together here that contain _x_ : a cosine function and an exponential. Split the function and differentiate:

Apply the product rule:

For the partial derivative with respect to _y_ , we do not need the product rule since variable _y_ only appears in the exponential. We thus arrive at the following:

- (c) Take partial derivatives of _z_ ( _u, v_ ) = _u_<sup>2</sup> <u>9+</u> _<u>u</u>_ 5 _v_<sup>.By taking the derivative with respect to</sup> _x_ we hold other variables constant. Well lets start with our partial derivative with

Chapter 11. Vectors and Partial Differentiation

174

respect to _u_ . We need to use the quotient rule as _u_ appears both in the numerator and denominator. Split the function and differentiate:

Apply the quotient rule:

For the partial derivative with respect to _v_ , we do not need the quotient rule since variable _v_ only appears in the exponential. We thus arrive at the following:

**Question 10.9** : Take the partial derivative of

with respect to _x_ :

Remember that taking the derivative with respect to _x_ we hold other variables constant.

# 12. Crib Sheet

### 12.1 Overview

This Chapter contains a Crib Sheet, is a concise summary of key information, concepts, or formulas, that we have encountered during this course. It is created to serve as a quick reference guide and designed to aid in studying or solving problems efficiently. Please note that you will not be allowed this in the exam. Please see Chapter 14 for the table of equations that will be presented in the exam. If an equation does not appear in this table, then you are expected to learn it for the exam.

### 12.2 Differentiation

Here is a summary of Chapters 1-5 and 11 which covered the topic of Differentiation.

### Finding gradients

We can use **differentiation** to find a function that calculates a gradient at any given point, which we might call _dx_<sup>_dy_.For example, when given a function</sup><sup>_f_(</sup><sup>_x_) = 2</sup><sup>_x_3</sup><sup>_−_20</sup><sup>_x_2 +</sup><sup>_x_+4000</sup> we can use the rules of differentiation to arrive at the expression _dx_<sup>_dy_= 6</sup><sup>_x_2</sup><sup>_−_40</sup><sup>_x_+1.In</sup> this example we have arrived at an **analytical** expression for the gradient. In some cases we cannot arrive at an analytical expression but have to use a **numerical** approximation. The first approach is to take the current _y_ value, subtracted from the previous _y_ value and divided by the increment in _x_ . Thus:

Chapter 12. Crib Sheet

176

OR, with regards to our current and previous _y_ value:

We call this the **Euler backward step** . Rather than taking the value from a previous point, we can also take the value at a future point. The approximate formula then becomes:

We call this the **Euler forward step** .

Both of these approximations are attempting to calculate the same gradient but using different parts of the function curve, or function values. The **central difference** approximation is more accurate for smooth functions, though this accuracy can vary depending on the shape of our curves. In this approach we take function values either side of our current value and use the difference in a similar way. If we have two equally spaced function values, we can write the central approximation approach as:

As you can find in this crib sheet, you may also come across yet another slightly different notation when writing differential equations. Sometimes we write _dx_<sup>_dy_as</sup><sup>_y′_.Allofthe</sup> following expressions are equally valid:

### Common differentials

Here is a table where we list all of the common differentials you will need for this course:

|Function_y_= _f_(_x_)|Derivative <sup>_dy_</sup><br>_dx_|
|---|---|
|constant|0|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup>|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>|
|_ln_(_x_)|1<br>_x_|
|_sin_(_x_)|_cos_(_x_)|
|_cos_(_x_)|_−sin_(_x_)|

177

### Chain rule

The **chain rule** states that to obtain the derivative of a function _f_ ( _x_ ), which can be written as a function of another function, (i.e. _f_ ( _g_ ( _x_ ))), we differentiate the function, _f_ , with respect to the function _g_ and multiply the result by the derivative of _g_ with respect to _x_ :

### Product rule

The **product rule** states that to obtain the derivative of a function _f_ ( _x_ ), which can be written as the product of two functions _u_ ( _x_ ) and _v_ ( _x_ ) (i.e. _u_ ( _x_ ) _v_ ( _x_ )), we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dxdv_<sup>and use:</sup>

### Quotient rule

The **quotient rule:** states that to obtain the derivative of a function _f_ ( _x_ ), which can be written as function _u_ ( _x_ ) divided by function _v_ ( _x_ ) (i.e.<sup>_u_</sup> _v_ (<sup><u>(</u></sup> _x_<sup>_x_</sup> )<sup><u>)), we calculate</u></sup><sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and</sup> use:

### Properties of a derivative and Stationary values

Remember, the derivative of a function at a given point represents the gradient of a function at that point, indicating the rate of change. Therefore, we can use the derivative to know where a function is increasing, decreasing or neither. We can see that if the rate of change is negative,

then the function is decreasing and that if the rate of change is positive,

then the function is increasing. If the derivative is zero,

then it is likely the function will be changing direction either side. This means that the point on the function where the derivative is either a **maximum value** , **minimum value**

178

Chapter 12. Crib Sheet

or a **saddle point** . This turns out to be a very useful property and more generally we call these **stationary values** or **stationary points** .

Sometimes it will not always be possible to solve an equation equal to zero by rearranging or factorising, due to the complexity of the function. We then must use an algorithm to find the stationary values (See Newton’s method below). To find a stationary value we:

1. Differentiate the function, to find the gradient function, _f_<sup>_′_</sup> ( _x_ ) or _dx_<sup>_dy_</sup>

2. Set the gradient function to zero and solve for _x_ .

3. Substitute _x_ into _f_ ( _x_ ) to get what the value of the stationary points are.

We verify that we have found a minimum and maximum point using the second-order derviatives (see below)

### Second-order derivatives

The **properties of derivatives** and how to use them to identify the **stationary values** of functions are listed above. These properties are invaluable for optimising functions or processes. However, to determine whether a stationary value represents a maximum or a minimum, a formal method for verifying this involves something called the **second-order derivative** which involves differentiating a function _f_ ( _x_ ) twice:

The second-order derivative has some very interesting and useful properties. Previously we saw that the first-order derivative, _f_<sup>_′_</sup> ( _x_ ) tells us about the rate of change of a function, _f_ ( _x_ ). The second-order derivative, _f_<sup>_′′_</sup> ( _x_ ), goes a step further by telling us how the rate of change, _f_<sup>_′_</sup> ( _x_ ), itself is changing.

The properties of second-order derivative make them very useful for understanding the nature of stationary points, which are the points where _f_<sup>_′_</sup> ( _x_ ) = 0. Here’s how _f_<sup>_′′_</sup> ( _x_ ) helps us classify these points:

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_)</sup><sup>_<_0, then</sup><sup>_f_(</sup><sup>_x_) has a local maximum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_)</sup><sup>_>_0, then</sup><sup>_f_(</sup><sup>_x_) has a local minimum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f ′′_(</sup><sup>_x_) = 0, then it is not possible to conclude anything about the point</sup><sup>_x_.It could</sup> be saddle point (neither a maximum nor a minimum) so we need to either visually inspect the stationary value or or further evaluation of _f_ ( _x_ ) is needed.

### Steady state

When a system is in steady-state, the key variables that describe the system’s behavior do not change over time. In a chemical system, this means that even though processes

179

are happening that could cause change, the system’s variables stay the same. For this to happen, there must be a continuous flow of materials through the system. This rate of change can be written as:

This equation means that the rate of change of _w_ is a function of time and multiple sources and sinks of water which I have expressed as _x_ 1, _x_ 2. Using the above definition of steady state, here the rate of change does not change over time, we can take the derivative of the equation above:

This equation tells us that the second derivative of _w_ with respect to time is zero. In other words, the rate of change of the volume of water is not changing—it remains constant. This implies that there is a steady flow, and the total amount of water in the system remains constant.

### Finding roots of equations: Newton-Raphson method

We know how derivatives help us understand change. We need to **find the roots** of a function, which is where a **function equals zero** . You have encountered these when finding stationary values. We might be able to solve the equation directly to find the root (see above), however, in many cases, we will not. In these situations, we must use Newton’s method which generally is written as:

where _f_<sup>_′_</sup> ( _x_ ) is the derivative of _f_ ( _x_ ). We iterate through until we reach a number of desired iterations or we have converged based on some criteria (i.e. three decimal places do not change).

### Ordinary Differential Equations

The theoretical base of many of the processes we are interested in are written in the form of Ordinary Differential Equations (ODEs). These are the derivative functions we have been working with. To predict values or properties in the past or future, we can integrate ODEs either without limits, or between specific limits. Some examples of first-order ODEs have been:

- <sup>The</sup><sup>**radioactive decay equation**: The number of decays per unit time is proportional</sup> to the number of unstable nuclei:

where _λ_ is a constant for a specific isotope and _N_ is the number of unstable nuclei.

180

Chapter 12. Crib Sheet

- <sup>**Thehydrostaticequation**:Thedensityofairdependsonthepressure,</sup><sup>_P_,and</sup> _<u>P</u>_

- temperature of the air, _T_ , (through the ideal gas law): _ρ_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J</sup> kg<sup>_−_1</sup> K<sup>_−_1</sup> :

- <sup>**Newton’s Laws of Motion**:They state that:</sup>

   - where _a_ is accelaration, _v_ is velocity, _x_ is distance, _m_ is mass and _F_ is the total forces acting on a object. Each expression is equivalent to the other.

- <sup>**Fourier’s Law**:Fourier stated that the flux of heat through a substance is propor-</sup> tional to the negative gradient of temperature in the substance (i.e. heat flows from hot to cold). We can express this, known as Fouriers law, as a differential equation:

where _T_ is the temperature and _x_ the distance variable.

- <sup>**Fick’s Law**:Fick also found that the law that governs transport of mass by</sup><sup>_Brow-_</sup> _nian motion_ (i.e. random thermal motion) moves from high concentrations to low concentrations. We can express this, known as Fick’s law, as a differential equation:

where _J_ is the mass flux, _C_ is the concentration of mass (e.g. mass of pollutant / gas or particulate) and _D_ is a diffusion coefficient which depends on the properties of the substance that is diffusing.

Other examples of ODEs that we have seen are **homogeneous, linear, second-order ODEs** which resemble the following expression:

Some examples of second-order ODEs have been:

- <sup>**Newton’s Laws of Motion**:</sup>

where _a_ is accelaration, _x_ is distance, _m_ is mass and _F_ is the total forces acting on a object. Each expression is equivalent to the other.

- <sup>**Fourier’sandFick’sLaws**:Assumingsteadystate,wespecifythattherateof</sup> change remains constant, either over space or time, we can rewrite them as:

More information can be seen in Chapter 13.

181

### Initial and Boundary Value Problems

Some ODEs are called _initial value problems_ <u>, where the initial conditions are specified</u> and you solve to find something in the future or a certain distance away. Other kinds of differential equations are called _boundary value problems_ <u>,</u> where upper and lower boundary conditions are specified.

### Partial differentiation

When there are more than one dimension we have to use something else to denote the gradient. The standard that is used is called ‘grad’, which is defined for a scalar field and can be written _grad_ ( _f_ ) or also written ∇ _f_ . We usually called this _‘grad-f’_ .

The ∇ _f_ (where _f_ = _f_ ( _x, y, z_ ) is a scalar field) is actually a vector. In Cartesian coordinates and vector form it is:

Vectors have **magnitude** and **direction** . In our set of problems we consider vectors in Cartesian form, that is broken down into components along _x_ , _y_ and _z_ of a Cartesian domain. The component along _x_ is component _i_<sup>ˆ</sup> , along _y_ is component _j_<sup>ˆ</sup> and along _z_ is component ˆ _k_ . So the gradient has magnitude and direction. Notice the change in the derivative symbol. Specifically, let us highlight the gradient along the x axis:

Up to this point in our course, we have been using the expression.

The change is important. The new expression is called a _partial differential equation_ . When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant. We are only interested in information along the axis given by the variable in the denominator.

We can use this to calculate the magnitude of the gradient at any given point. The **magnitude** of a vector _a_ ¯ = _a_ 1 _i_<sup>ˆ</sup> + _a_ 2 _j_<sup>ˆ</sup> + _a_ 3 _k_<sup>ˆ</sup> can be calculated by taking the square root of all of the square its components:

182

Chapter 12. Crib Sheet

### 12.3 Integration

**Integration is the reverse of differentiation** . Since the derivative function provides us with a **gradient** , integration therefore provides us with a function that can be used to **calculate absolute values** . For example, if a derivative function tells us how much water is changing over time, integrating that function tells us how much water is at a given time or how much total water has changed over a specific time period. To integrate a differential equation therefore requires us to reverse the steps taken to get to that point.

Because integration can be seen as a **summing up** of lots of smaller rectangles we write it formally with an S-shaped symbol:

here the � symbol represents a **summing up** . The _dx_ represents the length of the base of each rectangle (i.e. ∆ _x_ ) and the sub and super-scripts on the � are known as _limits of integration_ .

### Common integrals

Here is a table where we list all of the common integrals you will need for this course:

|Differential equation <sup>_dy_</sup><br>_dx_|Integral,_y_|
|---|---|
|constant|_constant ×x_+_d_|
|_x_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_ </sup>+_d_|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_)+_d_|
|_cos_(_x_)|_sin_(_x_)+_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

where _d_ is a constant.

### Indefinite integration

In **indefinite integration** , we do not prescribe limits on our integral, as per the table above. We add a constant in the integration here because integration is the reverse process of differentiation, and differentiating a constant yields zero. This means that the original function before differentiation could have any constant value, which cannot be determined from the integral without limits, or initial conditions alone. For example, if we want to **integrate** _y_ = _x_<sup>2</sup> , we write this out as follows:

183

### Definite integration

In **definite integration** , we derive the integral then evaluate the this for a lower and upper limit, and then calculate the difference. For example, if we want to **integrate** _y_ = _x_<sup>2</sup> between _x_ = 1 to _x_ = 2, we write this out as follows:

note that we calculate the integral and then evaluate the function by putting in both limits and calculating the difference.

### Integration by substitution

There are occasions when making a **substitution** in an integration enables us to perform what seems to be an otherwise difficult integration. For example, when the integrand contains a factor _ax_ + _b_ , often substituting _u_ = _ax_ + _b_ will enable you to evaluate the integral. However, we also need to write down what _dx_ is in terms of _u_ . For example, lets integrate ( _x_ + 4)<sup>2</sup> :

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Make the substitution in the original integral

184

Chapter 12. Crib Sheet

7. Integrate as usual:

8. Substitute the original expression back in to get the final expression:

So we see that we can integrate more complicated functions using substitution. We want to use a substitution so that the integration becomes something we can use our table of standard integrals for. However, this is integration by substitution for **indefinite integrals** . In many cases, we want to find the **area under a curve** so the integral has limits, therefore we have to perform **definite integration** . For example, lets integrate ( _x_ + 4)<sup>2</sup> between _x_ = 0 and _x_ = 1:

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Find the new limits of the integral:

7. Make the substitution in the original integral

8. Integrate as usual:

185

### Integrating Second-order ODEs

_Second order differential equations_ are differential equations that contain a _second order derivative_ . To solve second order ODEs we often have to integrate the equation twice. Firstly to get the first gradient and secondly to get the solution. See above for examples.

In the cases, we are concerned with **homogeneous, linear, second-order ODEs** which resemble the following expression:

To find a general solution for _y_ we first write out the **auxiliary** equation

and solve it to find the roots. If the roots are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _−_ 4 _ac <_ 0) in this course. In both general solutions, we have added two new constants _A_ and _B_ as we are combining multiple solutions we need to know how much each will contribute to the final solution. To calculate their values, we need some initial conditions on _y_ and _y_<sup>_′_</sup> such as:

The second-order ODEs above are called **initial value problems** . Other kinds of ODEs are called **boundary value problems** , where upper and lower boundary conditions are specified on _y_ and _y_<sup>_′_</sup> such as:

This gives us more information this means that we have to make the solution meet at both points. Examples include Newton’s Laws of Motion, Fick’s and Fourier’s laws, which are described above.

# 13. Constants and Physical Laws

### 13.1 Overview

This Chapter contains a concise summary of key information on the constants and physical laws that are used throughout the course. You are not expected to memorise the contents of this Chapter, as it is designed to supplement the course.

### 13.2 Constants, units and common formulae

**Table 13.1:** Derived Units

|**Entity**|**Abbreviation**|**Name**|
|---|---|---|
|Force|N=kg_·_m_/_s<sup>2</sup>|newton|
|Energy|J=kg_·_m<sup>2</sup>_/_s<sup>2</sup>|joule|
|Power|W=J_/_s|watt|
|Pressure|Pa=N_/_m<sup>2</sup>|pascal|
|Frequency|Hz=1_/_s|hertz|
|Electronic potential|V=J_/_C|volt|
|Capacitance|F=C_/_V|farad|
|Charge|C=s_·_A|coulomb|
|Resistance|Ω=V_/_A|ohm|
|Magnetic feld|T=N_/_(A_·_m)|tesla|
|Nuclear decay rate|Bq=1_/_s|becquerel|

188

Chapter 13. Constants and Physical Laws

**Table 13.2:** Fundamental Units

|**Entity**|**Abbreviation**|**Name**|
|---|---|---|
|Mass|_kg_|kilogram|
|Time|_s_|second|
|Current|_A_|ampere|

**Table 13.3:** Physical constants

|**Constant**|**Defnition**|**Value and unit**|
|---|---|---|
|_g_|earths gravitational constant|9.80 m s<sup>_−_2</sup>|
|_c_|speed of light in vacuum|3_._00_×_10<sup>8 </sup>ms<sup>_−_1</sup>|
|_e_|charge of electron|1_._60_×_10<sup>_−_19 </sup>C|
|_me_|mass of electron|9_._11_×_10<sup>_−_31 </sup>kg|
|_mn_|mass of neutron or proton|1_._67_×_10<sup>_−_27 </sup>kg|
|_NA_|Avogadro’s number|6_._022_×_10<sup>23 </sup>molecules/mol|
|_kB_|Boltzmann’s constant|1_._38_×_10<sup>_−_23</sup>J_/_K|
|_R_|universal gas constant|8_._31<br>J<br>mol K <sup>= 0</sup><sup>_._0821</sup> <sup>l atm</sup><br>mol K|
|_c_w|specifc heat of water|1 cal_/_(g K)]|
|1 cal|calorie|4_._186 J|
|_σ_|Stefan-Boltzmann constant|5_._67_×_10<sup>_−_8</sup><br>W<br>m<sup>2</sup>K<br>4|

**Table 13.4:** Powers of Ten and Their Symbols

||Metric Prefxes<br>||
|---|---|---|
|**Prefx**|**Symbol**|**Value**|
|tera|T|10<sup>12</sup>|
|giga|G|10<sup>9</sup>|
|mega|M|10<sup>6</sup>|
|kilo|k|10<sup>3</sup>|
|hecto|h|10<sup>2</sup>|
|deka|da|10<sup>1</sup>|
|deci|d|10<sup>_−_1</sup>|
|centi|c|10<sup>_−_2</sup>|
|milli|m|10<sup>_−_3</sup>|
|nano|n|10<sup>_−_9</sup>|
|pico|p|10<sup>_−_12</sup>|
|femto|f|10<sup>_−_15</sup>|

189

### 13.3 Common formulae

**Table 13.5:** Useful Formulae

|Formulae||
|---|---|
|**Defnition**|**Formula**|
|Circumference of a circle with radius_r_, r diameter_d_|_C_=2_πr_=_πd_|
|Area of a circle with radius_r_, or diameter_d_|_A_=_πr_<sup>2 </sup>=_πd_<sup>2</sup>_/_4|
|Area of a sphere with radius,_r_|_A_=4_πr_<sup>2</sup>|
|Volume of a sphere with radius,_r_|_V_ =(4_/_3)(_πr_<sup>3</sup>)|

### 13.4 Radioactive decay

Certain isotopes of atoms are unstable because they dont contain enough ‘glue’ or neutrons to hold the protons together in order to rectify this lack of stability the unstable isotopes spontaneously decay into daughter nuclei. There are three types of decay that are referred to as _α_ decay, _β_ decay and _γ_ decay, which are the high energy particles or radiation that is given off during the decay.

#### Alpha decay

Alpha decay is a type of radioactive decay in which an atomic nucleus emits an alpha particle, or rather a helium nucleus, and thereby transforms (or ‘decays’) into an atom with a mass number 4 less and atomic number 2 less. For example:

which can also be written

Note this is not a chemical reaction as it doesn’t involve movement of electrons per-se.

Why should this happen? Well before the decay the<sup>238</sup> U atom had 92 protons and 146 neutrons the ratio of neutrons to protons was low for such a large nucleus:<sup><u>146</u></sup> 92<sup>= 1</sup><sup>_._587%.</sup> Whereas after the ratio is<sup><u>144</u>Althoughthedifferencedoesn’tseemalotitis</sup> 90<sup>= 1</sup><sup>_._60.</sup> enough to make the daughter nucleus more stable and less likely to decay.

#### Beta decay

Beta decay is a type of radioactive decay in which a beta particle (an electron or a positron) is emitted. In the case of electron emission, it is referred to as beta minus ( _β_<sup>_−_</sup> ), while in the case of a positron emission as beta plus ( _β_<sup>+</sup> ). In electron emission, an electron antineutrino

190

Chapter 13. Constants and Physical Laws

is also emitted, while positron emission is accompanied by an electron neutrino. For _β_<sup>_−_</sup> decay a neutron is converted to a proton, electron and an anti-neutrino

Again this is not a chemical reaction as it doesn’t involve electrons taking part in bonds. Note though that when _β_<sup>_−_</sup> decay occurs the daughter nucleus is often left in an excited state and this can then decay to give off electro-magnetic radiation or gamma rays.

For _β_<sup>+</sup> decay a proton is converted to a neutron, positron and a neutrino.

In the same way that too few neutrons cause the nucleus to become unstable, too many also cause the nucleus to become unstable as they try to pull everything together too tightly. In this case a neutron can change into a proton and emit a _β_ particle. This can only occur when the binding energy of the daughter nucleus is higher than the mother.

#### Gamma decay

Gamma decay is a type of radioactive decay when a nucleus in an excited state decays to a lower state. Gamma rays are very penetrating high energy radiation.

#### Radioactive decay equations

For _α_ and _β_ decay we can apply the radioactive decay equations. The law states that the number of decays per unit time is proportional to the number of unstable nuclei:

where _λ_ is a constant for a specific isotope and _N_ is the number of unstable nuclei. This kind of law is quite common in physics. It is to be expected since if you have more unstable nuclei you would expect to observe more decays per second and vice versa. Another statement of this law is that the number of unstable nuclei decays away with time:

where _N_ 0 is the number of unstable nuclei at time _t_ = 0. The constant _λ_ is used to characterise how quickly the unstable nucleus decays it can be related to half-life (which is the time it takes for the initial number of unstable nuclei to decay to half the initial number) as

where _t_ 1 _/_ 2 is the half-life.

191

**Table 13.6:** Typical unstable isotopes, with their decay mode and half-life

|**Parent atom**|**Radioactive particle**|**Energy**|**Half-life**|
|---|---|---|---|
|235U|_α_|4.52 MeV|7_._1_×_10<sup>8 </sup>years|
|238U|_α_|4.18 MeV|4_._5_×_10<sup>9 </sup>years|
|232Th|_α_|3.98 MeV|1_._4_×_10<sup>10 </sup>years|
|222Rn|_α_|5.49 MeV|3_._825 days|
|14C|_β_|0.56 MeV|5670 years|

### 13.5 Newton’s laws

Before the 20th century, our understanding of the physical world was built entirely on classical mechanics. More specifically - **Newtonian Physics** . This framework emerged from the collective efforts of the "Scientific Revolution", spanning figures like Nicolaus Copernicus, Galileo Galilei, and Isaac Newton.

Newton’s laws of motion, a cornerstone of classical mechanics, were first presented in `Philosophiae Naturalis Principia Mathematica (1687)` , commonly known as the `Principia` . In 1543, Nicolaus Copernicus proposed a heliocentric model of the universe, placing the Sun rather than Earth at its center. This radical idea laid the groundwork for subsequent contributions by Galileo, Johannes Kepler, and René Descartes, who collectively challenged and replaced the Aristotelian worldview.

In the `Principia` , Newton formulated **three laws** to explain planetary motion, in order to explain why the orbits of the planets are ellipses rather than circles. These laws, however, extend far beyond planetary motion, offering a universal framework for understanding force and motion. Newton’s laws are as follows:

1. **Law of Inertia:** A body at rest or moving at a constant speed in a straight line will remain in that state unless acted upon by an external force.

2. **Law of Force and Momentum:** The rate of change of a body’s momentum is directly proportional to the force applied, with the change occurring in the same direction as the force (i.e. if a force acts on a body, that body will experience a change in momentum). This is captured in equations you see throughout this course.

3. **Law of Action and Reaction:** When two bodies interact, they exert forces on each other that are equal in magnitude and opposite in direction. You will have likely come across this law before; also known as the law of action and reaction.

In a number of our problems, we solve Newtons second law to predict how fast or far a body will travel down an incline. Since gravity is pulling the body downwards, why doesn’t the body move through the surface? Well, in very simplistic terms the surface

192

Chapter 13. Constants and Physical Laws

applies an equal and opposite force to the body resting on it. In reality, molecular forces that dictate the properties of both the object and surface also play a role but these laws are adequate to explain our observed motion.

#### Newton’s second law

Newton’s second law of motion is given by the following equation:

where _F_ is the net force acting on a body (in Newton’s, or _N_ ) that has a mass _m_ (in _kg_ ) and therefore acceleration _a_ (in _m.s_<sup>_−_2</sup> ). We can re-write this equation as an ordinary differential equation (ODE) as follows:

where these expressions are equal, and we use the fact that _a_ = _v dx_<sup>_<u>dv</u>_(because</sup><sup>_v_=</sup><sup>_<u>dx</u>_</sup> _dt_<sup>, so</sup> _v_<sup>_<u>dvdv</u>_</sup> _dx_<sup>=</sup> _dt_<sup>, which is equal to</sup><sup>_a_).</sup>

#### Kinetic energy

As we talk about forces and movement we should also consider the transfer of energy. This is obvious when we discuss transfer of heat, but the same applies for movement of mass. It takes energy to move something. As we consider the movement of a body down an incline, we can consider the gravitational force imparting a kinetic energy to our body. We often talk about the work done by something. In Physics, work done can be calculated through the following equation:

where _W_ is the work done (Joules, J or newton-metres, (Nm)), _F_ the force [Newtons (N))] and _s_ the distance travelled (in metres (m)). As an example, as we push a body against a frictional surface we transfer energy into heat. If a force of 20N acts along a path of distance 3m, then 60J of work has been transferred. This sounds rather abstract. We have an amount of energy that has been transferred but we know, through our real-world experience, that the same amount of energy would surely not lead to a 20kg ball and a 20g ball of mass moving at the same speed, would it? We expect the smaller mass to end up with a higher speed with the same transfer of energy. We can calculate this directly.

Newton’s second law _F_ = _ma_ = _m_<sup>_<u>d</u>_</sup> _dt_<sup>22</sup><sup>_<u>x</u>_can be made to look like a 1st order ODE because</sup> _<u>d</u>_<sup>2</sup> _<u>x dx</u> dt_<sup>2=</sup> _dt_<sup>_<u>d</u>_</sup> � _dt_ � =<sup>_<u>dv</u>_</sup> _dt_<sup>, which also equals</sup><sup>_v_</sup> _dx_<sup>_<u>dv</u>_, by chain rule.</sup>

193

If we then consider that the work done along a path _dx_ is equal to _F × dx_ , the total work done is � _Fdx_ . If we proceed using the 1st order ODE variant of Newton’s second law and integrate this equation, we arrive at the following equation the describes the change in kinetic energy:

where _v_ would be final velocity and _u_ the initial velocity.

### 13.6 Heat transfer and Fourier’s laws

We know from our own experience that heat migrates from warm to cold regions. There is a molecular and thermodynamic description that explains why this is the case. In 1822 a french Physicist and Mathematician, Joseph Fourier, concluded that **the heat flux resulting from thermal conduction is proportional to the magnitude of the temperature gradient and opposite to it in sign** . There are a number of terms here, but we can see the use of a gradient and reference to the sign of the gradient. In other terms, this is saying that heat flux moves in the opposite direction to the gradient in heat - it moves from hot to cold. What is thermal conduction? Thermal conduction is the transfer of heat from hotter to cooler parts of a body resulting in equalizing of temperature. In contrast to heat transfer by convection, thermal conduction has nothing to do with macroscopic displacements in the body, but is a result of a direct energy transfer between particles, such as molecules, atoms, and electrons, with higher energy and ones with lower energy. Contrary to heat transfer by radiation, there is no thermal conduction in vacuum. Materials have a measurable thermal conductivity; a property that quantifies the potential for dissipation of heat through it. The table below lists thermal conductivity of some common materials.

**Table 13.7:** Thermal conductivity of some common materials

|**Material**|**Thermal Conductivity (**_W.m_<sup>_−_1</sup>_K_<sup>_−_1</sup>**)**|
|---|---|
|Air at 0_◦C_|0.024|
|Aluminum|205.0|
|Brass|109.0|
|Concrete|0.8|
|Copper|385.0|
|Glass|0.8|
|Styrofoam|0.01|
|Wood|0.12-0.04|

194

Chapter 13. Constants and Physical Laws

**Figure 13.1:** Schematic illustrating transfer of heat normal to the surface area of a substance. Source: `https://en.wikipedia.org/w/index.php?curid=59712855`

We note that Thermal conductivity (which we have denoted _k_ ) is defined as the quantity of heat ( _Q_ , measured in Watts or _W_ ) transmitted through a unit thickness ( _L_ - a value of 1) in a direction normal to a surface of unit area ( _A_ , in _m_<sup>_−_2</sup> ) due to a unit temperature gradient (∆ _T_ , in _K_ ) under steady state conditions and when the heat transfer is dependent only on the temperature gradient. In equation form this becomes the following:

This is shown schematically in Figure 13.1

How do we relate this to a rate of change with distance? We only need to modify this equation slightly. Heat flux is a flow of energy per unit area per unit time (thus in _W.m_<sup>_−_2</sup> , knowing that one Watt is one Joule per second!). If we re-arrange the above equation by moving the ∆ _T_ to the left hand side we arrive at this definition:

Where are variable _q_ is given in _W.m_<sup>_−_2</sup> . This is in one dimension. Heat flux however has both strength and direction. If we re-write our equation as a vector quantity (please see Chapter 11), we arrive at the following:

where **q** is still the flux of heat W m<sup>_−_2</sup> and _k_ is the thermal conductivity W m<sup>_−_1</sup> K<sup>_−_1</sup> , _T_ is the temperature. The symbol ∇ represents the Grad operator covered in Chapter 11. The above equations represent **Fourier’s first law** .

195

If we consider heat conduction in 1-D entering and leaving two sides of a box, volume 1 m<sup>3</sup> , of thickness _δ x_ then the rate that heat enters the box, _R_ (W m<sup>_−_3</sup> ), is equal to the difference in the heat entering through one side and exiting through the other side (i.e. a **gradient of a gradient** ):

If we assume that the box’s temperature is in steady state, _R_ = 0, we can write this as:

which is **Fourier’s second law** . Using vector calculus notation we can write it as:

### 13.7 Mass transfer and Fick’s laws

Following Fourier, a physiologist called Adolf Fick also found that the law that governs transport of mass by **Brownian motion** (i.e. random thermal motion) is very similar (i.e. mass moves from high concentrations to low concentrations). Again from our real-world experience we can see that mass moves from high to low concentrations. Again, there are molecular and fluid properties that are important to understand. We can qualitatively understand some of those properties before we take a look at equations that describe Ficks laws.

**Figure 13.2:** If the particles randomly move around ("diffuse") in the water, they eventually become distributed randomly and uniformly from an area of high concentration to an area of low, and organized (diffusion continues, but with no net flux). Source: `https://creativecommons.org/ licenses/by/3.0`

In a gas we know that the molecules in that gas are moving according to a thermal energy they have at a set temperature. There are relationships that can be used to calculate that

196

Chapter 13. Constants and Physical Laws

thermal speed as a function of temperature and molecular weight. There are also some very interesting distributions of speeds of a given type of molecule but that isn’t for this course. These molecules will collide with each other and change direction accordingly. If we keep that gas within a sealed box we know, through the ideal gas equation, that the gas exerts a pressure on the walls of this box through those collisions. If we were able to inject an initial cluster of molecules in the middle of that box, through this thermal motion they will diffuse out within the box. If we suddenly open a side of the box, the gas will eventually diffuse out of this opening.

The following equation presents **Ficks first law** in one dimension. Can you see the similarity with Fourier’s law and the use of the negative gradient?:

> _J_ is the diffusive flux (amount of substance per unit area per unit time -e.g _g.cm_<sup>_−_2</sup> _.s_<sup>_−_1</sup> . Variable Θ is the concentration (amount per unit volume) along a given axis, in this case it could be the _x_ axis, and is given in units of e.g _molecules.cm_<sup>_−_3</sup> . The derivative would give us units of _molecules.cm_<sup>_−_4</sup> . Variable _D_ is the diffusion coefficient, and is given in units of _cm_<sup>2</sup> _.s_<sup>_−_1</sup> . The diffusion coefficient _D_ is proportional to the squared velocity of the diffusing particles, which depends on the temperature, viscosity of the fluid and the size of the colliding molecules. A table listing some common diffusion coefficients of gases in air can be found below.

The previous equation is in one dimension. As with heat transfer, if we re-write our equation as a vector quantity, we arrive at the following:

The symbol ∇ represents the Grad operator covered in Chapter 11. Fick’s **second law** predicts how diffusion causes the concentration to change with respect to time. Notice how Fick’s first law provides us with a flux. We can relate that flux as another differential equation:

This is a **partial differential equation** . We do not solve these types of equations in our course. Indeed, they are very difficult to solve. We can however use this to frame a steady-state scenario. If the system is in steady-state, Ficks second law this becomes:

Or alternatively we can write (in 1 dimension):

197

We canintegrate this equation to derive expressions that describe the change in concentration along a given dimension.

### 13.8 Atmospheric pressure and the hydrostatic equation

The pressure above the earth’s surface can be found based on the fact that it arises due to the weight of the air above us (this is similar for the pressure in deep water, except it is the weight of water above). We know that the weight of any object is given by the following equation:

where _m_ is the objects mass ( _kg_ ) and _g_ is the Earths gravitational factor. Weight is equivalent to the definition of gravitational force we have been using in Newtons second laws.

The weight of a 1 m<sup>3</sup> cube or air that has density _ρ_ is thus equal to _ρ ×_ 1 _× g_ , since we simply calculate the mass as _V.ρ_ where _V_ = 1 _m_<sup>3</sup> and _ρ_ is given in _kg.m_<sup>_−_3</sup> . We know that the definition of pressure is force per unit area and, as we are working with 1 _m_<sup>3</sup> of air, we can divide by 1 _m_<sup>2</sup> and write an expression for pressure as follows:

The pressure is force per unit area so that the change in pressure (within a column that has area 1 m<sup>2</sup> ) as we move, ∆ _z_ = 1 m, up through the atmosphere is ∆ _P_ = _−ρ × g ×_ ∆ _z_ . We can therefore write that:

that is the gradient in pressure with height is equal to minus the density of the air multiplied by gravity, where gravity, _g_ = 9 _._ 8 m s<sup>_−_2</sup> .

The density of air depends on the pressure, _P_ , and temperature of the air, _T_ , (through the _<u>P</u>_ ideal gas law): _ρ_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J kg</sup><sup>_−_1 K</sup><sup>_−_1.So we can write:</sup>

In actual fact the assumption that the temperature is constant is not true as it usually decreases with height in the atmosphere at about 10<sup>_◦_</sup> C km<sup>_−_1</sup> (i.e. a drop of 10<sup>_◦_</sup> C for every km). When we take into account that temperature drops with altitude the hydrostatic equation becomes:

which has an analytical solution of:

# 14. Provided Equations in the Exam

This Chapter contains equations that will be presented to you in the exam. If an equation does not appear in this Chapter, then you are expected to learn it for the exam.

**Newton’s method:** Recall that we can write Newtons formula for root finding, generally, as:

where _f_<sup>_′_</sup> ( _x_ ) is the derivative of _f_ ( _x_ ).

**Chain rule:** To obtain the derivative of a function _f_ ( _x_ ), which can be written as a function of another function, (i.e. _f_ ( _g_ ( _x_ ))), we differentiate the function, _f_ , with respect to the function _g_ and multiply the result by the derivative of _g_ with respect to _x_ :

**Product rule:** To obtain the derivative of a function _f_ ( _x_ ), which can be written as the product of two functions _u_ ( _x_ ) and _v_ ( _x_ ) (i.e. _u_ ( _x_ ) _v_ ( _x_ )), we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and use:</sup>

**Quotient rule:** To obtain the derivative of a function _f_ ( _x_ ), which can be written as function _u_ ( _x_ ) divided by function _v_ ( _x_ ) (i.e.<sup>_u_</sup> _v_ (<sup><u>(</u></sup> _x_<sup>_x_</sup> )<sup><u>)), we calculate</u></sup><sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and use:</sup>

200

Chapter 14. Provided Equations in the Exam

#### **Common differentials:**

|_y_=_x_<sup>_n_</sup><br>_y_=_e_<sup>_f_(</sup><sup>_x_)</sup>|_dy_<br>_dx_ <br>_dy_<br>_dx_|<sup>=</sup><sup>_nxn−_1</sup><br><sup>=</sup> <sup>_df_</sup><br>_dx _<sup>_ef_(</sup><sup>_x_)</sup>|
|---|---|---|
|_y_=ln(_x_)|_dy_<br>_dx_|<sup>= 1</sup><br>_x_|
|_y_=sin(_x_)|_dy_<br>_dx_|<sup>= cos(</sup><sup>_x_)</sup>|
|_y_=cos(_x_)|_dy_<br>_dx_|<sup>=</sup><sup>_−_sin(</sup><sup>_x_)</sup>|

#### **Common integrals:**

15. Acknowledgments

This course and the course textbook builds on the historical course developed and delivered by Prof David Topping and Prof Paul Connolly in the Department of Earth and Environmental Sciences. I would also like to make reference to a the online Calculus repository provided by Dr Paul Dawkins (Link)
