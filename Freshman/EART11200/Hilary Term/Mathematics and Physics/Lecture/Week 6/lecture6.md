---
title: "lecture6"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 6/lecture6.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 6 Lecture - Introduction to Integration_

1/ 24

## LAST WEEK...

▶ Differential equations have an "order".

- Up to this point, we have only differentiated functions, _f_ ( _x_ ) once:

_f_<sup>_′_</sup> ( _x_ ) =<sup>_df_</sup> _dx_

- This is known as the **first-order derivative** .

- Differentiation can be carried out multiple times.

- By differentiating again, we obtain the **second-order derivative** which is defined as:

_f_<sup>_′′_</sup> ( _x_ ) =<sup>_d_</sup> _df_ =<sup>_d_2</sup><sup>_<u>f</u>_</sup> _dx_ � _dx_ � _dx_<sup>2</sup>

2/ 24

## LAST WEEK...

- Second-order derivatives have interesting properties and can be used to confirm whether a stationary point is a maximum or minimum point!

- We see that for a stationary value _x_ for the function _f_ ( _x_ ):

   - If _f_<sup>_′′_</sup> ( _x_ ) _<_ 0 the stationary value is a maximum

   - If _f_<sup>_′′_</sup> ( _x_ ) _>_ 0 the stationary value is a minimum

   - If _f_<sup>_′′_</sup> ( _x_ ) = 0 it is not possible to conclude anything about the stationary value.

- If we’re in the situation that _f_<sup>_′′_</sup> ( _x_ ) = 0, then it is potentially a saddle point. Need to investigate using the properties of the first-order derivative.

3/ 24

## LAST WEEK...

- You may not be familiar with the concept of **steady-state** .

- When a system is in steady-state, the key variables that

describe the system’s behavior do not change over time:

<!-- Start of picture text -->
dV<br>= ⇒ d 2 V<br>dt =  f ( t, x 1 , x 2) dt 2 = 0<br><!-- End of picture text -->

4/ 24

## LAST WEEK...

- In many cases, it will not be possible to calculate when a function has a value of 0. Important for stationary values.

- For example, how do you solve:

- Use Newton’s Method for Root Finding:

- We pick a starting guess _x_ 0 and apply this formula iteratively until we reach some threshold.

5/ 24

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

6/ 24

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of integration and explain its significance in calculus.

- (2) Identify and interpret common notation used in integration.

- (3) Describe the role of Ordinary Differential Equations (ODEs) in scientific modeling across

various disciplines.

- (4) Apply common laws of integration to solve theoretical and real-world problems.

7/ 24

## WHAT IS INTEGRATION?

- Integration is the **reverse** of differentiation.

- Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values.

- The � symbol was introduced by Gottfried Wilhelm Leibniz in the 17th century to represent summation of infinitely many infinitesimally small quantities.

e.g. An equation that calculates the rate of change of temperature in the past, present or future

e.g. An equation that calculates the temperature in the past, present or future

8/ 24

## ORDINARY DIFFERENTIAL EQUATIONS (ODES)

- A large part of science is built on solving Ordinary Differential Equations (ODEs).

- Important in all areas of science, and you have already been playing with them! If we have a

differential equation with respect to 1 variable, we have an ODE. Some "famous" equations:

- You may also come across reference to "types" of ODEs in textbooks. These are various forms of an ODE that require certain approaches to solve them. We don’t dive into them here, but include: Homogeneous, Cauchy-Euler, Harmonic Oscillators.

9/ 24

## INTEGRATION: ANALYTICAL VS. NUMERICAL APPROACHES

- Suppose a derivative function tells us how much the

volume of water in a tank is changing over time:

▶ Integrating this tells us how much water is in the tank at a given time or how much the volume of water has changed over a specific time period.

- We can use area of a triangle and the area of the rectangle to find the area of the curve.

<!-- Start of picture text -->
300<br>250<br>200<br>150<br>100 Area=base ×  height<br>50 Area=0.5base ×  height × Area=0.5base ×  height ×<br>00 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>4<br>2  x 10<br>1.5 Area under the curve<br>1<br>0.5<br>00 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>Flow rate (milli−litres per second)<br>Total volume (milli−litres)<br><!-- End of picture text -->

- Not all functions will be as simple as this.

10/ 24

## INTEGRATION

- For example, consider the following:

▶ We could approximate the integral value by splitting the area into lots of smaller rectangles, with a base of length ∆ _x_ and a height equal to _f_ ( _x_ ), the value of the function at _x_ and sum these up:

- This is a numerical approximation method, similar to the central differences method for differentation.

11/ 24

## INTEGRATION

- Obviously, choice of increment used is important.

- Remember that in numerical differentiation we made the step size small to give us the analytical derivative

_dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

- Well integration works in the same way! Making the

increment smaller in the sum gives us analytical integration:

12/ 24

## INTEGRATION

- Because integration can be seen as a summing up of lots of rectangles we write it with an S-shaped symbol.

- We can use analytical integration to find a function that describes the area under the curve.

▶ Numerical integration is much more involved than numerical differentiation, so we would much rather use an analytical approach:

   - _x_

   - �0 ( _−_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ ) _dx_ = _−_<sup>0</sup> 3<sup>_._1</sup><sup>_x_3 + 5</sup><sup>_x_2</sup>

- How do we do this?

13/ 24

## INTEGRATION - COMMON LAWS

- We can reverse some common derivatives, we arrive at the following functions.

- The more you practice these procedures, the easier it will become to apply them without looking them up.

- Use your math’s survival pack when needed!

- In class this week you will practice using all of these, and also have questions on the weekly assessment related to them.

|**Derivative** <sup>_dy_</sup><br>_dx_|**Integral** _y_|
|---|---|
|0|_d_|
|constant|_constant × x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup><br>|
|_x_<sup>_n_</sup><br>_e_<sup>_x_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_e_<sup>_x_ </sup>+_d_|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_) +_d_|
|_cos_(_x_)|_sin_(_x_) +_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

14/ 24

## INTEGRATION - INDEFINITE INTEGRATION

- Why do we add the constant, d? Well, integration is the

   - opposite of differentiation and differentiation "loses" any constant that might have been present in the original function so we add this in.

- For standard integration we cannot say what the constant is: it can take on any value so we just call it a constant.

- For this reason it is called **indefinite integration** .

- You may have something called initial or boundary conditions, which helps figure out what this constant is!

|**Derivative** <sup>_dy_</sup><br>_dx_|**Integral** _y_<br>|
|---|---|
|0|_d_|
|constant|_constant × x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup><br>|
|_x_<sup>_n_</sup><br>_e_<sup>_x_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_e_<sup>_x_ </sup>+_d_|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_) +_d_|
|_cos_(_x_)|_sin_(_x_) +_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

15/ 24

## INTEGRATION - DEFINITE INTEGRATION

- To find the **area under a curve** we have to perform

**definite integration** between limits.

- This means that we calculate the integral (as in the table above) then evaluate the integral for two values of _x_ , and calculate the difference.

- Let’s find the area under the curve for _y_ = _x_<sup>2</sup> between _x_ = 1 and _x_ = 2:

|**Derivative** <sup>_dy_</sup><br>_dx_|**Integral** _y_<br>|
|---|---|
|0|_d_|
|constant|_constant × x_+_d_<br>|
|_x_<br>_x_<sup>_n_</sup><br>_e_<sup>_x_</sup><br>|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup><br>_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_e_<sup>_x_ </sup>+_d_<br>|
|_ke_<sup>_kx_</sup><br>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_<br>|_ln_(_x_) +_d_<br>|
|_cos_(_x_)|_sin_(_x_) +_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

- Where do you think the constant has gone?

16/ 24

## INTEGRATION - COMMON LAWS

### ▶ What happens when we have a sum of functions?

<!-- Start of picture text -->
dy<br>dx = 2 x  +  ex<br>y  =  x 2 +  e x<br><!-- End of picture text -->

- Well luckily, the integral of the sum is the sum of the integral!

- This means we can just integrate each term individually

- We’ll see what happens when we have more complicated combinations of functions soon.

<!-- Start of picture text -->
Derivative d dx y Integral y<br>0 d<br>constant constant × x  +  d<br>x 2<br>x 2 +  d<br>x n +1<br>x n n +1 +  d<br>e x e x +  d<br>ke kx e kx +  d<br>1 x ln ( x ) +  d<br>cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

17/ 24

SOLVING ORDINARY DIFFERENTIAL EQUATIONS (ODES)

- Science is built on solving Ordinary Differential Equations (ODEs).

- Important in all areas of science, and you have already been playing with them! If we have a differential equation with respect to 1 variable, we have an ODE. Some "famous" equations:

- You may also come across reference to "types" of ODEs in textbooks. These are various forms of an ODE that require certain approaches to solve them.

- We don’t dive into them here, but include: Homogeneous, Cauchy-Euler, Harmonic Oscillators.

18/ 24

## SOLVING ORDINARY DIFFERENTIAL EQUATIONS (ODES)

- You may also come across reference to "types" of ODEs in textbooks. These are various forms of an ODE that require certain approaches to solve them.

- We don’t dive into them here, but include: Homogeneous, Cauchy-Euler, Harmonic Oscillators.

- To predict values or properties in the past or future, we can integrate ODEs either without limits, or between specific limits.

- The radioactive decay and hydrostatic equation have the same algebraic formulation. Why is

   - this?

19/ 24

## EXAMPLE: RADIOACTIVE DECAY

▶ The equation describing radioactive decay is:

_dN dt_<sup>=</sup><sup>_−λN_</sup> where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay rate.

▶ This is a differential equation, and it has solution:

where _N_ 0 is the total number of nuclei in the sample at _t_ = 0.

- To prove that this is the solution, we integrate using a technique called **separation of variables** .

20/ 24

## EXAMPLE: RADIOACTIVE DECAY

- We rearrange the decay equation so that all _N_ ’s are on one side and all _t_ ’s are on the other and then integrate both sides:

<!-- Start of picture text -->
dN<br>dt =  −λN<br>▶ We first divide both sides by  N<br>1 dN<br>N dt =  −λ<br>▶ Then multiply both sides by  dt<br>1<br>N dN =  −λdt<br>▶ Then integrate both sides<br>1<br>� N dN =  −λ � dt<br><!-- End of picture text -->

21/ 24

## EXAMPLE: RADIOACTIVE DECAY

▶ The integral � _x_ <u>1</u><sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

ln _N_ = _−λt_ + _c_

and if we say at _t_ = 0, _N_ = _N_ 0 we get that _c_ = ln _N_ 0, we therefore obtain

_N_ = _N_ 0 exp ( _−λt_ )

as the solution to Newton’s radioactive equations.

|**Derivative** <sup>_dy_</sup><br>_dx_|**Integral** _y_|
|---|---|
|0|_d_|
|constant|_constant × x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup><br>|
|_x_<sup>_n_</sup><br>_e_<sup>_x_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_e_<sup>_x_ </sup>+_d_|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_) +_d_|
|_cos_(_x_)|_sin_(_x_) +_d_|
|_sin_(_x_)|_−cos_(_x_)+_d_|

22/ 24

## EXAMPLE: HYDROSTATIC EQUATION

- Air density depends on pressure, _P_ , and temperature, _T_ , through the ideal gas law, _ρ_ = _RαP T_<sup>:</sup>

where _g_ and _Rα_ are constants.

- This is a differential equation, and it has solution:

where _P_ 0 is the pressure at surface level.

- The assumption that the temperature is constant is not true as it usually decreases with altitude at about 10<sup>_◦_</sup> C km<sup>_−_1</sup> but for now let’s assume it is

- To prove that this is the solution of this formulation of Hydrostatic Equation, we can integrate using separation of variables.

23/ 24

## EXAMPLE: HYDROSTATIC EQUATION

- We rearrange the decay equation so that all _P_ ’s are on one side and all _z_ ’s are on the other and then integrate both sides:

- We first divide both sides by _P_

- Then multiply both sides by _dt_

▶ Then integrate both sides

- Completing this will be part of todays practical!

24/ 24
