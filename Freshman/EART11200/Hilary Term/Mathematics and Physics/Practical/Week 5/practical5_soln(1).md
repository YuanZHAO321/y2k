---
title: "practical5_soln(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 5/practical5_soln(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 5 Practical - Second-order Derivatives and Root Finding (Solutions)_

1/ 13

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

2/ 13

## INTENDED LEARNING OUTCOMES

(1) Explain the concept and significance of second-order derivatives in the analysis of functions.

(2) Compute second-order derivatives of functions to classify stationary values as maxima, minima, or saddle points in optimisation problems.

- (3) Describe steady-state systems in physical and mathematical modeling.

- (4) Apply Newton’s Method to find the roots of complex functions in numerical problem-solving.

3/ 13

## EXERCISE 1: SECOND-ORDER DERIVATIVES

||**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
|In the last practical, we found stationary values for the|constant|0|
|following function:|_x_|1|
|<sup>3</sup>|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_f_(_x_) = <sup>_x_</sup><br>3 <sup>+</sup><sup>_x_2</sup><sup>_−_15</sup><sup>_x_ + 1</sup>|_e_<sup>_x_</sup><br>_e_<sup>_kx_</sup>|_e_<sup>_x_</sup><br>_ke_<sup>_kx_</sup>|
|which were_x_=_−_5 and_x_=3.|_e_<sup>_f_(</sup><sup>_x_)</sup>|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup>|
|Use the second-order derivative to confrm if they are|_ln_(_x_)<br>_sin_(_x_)|1<br>_x_<br>_cos_(_x_)|
|maxima, minima or saddle points.|_cos_(_x_)|_−sin_(_x_)|

- In the last practical, we found stationary values for the following function:

- Use the second-order derivative to confirm if they are maxima, minima or saddle points.

4/ 13

## SOLUTION 1: SECOND-ORDER DERIVATIVES

<!-- Start of picture text -->
▶ For the following functions<br>f ( x ) = x 3 3 +  x 2  − 15 x  + 1<br>the first- and second-order derivatives are:<br>dy d 2 y<br>dx =  x 2 + 2 x − 15 dx 2 = 2 x  + 2<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

5/ 13

## SOLUTION 1: SECOND-ORDER DERIVATIVES

▶ To confirm whether they are maxima or minima, we evaluate the second-order derivative at the stationary values:

<!-- Start of picture text -->
evaluate the second-order derivative at the stationary Function constant y  = f ( x ) Derivative 0 dy dx<br>values: x 1<br>x n nx n− 1<br>d 2 y<br>dx 2 (3) = 2  ×  3 + 2 = 8 e x e x<br>e kx ke kx<br>d 2 y e f ( x ) df<br>dx 2 ( − 5) = 2  ×  ( − 5) + 2 =  − 8 ln ( x ) dx e 1 x f ( x )<br>▶ As dx d 22 y (3)  >  0 then  x  = 3 is a minimum. cossin (( xx )) −cossin (( xx ))<br>▶ As d dx 2 y 2 ( − 5)  <  0 then  x  =  − 5 is a maximum.<br><!-- End of picture text -->

6/ 13

## EXERCISE 2: STEADY STATE

▶ An industrial incinerator produces a steady output of particulate matter and has a concentration of _C_ 0 = 1mg/m<sup>3</sup> of air at the chimney.

- At 1km away from the incinerator plant the concentration is

_C_ 1 = 0 _._ 11mg/m<sup>3</sup> .

- The concentration as a function of distance from the incinerator

is given by:

_C_ ( _x_ ) = _C_ 0 +<sup><u>(</u></sup><sup>_C_1</sup><sup>_−C_0)</sup> _x_ 1000

- Is this system in steady state?

7/ 13

## SOLUTION 2: STEADY STATE

- To deduce if the system is in steady state, we look at the

first-order derivative:

_C_ ( _x_ ) = _C_ 0 +<sup><u>(</u></sup><sup>_C_1</sup><sup>_−C_0)</sup> _x_ 1000

_dC_<sup>_C_1</sup><sup>_−C_0</sup> _dx_<sup>=</sup> 1000

- We see that the first-order derivative is constant which means the second-order derivative is zero:

_d_<sup>2</sup> _C dx_<sup>2= 0</sup>

- So the system is in steady state.

8/ 13

## EXERCISE 3: NEWTON’S METHOD FOR ROOT FINDING

- Find a root of the following equation:

_f_ ( _x_ ) = _x_<sup>2</sup> + 2 _x −_ 10

using Newtons Method:

_xn_ +1 = _xn − f_<sup>_<u>f′</u>_</sup><sup><u>(</u></sup> (<sup>_x_</sup> _x_<sup>_n_</sup> _n_<sup><u>)</u></sup> )

- Use an initial guess of _x_ 0 = 4 and give the answer to 3 decimal places (i.e. there is no more

change in the fourth decimal place).

9/ 13

## SOLUTION 3: NEWTON’S METHOD FOR ROOT FINDING

### ▶ We see that

### ▶ Using Newton’s Method with an initial guess of _x_ 0 = 4:

- Continue using Newton’s Method:

10/ 13

## SOLUTION 3: NEWTON’S METHOD FOR ROOT FINDING

- Continue using Newton’s Method:

- Continue using Newton’s Method:

- You can see that at the fourth iteration, thus a value for _x_ 4, our value only changes at an accuracy greater than 4 decimal places so we can stop.

- Therefore, we can see the function, _f_ ( _x_ ), has a root at 2.31662

11/ 13

## SOLUTION 3: NEWTON’S METHOD FOR ROOT FINDING

- Luckily we can verify this that 2.31662 is a root of:

- Use the quadratic formula:

which means there are roots at _x_ = 2 _._ 31662 and _x_ = _−_ 4 _._ 31662.

- Newton’s Method for Root Finding did find the root correctly!

12/ 13

## INTENDED LEARNING OUTCOMES

(1) Explain the concept and significance of second-order derivatives in the analysis of functions.

(2) Compute second-order derivatives of functions to classify stationary values as maxima, minima, or saddle points in optimisation problems.

- (3) Describe steady-state systems in physical and mathematical modeling.

- (4) Apply Newton’s Method to find the roots of complex functions in numerical problem-solving.

13/ 13
