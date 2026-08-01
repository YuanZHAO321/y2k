---
title: "Exercises4(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 4/Exercises4(1).pdf"
type: pdf
---

63

# Exercises

## Algebraic problems

**Question 4.1** : Find the stationary point of the following functions and verify whether they are maxima or minima either by evaluating the function, or using the properties of the derivative.

- (a) _f_ ( _x_ ) = _x_<sup>2</sup> + _x_

- (b) _f_ ( _x_ ) = 2 _x → x_<sup>2</sup>

- (c) _f_ ( _x_ ) = ( _x →_ 2)<sup>2</sup>

- (d) _f_ ( _x_ ) = ( _x →_ 2)(3 _→ x_ ) (e) _f_ ( _x_ ) =<sup>_<u>x</u>_</sup> 3<sup>3</sup><sup>_→_4</sup><sup>_x_2 +15</sup><sup>_x_+5</sup> (f) _f_ ( _x_ ) = _ln_ ( _x_ ) _→ x_

**Question 4.2** : Find two non-negative numbers whose sum is 9 and so that the product of one number and the square of the other number is a maximum. To solve this, first construct the two equations that define these conditions, using variables _x_ and _y_ . To start, you can write _x_ + _y_ = 9.

## Real-world problems

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

If you choose _r_ = 0 _._ 01m, then, since the volume has to be 330 _↑_ 10<sup>_→_6</sup> , the height, _h_ , and surface area, _A_ , has to be:

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

- (b)

**Question 4.6: A gold seam optimisation problem.** You decide to mine a gold seam and want to decide on how long to mine it for to maximise your profits. The cost of gold you can mine per day, _G_ , is a function of the number of days, _n_ , that you mine for. It becomes more difficult to mine the gold as time goes on:

In addition the cost of renting the equipment to mine the gold, _C_ , increases with the number of days:

_P_ = _G →C_ . Graphs of _P, G_ and _C_ are shown in Figure 4.3.

65

- (a) Work out how long you should mine the gold to optimise (find the stationary value of) your profit, _P_ . (Hint: you can either use _chain or quotient rules_ to perform the differentiation. To find the stationary points you will need to solve a quadratic equation).

- (b) In the project a "snag" occurs that causes no profit to be made on one day (see Figure 4.4). After the snag is overcome mining can proceed at a faster rate. A function describing the cost of gold mined as the project goes on is:

Use this function to find the day where the amount of gold extracted hits a snag (you will need to make use of the product rule).

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>Gross profit, G<br>0<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

**Figure 4.3:**

<!-- Start of picture text -->
4<br>10  x 10<br>8<br>Snag<br>6<br>4<br>2<br>0<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

**Figure 4.4:**

Chapter 4. Optimisation and Properties of Derivatives

66

**Question 4.7: Geoengineering.** In this problem economists investigating the _economic cost to society_ , _E_ , of an increase in global temperature, ! _T_ (e.g. see the Stern report) estimate that:

with _E_ in billions of dollars (see Figure 4.5). In addition climate scientists investigating the _marine cloud brightening_ proposal for geoengineering estimate that the technique does have the capability to offset warming by rising CO2. They estimate spending money, _C_ , on a program to implement geoengineering can result in a lower increase in temperature:

where _C_ is the amount spent on the scheme and _d_ is a constant that has some uncertainty (see Figure 4.6).

<!-- Start of picture text -->
5000<br>E( ∆  T)=500 ×∆  T<br>4000<br>3000<br>2000<br>1000<br>0<br>0 2 4 6 8 10<br>Change in global temperature,  ∆  T (K)<br> dollars)<br>9<br>Cost to society, E (x10<br><!-- End of picture text -->

**Figure 4.5:** Hypothetical cost to society as a function of changes in global temperatures

<!-- Start of picture text -->
10<br>∆  T(C)=10 exp(−dC)<br>8<br>6<br>4<br>2<br>0<br>0 10 20 30 40 50<br>Billions spent on geoengineering, C ( ×  10 9  dollars)<br> T (K)<br>∆<br>Change in temperature if we  use geoengineering,<br><!-- End of picture text -->

**Figure 4.6:** Hypothetical change in global temperatures as a function of investment in geoengineering

67

In order to decide whether the scheme is worth implementing we need to get an idea of the _total cost_ that implementing the scheme has (i.e. the benefit plus cost of scheme) vs the _<u>E</u>_ amount spent on implementing it. To do this rearrange Equation 4.1 to give ! _T_ = 500<sup>and</sup> substitute into Equation 4.2 to get an equation for the economic cost to society, _E_ , vs the amount spent on geoengineering, _C_ . Then add on the cost of the scheme, _C_ , to get the _total cost_ , _T_ = _E_ + _C_ :

This function can be seen in Figure 4.7 and we can see there is a minimum in the _total cost_ .

Your goal is to optimise / find the stationary value of Equation 4.3 (i.e. find how much we should spend on the scheme so that we can minimise the total cost). Choose the parameter _d_ to be equal to 2 _↑_ 10<sup>_→_4</sup> ; how much should be spent? What is the meaning of your answer (i.e. what should the advice to policy makers be?)

<!-- Start of picture text -->
χ =E+C<br>χ =500 ×  10 exp(−dC)+C<br>Billions spent on geoengineering, C ( ×  10 9  dollars)<br> dollars)<br>9<br> 10<br>×<br> (<br>χ<br>Total cost in billions,<br><!-- End of picture text -->

**Figure 4.7:** Hypothetical total cost to society as a function of investment in geo-engineering
