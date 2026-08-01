---
title: "practical6_soln(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 6/practical6_soln(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 6 Practical - Introduction to Integration (Solutions)_

1/ 10

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

2/ 10

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of integration and explain its significance in calculus.

- (2) Identify and interpret common notation used in integration.

- (3) Describe the role of Ordinary Differential Equations (ODEs) in scientific modeling across

various disciplines.

- (4) Apply common laws of integration to solve theoretical and real-world problems.

3/ 10

## EXERCISE 1: COMMON LAWS OF INTEGRATION

<!-- Start of picture text -->
Derivative d dx y Integral y<br>▶ Evaluate the following indefinite integrals: 0 d<br>constant constant × x  +  d<br>� 6 x 5 − 18 x 2 + 7  dx x x 2 2 +  d<br>x n +1<br>x n n +1 +  d<br>10 w 4 + 9 w 3 + 7 w dw e x e x +  d<br>�<br>ke kx e kx +  d<br>▶ You can verify your answer by differentiating and 1 x ln ( x ) +  d<br>making sure that the result is the same as the integrand! cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

4/ 10

## EXERCISE 1: COMMON LAWS OF INTEGRATION

|▶Evaluating the frst integral:<br>�<br>6_x_<sup>5</sup> _−_18_x_<sup>2 </sup>+7_dx_= <sup>6</sup><br>6<sup>_x_6</sup><sup>_−_18</sup><br>3 <sup>_x_3 + 7</sup><br>1<sup>_x_ +</sup><sup>_d_</sup><br>=_x_<sup>6</sup> _−_6_x_<sup>3 </sup>+7_x_+_d_|**Derivative** <sup>_dy_</sup><br>_dx_<br>0<br>constant<br>_x_|**Integral** _y_<br>_d_<br>_constant × x_+_d_<br>_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup><br>|
|---|---|---|
|▶Evaluating the second integral:<br>|_x_<sup>_n_</sup><br>_e_<sup>_x_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_e_<sup>_x_ </sup>+_d_|
|�<br>10_w_<sup>4 </sup>+9_w_<sup>3 </sup>+7_w dw_= <sup>10</sup><br>5 <sup>_w_5</sup><sup>_−_9</sup><br>4<sup>_w_4 + 7</sup><br>2<sup>_w_2 +</sup><sup>_d_</sup><br>=2_w_<sup>5</sup> _−_<sup>9</sup><br>4<sup>_w_4 +</sup> <sup>7</sup><br>2<sup>_w_2 +</sup><sup>_d_</sup>|_ke_<sup>_kx_</sup><br>1<br>_x_<br>_cos_(_x_)<br>_sin_(_x_)|_e_<sup>_kx_ </sup>+_d_<br>_ln_(_x_) +_d_<br>_sin_(_x_) +_d_<br>_−cos_(_x_)+_d_|

- Don’t forget the constants in indefinite integrals!

5/ 10

## EXERCISE 2: DEFINITE INTEGRATION

- A gas leaks from a container according to the following ordinary differential equation:

_dG dt_<sup>= 390</sup><sup>_t_0</sup><sup>_._4</sup>

where _t_ is time (in minutes) and _G_ is in litres per minute.

- Calculate the volume of gas that has been released between 1 and 3 minutes.

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

6/ 10

## SOLUTION 2: DEFINITE INTEGRATION

▶ As we want to calculate the volume of gas that has been released between 1 and 3 minutes, we integrate<sup>_<u>dG</u>_</sup> _dt_ between 1 and 3:

<!-- Start of picture text -->
3 t 1 . 4 3<br>390 t 0 . 4 = 390<br>�1 � 1 . 4 �1<br>31 . 4<br>= 390<br>� 1 . 4 − 1 1 1 . . 4 4 �<br>= 390 (3 . 325  − 0 . 714) = 1018 . 328<br><!-- End of picture text -->

- So approximately 1018.328 litres were lost between 1 and 3 minutes.

<!-- Start of picture text -->
Derivative d dx y Integral y<br>0 d<br>constant constant × x  +  d<br>x 2<br>x 2 +  d<br>x n +1<br>x n n +1 +  d<br>e x e x +  d<br>ke kx e kx +  d<br>1 x ln ( x ) +  d<br>cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

7/ 10

## EXERCISE 3: HYDROSTATIC EQUATION

▶ In lectures, we aimed to solve the Hydrostatic Equation, which states that air density depends _<u>P</u>_ on pressure, _P_ , and temperature, _T_ , through the ideal gas law, _ρ_ = _RαT_<sup>:</sup>

where _g_ and _Rα_ are constants.

- We used separation of variables to get the following integrals:

- Complete the integration to show that:

is a solution to the Hydrostatic Equation. Here, _P_ 0 is the pressure at surface level.

8/ 10

## SOLUTION 3: HYDROSTATIC EQUATION

▶ The integral � _x_ <u>1</u><sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

<!-- Start of picture text -->
ln  P = − RαgT z  +  c Derivative 0 d dx y Integ d ral y<br>constant constant × x  +  d<br> = 0, 0,  P  =  P 0 we get that  c  = ln( P 0), we), we, we x x 2 2 +  d<br>x n +1<br>x n n +1 +  d<br>== exp P 0 exp� − � R−αgRTαg z T  + ln( z � P 0) � cossinkee 1 x (( xkx xx )) −sinlncosee ( kx ( x xx (+) ++ x ) +)  d d  +  d d d<br><!-- End of picture text -->

and if we say at _t_ = 0, 0, _P_ = _P_ 0 we get that _c_ = ln( _P_ 0), we), we, we therefore obtain

as the solution to Hydrostatic Equation.

9/ 10

## INTENDED LEARNING OUTCOMES

- (1) Describe the concept of integration and explain its significance in calculus.

- (2) Identify and interpret common notation used in integration.

- (3) Describe the role of Ordinary Differential Equations (ODEs) in scientific modeling across

various disciplines.

- (4) Apply common laws of integration to solve theoretical and real-world problems.

10/ 10
