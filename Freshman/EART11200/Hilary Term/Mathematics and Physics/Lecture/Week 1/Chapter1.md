---
title: "Chapter1"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 1/Chapter1.pdf"
type: pdf
---

# 1. Calculating Gradients

## 1.1 Maths, Calculus and Physics

In Earth and Environmental Science we are typically interested in understanding our past, and predicting our future. We live in a dynamic world where processes change in a matter of milliseconds to millennia. But what is Physics? If we check Encyclopedia Britannica we see that:

_Its laws are typically expressed with economy and precision in the language of mathematics._

Essentially, Physics presents us with equations that describe the movement of energy through motion. Imagine relevant questions within our scientific domain:Where will warm air move from the tropics? How long will it take for the glacier to melt? But how do we solve these equations? We use the laws of Calculus. Again, if we check Encyclopedia

_Calculus makes it possible to solve problems as diverse as tracking the position of a space shuttle or predicting the pressure building up behind a dam as the water rises._

Calculus gives us the tools to calculate how quickly something is changing for example, or using that information to calculate quantities and states in the past or future. Is that relevant to understanding our changing climate? Physics is intricately built around laws of mathematics, and calculus provides us with the tools to understand the past, present

8

Chapter 1. Calculating Gradients

and future of our planet and our role on it. If we treat mathematics as the language of the universe then, through this course, we are going to expand our vocabulary. Understanding the basic laws of calculus and being able to implement fundamental laws of physics has been central to progressing all physical sciences.

What equations do we start with to practice implementing common rules of Calculus? This depends on the problem we wish to solve and each week we will focus on common problems in physics that are relevant to earth and environment sciences. As a start, we need to become familiar with a number of descriptions and concepts. For example, the following list of equations were taken from Ian Stewart in his book _17 Equations That Changed The World_ . Let us quickly review some of these. You may have come across all of them or a subset, in your previous studies:

1. The first is the Pythagorean theorem. It was Pythagoras of Samos (c.570 – c.495 BC), who was an ancient Greek philosopher that discovered this:

This formula describes the relationship between the sides of a right triangle on a flat plane.

2. The second ones are a handful of laws of logarithms:

This simple rule turns multiplication into addition, division into subtraction and powers into multiples! Logarithms were introduced by John Napier in 1614 to simplify calculations. Indeed, this was the most common way to quickly multiply together large numbers, greatly speeding up calculations in physics, astronomy, and engineering.

3. The third we look at is is Newton’s law of gravitation:

It describes the force of gravity between two objects, _F_ , in terms of a universal constant, _G_ and the masses of the two objects, _m_ 1 and _m_ 2, and the distance between the objects, _r_ . Newton’s law is remarkable in that it explains, almost perfectly, why

9

the planets move in the way they do. Notice the power; how would you rearrange this to calculate _r_ ?.

4. The fourth was derived by Albert Einstein as part of the theory of special relativity, and has adorned many a t-shirt:

This famous formula states matter and energy are equivalent to each other.

5. **derivative** :

Derivatives are central to Calculus, and tell us how much one variable is changing with respect to one or many others. The expression<sup>_d_</sup> _dt_<sup>_<u>f</u>_in the English equivalent</sup> reads: the rate of change of _f_ with respect to variable _t_ , which is often time. We use Calculus to arrive at an expression for<sup>_d_</sup> _dt_<sup>_<u>f</u>_, rather than calculating this by hand.</sup> In this equation, we are using an approximation which forms the basis of the final exercise in today’s class.

6.

These take a messy wave function like a recording of a person talking, and allow us to break the messy function into a combination of a number of simple waves. This transform is at the heart of modern signal processing and analysis, and data compression. However the important component of this equation is the symbol � , which represents the act of **integration** .

tion of the variable _f_ ( _f_ ( _x_ ) tells us that _f_ is a function of variable _x_ e.g. temperature as a function of latitude), but because of the procedures they represent. Whilst a derivative function tells us how much one variable is changing as a function of time, for example, the integral reverses this operation. Specifically, we can convert a derivative at a given point in time (or space) to an absolute or net quantity. For example, if water is flowing out of a reservoir at a variable rate, we could work out the total water lost or gained over a set period of time through the act of integration. Conversely, if we measure the actual value of water in the reservoir at certain points in time, we could then derive a derivative expression that tells us the rate of change at any point in time.

10

Chapter 1. Calculating Gradients

**Figure 1.1:** Interplay between differentiation and integration throughout this course. We start with differentiation and move in to integration later on

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

## 1.2 Approximating gradients

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

Here, ∀ _x_ refers to the step-size or increment used between values in the approximation. Both of these approximations are attempting to calculate the same gradient but using different parts of the function curve, or function values.

The **central difference** method is another way to obtain a numerical approximation for the gradient and is more accurate for smooth functions, though this accuracy can vary depending on the shape of our curves. In this approach we take function values either side

13

of our current value and use the difference in a similar way. If we have two equally spaced function values, we can write the central approximation approach as:

Can you see why we now use 2∀ _x_ in the denominator?

You may come across other (slightly) different notation when writing differential equations. Sometimes we write _dx_<sup>_dy_as</sup><sup>_y↗_.All of the following expressions are equally valid:</sup>

Now we are done with numerical approximations. The analytical derivative of Equation 1.2 above happens to be given by the following:

## 1.3 Working in the practical classes

For the exercises given out each week, you will find the solutions at the end of each Chapter. Rather than print these out in class, I would encourage you to try these first and then take a look at your working. Do try to resist looking at these solutions until you have given each problem a shot. Once you read through the solutions to check your answer, if anything is not clear then please do ask for help during each class. I will walk through example solutions, often at the beginning of the following weeks lecture.

You are not expected to retain a carbon copy of each solution in your head as we move through the course content. Do feel free to revisit material and operations as appropriate. The point of this course is to become familiar with numerical operations used to solve common problems in physical sciences. The more time you spend on these problems, the easier they will become.
