---
title: "practical2_soln(5)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 2/practical2_soln(5).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 2 Practical - Introduction to Differentiation (Solutions)_

1/ 11

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

2/ 11

## INTENDED LEARNING OUTCOMES

(1) Describe the concept of differentiation and explain its significance in calculus.

(2) Identify and interpret common notation used in differentiation.

- (3) Apply common laws of differentiation to solve theoretical and real-world problems.

3/ 11

## EXERCISE 1: REARRANGING EXPRESSIONS

||**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
||constant|0|
|▶Differentiate the following functions with respect to_x_:<br>|_x_<br>_x_<sup>_n_</sup>|1<br>_nx_<sup>_n−_1</sup>|
|(a) _y_=4_x_<sup>3 </sup>+2_x_<sup>2 </sup>+5_x_+6|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|(b) _f_(_x_) = <sup>_√_</sup><br>_x_|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|(c) _g_(_x_) =4_x_<sup>4 </sup>+_e_<sup>_x _</sup>_−_cos(_x_)<br>(d) _h_(_x_) =_e_<sup>5</sup><sup>_x_+4</sup>|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_|
||_sin_(_x_)<br>_cos_(_x_)|_cos_(_x_)<br>_−sin_(_x_)|

4/ 11

## SOLUTION 1: REARRANGING EXPRESSIONS

||**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
||constant|0|
|▶Differentiate the following functions with respect to_x_:<br>(a)<br>_dy_<br>_dx_ <sup>= 12</sup><sup>_x_2 + 4</sup><sup>_x_ + 5</sup><br>|_x_<br>_x_<sup>_n_</sup><br>_e_<sup>_x_</sup>|1<br>_nx_<sup>_n−_1</sup><br>_e_<sup>_x_</sup>|
|(b)<br>_df_<br>_dx_ <sup>=</sup><br>1<br>2<sup>_~~√~~_</sup><br>_x_|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|(c)<br>_dg_<br>_dx_ <sup>= 16</sup><sup>_x_3 +</sup><sup>_ex_ + sin(</sup><sup>_x_)</sup><br>|_e_<sup>_f_(</sup><sup>_x_)</sup>|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup>|
|(d)<br>_dh_<br>_dx_ <sup>= 5</sup><sup>_e_5</sup><sup>_x_+4</sup>|_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

5/ 11

## EXERCISE 2: GAS LEAK

▶ Imagine we are studying the volume of helium gas in a tank, which is leaking, over time. If we say that the volume of water in the system can be described in time _t_ as: _V_ ( _t_ ) = _V_ 0 _−_<sup>_t_</sup> 60 where _V_ 0 = 1 is the volume of gas (in _m_<sup>3</sup> ) and 0 _< t <_ 60 (in mins).

▶ What is the rate of the leak?

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

▶ Do you think the rate is sensible?

6/ 11

## SOLUTION 2: GAS LEAK

▶ To obtain the rate of the leak we differentiate with respect to time _t_ : _dV dt_<sup>=</sup><sup>_−_</sup> 60<sup>1</sup>

which is constant.

- It is unlikely that the rate of the gas leak is constant.

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

7/ 11

## EXERCISE 2: GAS LEAK

▶ In reality the gas would leak at a non-constant rate. If we say that the volume of gas in the tank can be described as:

_V_ ( _t_ ) = _V_ 0 exp _−_<sup>_t_</sup> � 6 �

   - where _V_ 0 = 1 is the volume of gas (in _m_<sup>3</sup> ) and 0 _< t <_ 60 (in mins).

- What is the rate of the leak at 6 minutes?

▶ Compare this to a gradient calculated numerically using the central difference method with a time step of 0.1 minutes either side of 6 minutes.

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)|
|_cos_(_x_)|_−sin_(_x_)|

8/ 11

## SOLUTION 2: GAS LEAK

- To obtain the rate of the leak we differentiate with respect to time _t_ :

<!-- Start of picture text -->
dV<br>− t<br>dt =  − 6 1 exp � 6 �<br>▶ At  t  = 6 the (analytical) rate of the leak is:<br>dV<br>dt (6) =  − 6 1 exp ( − 1) = 0 . 061313<br><!-- End of picture text -->

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

9/ 11

## SOLUTION 2: GAS LEAK

<!-- Start of picture text -->
▶ At  t  = 6 the (analytical) rate of the leak is:<br>∆ V V (6 . 1)  − V (5 . 9)<br>∆ t (6) = 6 . 1  − 5 . 9<br>= exp( − 6 . 1 / 6)  − exp( − 5 . 9 / 6)<br>0 . 2<br>=  − 0 . 061316<br>▶ It is fairly accurate with a small step-size:<br>Error = 100  × − 0 . 061313 + 0 . 061316<br>− 0 . 061313<br>= 0 . 004%<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

10/ 11

## INTENDED LEARNING OUTCOMES

(1) Describe the concept of differentiation and explain its significance in calculus.

(2) Identify and interpret common notation used in differentiation.

(3) Apply common laws of differentiation to solve theoretical and real-world problems.

11/ 11
