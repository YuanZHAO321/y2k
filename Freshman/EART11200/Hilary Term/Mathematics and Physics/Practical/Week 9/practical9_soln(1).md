---
title: "practical9_soln(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 9/practical9_soln(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 9 Practical - Integrating Second-Order ODEs (Solutions)_

1/ 12

## COURSE LAYOUT

|**Date**|**Week**|**Topic**|
|---|---|---|
|27/01/2025|20|Calculating Gradients|
|03/02/2025|21|Introduction to Differentiation|
|10/02/2025|22|Differentiating Combinations of Functions|
|17/02/2025|23|Optimisation & Properties of Derivatives|
|24/02/2025|24|Second Order Derivatives & Root Finding|
|03/03/2025|25|Introduction to Integration|
|10/03/2025|26|Integration using Newtons Laws|
|17/03/2025|27|Integration by Substitution|
|24/03/2025|28|Integrating Second Order ODEs|
|31/03/2025|29|Vectors and Partial Differentiation|
|07/04/2025|30|Non-teaching week|
|14/04/2025|31|Easter break|
|21/04/2025|32|Easter break|
|28/04/2025|33|Revision: Differentiation|
|05/05/2025|34|Revision: Integration<br>**Exam Period**|

2/ 12

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of second-order ordinary differential equations and explain their role in mathematical and physical modelling.

- (2) Solve second-order ODEs to generate general solutions using the auxiliary equation method

- (3) Determine full solutions to second-order ODEs by applying given initial conditions.

- (4) Apply second-order ODEs to model physical processes through boundary conditions in real-world examples such as Newtons Laws, Heat Transfer, and Mass Transfer

3/ 12

## EXERCISE 1: SECOND-ORDER ODES

▶ Suppose we given the following second-order ODE: _d_<sup>2</sup> _<u>y</u> dx_<sup>2</sup><sup>_−d_</sup> _dx_<sup>_<u>y</u>−_6 = 0</sup>

- (a) Write out the auxiliary equation for this ODE.

- (b) Find the roots of the auxiliary equation.

- (c) Write the general solution of the ODE.

4/ 12

## SOLUTION 1: SECOND-ORDER ODES

- (a) The auxiliary equation for this ODE is given by:

- (b) Use the quadratic formula:

<!-- Start of picture text -->
λ = −b ± √ b 2 − 4 ac = − ( − 1)  ± � ( − 1) 2 − 4  ∗ ( − 1)  ∗ 6 = 1  ± √ 25 = 1  ±  5<br>2 a 2  ∗ 1 2 2<br><!-- End of picture text -->

therefore _λ_ 1 = _−_ 2 and _λ_ = 3.

- (c) As the roots are real and distinct, we see that the general solution is:

5/ 12

## EXERCISE 1: SECOND-ORDER ODES

- Suppose we given the following second-order ODE:

_d_<sup>2</sup> _<u>y</u> dx_<sup>2</sup><sup>_−d_</sup> _dx_<sup>_<u>y</u>−_6 = 0</sup>

- and now you are told the following initial conditions:

_y_ (0) = 3 _y_<sup>_′_</sup> (0) = 4

- (d) Find the full solution of the ODE.

6/ 12

## SOLUTION 1: SECOND-ORDER ODES

- Write out _y_ and _y_<sup>_′_</sup> :

- Plug in the initial conditions in to _y_ and _y_<sup>_′_</sup> to get:

- This leaves us with a system of simultaneous equations which we can solve:

7/ 12

## SOLUTION 1: SECOND-ORDER ODES

- Substitute _B_ = 2 into _A_ + _B_ = 3 gives us:

- Then the full solution is given by:

8/ 12

## EXERCISE 2: FICK’S LAWS OF DIFFUSION

- An industrial incinerator produces a steady output of particulate matter, having a concentration of _C_ 0 = 1 _._ 0mg/m<sup>3</sup> of air at the chimney.

- At 1km away from the incinerator plant, the concentration is _C_ 1 = 0 _._ 1mg/m<sup>3</sup> .

- We want to model the diffusion of the particulate matter using Fick’s law of 1D diffusion under

steady state:

- (a) Integrate twice and use the boundary conditions to find the solution to the second-order ODE.

- (b) Some houses are a distance of 500 m away from the plant, is the concentration at the houses above 0 _._ 5mg/m<sup>3</sup> ?

9/ 12

## SOLUTION 2: FICK’S LAWS OF DIFFUSION

### ▶ We integrate this second-order ODE twice:

- At _x_ = 0 we see that _C_ 0 = 1 then:

10/ 12

## SOLUTION 2: FICK’S LAWS OF DIFFUSION

- So the solution to the ODE is: _C_ ( _x_ ) = 1 _−_<sup>9</sup> 10<sup>_x_</sup>

- At the houses 500m away from the incinerator, concentrations are:

- So yes, the concentration of particulate matter is above 0.5mg/m<sup>3</sup> .

11/ 12

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of second-order ordinary differential equations and explain their role in mathematical and physical modelling.

- (2) Solve second-order ODEs to generate general solutions using the auxiliary equation method

- (3) Determine full solutions to second-order ODEs by applying given initial conditions.

- (4) Apply second-order ODEs to model physical processes through boundary conditions in real-world examples such as Newtons Laws, Heat Transfer, and Mass Transfer

12/ 12
