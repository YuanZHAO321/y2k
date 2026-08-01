---
title: "lecture9"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 9/lecture9.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 9 Lecture - Integrating Second-Order ODEs_

1/ 22

## LAST WEEK...

<!-- Start of picture text -->
▶ In some cases, we cant directly integrate by using the<br>common laws, as we are faced with more complicated Derivative d dx y Integral y<br>combinations of functions such as  functions of 0 d<br>functions . constant constant × x  +  d<br>x 2<br>▶ For example, what happens if we want to integrate x x n 2 +1+  d<br>x n n +1 +  d<br>dy e x e x +  d<br>y  = (3 x  + 2) 4 dx<br>� dx = � ke kx e kx +  d<br>▶ This is where  integration by substitution  comes in. cos 1 x ( x ) sinln (( xx ) +) +  d d<br>▶ Integration by substitution is essentially the reverse sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

- Integration by substitution is essentially the reverse process of the chain rule in differentiation.

2/ 22

## LAST WEEK...

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

3/ 22

## LAST WEEK...

5. Get an expression for _dx_ :

_dx_ =<sup>_du_</sup> 3

6. (If needed) Find the new limits of the integral:

When _x_ = _−_ 1 _, u_ = 3 _×_ ( _−_ 1) + 2 = _−_ 1 When _x_ = 1 _, u_ = 3 _×_ 1 + 2 = 5

7. Make the substitution in the original integral

4/ 22

## LAST WEEK...

- Hydrostatic Equation, with constant temperature requires integration via separation of variables:

- Hydrostatic Equation, with varying temperature requires integration by substitution:

5/ 22

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

6/ 22

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of second-order ordinary differential equations and explain their role in mathematical and physical modelling.

- (2) Solve second-order ODEs to generate general solutions using the auxiliary equation method

- (3) Determine full solutions to second-order ODEs by applying given initial conditions.

- (4) Apply second-order ODEs to model physical processes through boundary conditions in real-world examples such as Newtons Laws, Heat Transfer, and Mass Transfer

7/ 22

## SECOND-ORDER DIFFERENTIAL EQUATIONS

- We started thinking about ODEs from the need to calculate a gradient.

- In Week 5, we discovered that differentiating a function

   - twice can also be useful.

- For a stationary value _x_ for the function _f_ ( _x_ ):

   - If _f_<sup>_′′_</sup> ( _x_ ) _<_ 0 the stationary value is a maximum

   - If _f_<sup>_′′_</sup> ( _x_ ) _>_ 0 the stationary value is a minimum

   - If _f_<sup>_′′_</sup> ( _x_ ) = 0 it is not possible to conclude anything about

      - the stationary value.

- If we’re in the situation that _f_<sup>_′′_</sup> ( _x_ ) = 0, then it is potentially a saddle point. Need to investigate further.

8/ 22

## SECOND-ORDER DIFFERENTIAL EQUATIONS

- We can write a physical law using second order ODEs and we have implicitly done this already for Newtons second law.

- In Week 5, we discussed second-order derivatives and observed that

acceleration ( _a_ ) is the rate of change of velocity ( _v_ ), while velocity ( _v_ ) is the rate of change of position or distance ( _x_ ).

- In Week 7, we showed that all objects fall the same distance (quadratically) over the same amount of time in a vacuum, regardless of their mass.

- So... we have written and solved a second-order ODE!

9/ 22

## SECOND-ORDER DIFFERENTIAL EQUATIONS

- **Second-order ordinary differential equations** are ODEs that involve a **second-order**

   - **derivative** .

- We could devote an entire course looking at solving different types of second-order ODEs, but

   - we will only concentrate on

where _a_ , _b_ and _c_ are constants.

- This is referred to as a **homogeneous, linear, second-order ODE** .

- Note that we can write the exact same expression using alternative notation as per the following equation:

10/ 22

## SOLVING SECOND-ORDER DIFFERENTIAL EQUATIONS

- In every problem so far, we have wanted to arrive at a general analytical solution from integrating a differential equation.

- Fortunately, there is a general form we can use if the second-order ODE to be solved has the same form.

- It looks like we might be able to use the approach to solving quadratic equations, but how do

   - we find a value for _y_ ?

- Let’s just jump to an educated guess and assume the expression for _y_ is going to be:

where _λ_ is a constant with an unknown value.

11/ 22

## SOLVING SECOND-ORDER DIFFERENTIAL EQUATIONS

▶ If we differentiate (twice) this expression we can arrive at two expressions:

- Lets now substitute these expressions back into our general differential equation as follows:

- Because _e_<sup>_λx_</sup> cant be zero, it is safe to divide through to acquire a quadratic in _λ_ :

- This is called the **auxiliary** equation or **characteristic** equation.

- When you encounter a **homogeneous second-order ODE** , you can jump straight to this point.

12/ 22

## SOLVING SECOND-ORDER DIFFERENTIAL EQUATIONS

- Looks like we have a quadratic equation.

- If we can solve this, we get a value of _λ_ which we can use to find a solution to the second-order

   - ODE.

- Remember that we can solve (or find roots of) quadratic equations using the following formula:

- When we solve a quadratic expression we will arrive at 2 roots, which we can call _λ_ 1 and _λ_ 2.

- Since there are two roots to the auxiliary equation, the general solution to the second-order

   - ODE will be a combination of the two functions.

13/ 22

## SOLVING SECOND-ORDER DIFFERENTIAL EQUATIONS

▶ If _λ_ 1 and _λ_ 2 are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

_y_ = _Ae_<sup>_λ_1</sup><sup>_x_</sup> + _Be_<sup>_λ_2</sup><sup>_x_</sup>

- If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

_y_ = ( _A_ + _Bx_ ) _e_<sup>_λ_1</sup><sup>_x_</sup>

- We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _−_ 4 _ac <_ 0) in this

course.

14/ 22

## EXAMPLE: SECOND-ORDER DIFFERENTIAL EQUATIONS

- Imagine we are asked to solve the following linear, homogeneous, second-order ODE:

- Firstly, we write out the auxiliary equation:

- Secondly, find the roots ( _λ_ 1 and _λ_ 2) of this equation to understand what solution is needed:

- So the roots are _λ_ 1 = 1 and _λ_ 2 = 5.

15/ 22

## EXAMPLE: SECOND-ORDER DIFFERENTIAL EQUATIONS

### ▶ Since they are real and distinct then the solution will have form

_y_ = _Ae_<sup>_λ_1</sup><sup>_x_</sup> + _Be_<sup>_λ_2</sup><sup>_x_</sup>

- Finally, we plug the values of _λ_ 1 and _λ_ 2

_y_ = _Ae_<sup>_x_</sup> + _Be_<sup>5</sup><sup>_x_</sup>

and this is our general solution to the problem.

16/ 22

## SOLVING SECOND-ORDER DIFFERENTIAL EQUATIONS

- The next question is how to calculate the values for constants _A_ and _B_ ?

- We need more information to constrain these values such as _y_ = 0 and _y_ = 1 when _x_ = 0.

- These are called **initial conditions** , and they tell us the value of the solution and/or its derivatives at a specific point, allowing for a unique solution to the differential equation.

- ▶ For example, for<sup>_d_</sup> _dx_<sup>_<u>y</u>_=</sup><sup>_f_(</sup><sup>_x_), an initial condition might be</sup><sup>_y_=</sup><sup>_y_0at</sup><sup>_x_=</sup><sup>_x_0.</sup>

- You will have seen examples when solving the radioactive decay equation, hydrostatic equation and Newton’s Laws of Motion.

- This will lead us to solving simultaneous equations.

17/ 22

## EXAMPLE: SECOND-ORDER DIFFERENTIAL EQUATIONS

- Let’s return to the previous example:

- The general solution to the problem was

- Suppose that we are told that _y_ = 0 and _y_<sup>_′_</sup> = 1 when _x_ = 0 then we use this information to find

   - _A_ and _B_ .

- Write out _y_ and _y_<sup>_′_</sup> :

18/ 22

## EXAMPLE: SECOND-ORDER DIFFERENTIAL EQUATIONS

- Plug in the initial conditions in to _y_ and _y_<sup>_′_</sup> to get:

- This leaves us with a system of simultaneous equations which we can solve:

- Then the full solution is given by:

19/ 22

## HEAT TRANSFER AND FOURIER’S LAWS

- Heat moves from hot to cold regions and the material, or medium, properties dictate the rate of heat transfer.

- **Fourier’s Second Law** , describes how the distribution of

heat (temperature) in a material changes over time:

_dT dt_<sup>=</sup><sup>_αd_</sup> _dx_<sup>2</sup><sup>_T_2</sup>

where _α_ is the thermal diffusivity (speed heat diffuses).

- Thermal diffusivity combines the material’s thermal conductivity, density, and specific heat capacity.

20/ 22

## MASS TRANSFER AND FICK’S LAWS

- Fick also found that the law that governs transport of mass

   - by Brownian motion (i.e. random thermal motion) is very similar (i.e. mass moves from high to low concentrations).

▶ **Fick’s Second Law** , takes into account the time-dependent change in concentration within a material and the principle of conservation of mass:

_dC dt_<sup>=</sup><sup>_Dd_</sup> _dx_<sup>2</sup><sup>_C_2</sup>

where _D_ is a diffusion coefficient which depends on the properties of the substance that is diffusing

21/ 22

## FOURIER’S AND FICK’S LAWS

- Remember that a system is in steady-state when the rate of change that describes the system’s behavior do not change over time.

- If we assume steady state, we get second-order ODEs which we can simply integrate twice

- We can use boundary conditions to solve this and find an expression.

- **Boundary value problems** differ from **initial value problems** as we specify upper and lower boundary conditions are specified (i.e, when _x_ = _x_ 0 and _x_ = _x_ 1).

- This gives us more information this means that we have to make the solution meet at both points.

22/ 22
