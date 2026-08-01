---
title: "Exercises9(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 9/Exercises9(1).pdf"
type: pdf
---

Chapter 9. Second-Order Ordinary Differential Equations

146

# Exercises

## Algebraic problems

For this section we are concerned with **homogeneous, linear, second-order ODEs** which resemble the following expression:

_y_ **auxiliary** equation

and solve it to find the roots. If the roots are real and not equal ( _!_ 1 _→_ = _!_ 2 then we can write a general solution as:

If our two roots are real and equal (i.e. _!_ 1 = _!_ 2) then we use the formula:

We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _↑_ 4 _ac <_ 0) in this course.

**Question 9.1** : For the following second-order ordinary differential equations, write out the auxiliary questions, find the roots and express the general solution:

- (a)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>_+6</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>↑_16</sup><sup>_y_= 0</sup> (b) 8<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_2</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>↑y_= 0</sup> (c) 4<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_24</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>_+27</sup><sup>_y_= 0</sup> (e)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_4</sup><sup>_y_= 0</sup>

**Question 9.2** : Return to the general solutions found in Question 9.1 and use the following initial or boundary conditions to find the constants _A_ and _B_ and then state the full solution. (a)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>_+6</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>↑_16</sup><sup>_y_= 0 using</sup><sup>_y_= 2 and</sup> _dx_<sup>_dy_=</sup><sup>_↑_6 when</sup><sup>_x_= 0.</sup> (b) 8<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_2</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>↑y_= 0 using</sup><sup>_y_= 10 and</sup> _dx_<sup>_dy_= 2 when</sup><sup>_x_= 0.</sup> (c) 4<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_24</sup><sup>_d_</sup> _dt_<sup>_<u>y</u>_+27</sup><sup>_y_= 0 using</sup><sup>_y_= 0 and</sup> _dx_<sup>_dy_= 12 when</sup><sup>_x_= 0.</sup> (d)<sup>_d_</sup> _dt_<sup>22</sup><sup>_<u>y</u>↑_4</sup><sup>_y_= 0 using</sup><sup>_y_=</sup><sup>_↑_4 and</sup> _dx_<sup>_dy_= 0 when</sup><sup>_x_= 0.</sup>

**Question 9.3** : Solve the following differential equation given the associated initial conditions associated with both the function value for _y_ and gradient<sup>_dy_.</sup>

147

where

**Question 9.4** : For the following second-order ordinary differential equations, write out the auxiliary questions, find the roots and express the general solution:

## Real-world problems

**Question 9.5: Newtons laws of motion (as 2nd Order ODEs)** : We can write Newtons second law of motion as follows:

- (a) Use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_↓_</sup> , starting with velocity _v_ = 0. Do not consider air resistance or friction.

- (b) Use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_↓_</sup> , starting with velocity, _v_ = 0. Do not consider air resistance but consider the frictional force to be equal to _µ ↔ N_ , where _N_ is the magnitude of the contact force and _µ_ = 0 _._ 1. Solve this for initial velocity = 0 to get the position _x_ vs time.

**Question 9.6: Fick’s Law of diffusion (as 2nd Order ODEs)** : An industrial incinerator produces a steady output of particulate matter having a concentration of _C_ 0 = 1 _._ 0 mg m<sup>_↑_3</sup> of air at the chimney. 1 km away from the incinerator plant the concentration is _C_ 1 _km_ = 0 _._ 1 mg m<sup>_↑_3</sup> . Some houses are a distance of 500 m away from the plant. Using Fick’s law of 1-d diffusion,<sup>_<u>d</u>_</sup> _dx_<sup>2</sup><sup>_<u>C</u>_2= 0, what is the concentration of pollutant where the houses are?Note</sup> that you have been told the limit for particulate matter is 0 _._ 5 mg m<sup>_↑_3</sup> . Is the concentration at the location of the houses above 0 _._ 5 mg m<sup>_↑_3</sup> ?

**Question 9.7: Fouriers law of heat transfer (as 2nd Order ODEs)** : 3 km below the surface there is a hot granite bed, with a steady-state temperature of 250<sup>_↓_</sup> C. The temperature just below the surface the temperature stays relatively constant at 10<sup>_↓_</sup> C, use the steady-state Fouriers law in 1-d,<sup>_<u>d</u>_</sup> _dx_<sup>2</sup><sup>_<u>T</u>_2= 0 to derive an equation that describes the temperature profile</sup> between the surface and the hot granite.

148 Chapter 9. Second-Order Ordinary Differential Equations

**Question 9.8: Newtons laws of motion (as 2nd Order ODEs)** : Derive an equation for the displacement with time if an object moving at an initial velocity is experiencing a constant acceleration. In other words, we know that we can write Newtons second law as a second order ODE):

where _a_ is now a constant. Proceed with integrating this expression by assuming that the starting position is _x_ = 0 and initial velocity is _v_ 0 m/s.
