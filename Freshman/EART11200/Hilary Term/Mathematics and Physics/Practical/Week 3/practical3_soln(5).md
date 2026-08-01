---
title: "practical3_soln(5)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 3/practical3_soln(5).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 3 Practical - Differentiating Combinations of Functions (Solutions)_

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

- (1) Apply the chain rule to differentiate composite functions in theoretical and real-world applications.

- (2) Apply the product rule to differentiate products of functions in theoretical and real-world applications.

- (3) Apply the quotient rule to differentiate products of functions in theoretical and real-world

applications.

3/ 12

## EXERCISE 1: CHAIN RULE

- Use the chain rule to differentiate the following function:

_f_ ( _x_ ) = _−_ ln(cos( _x_ ))

<!-- Start of picture text -->
The Chain Rule<br>df df dg<br>dx = dg × dx<br><!-- End of picture text -->

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)|
|_cos_(_x_)|_−sin_(_x_)|

4/ 12

## SOLUTION 1: CHAIN RULE

- **Step 1** : Split the function and substitute

_f_ ( _g_ ) = _−_ ln( _g_ ) _g_ ( _x_ ) = cos( _x_ )

<!-- Start of picture text -->
The Chain Rule<br>df df dg<br>dx = dg × dx<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>df dg x 1<br>dg =  − 1 g dx =  − sin( x ) x n nx n− 1<br>e x e x<br>Apply the product rule and substitute back in: e kx ke kx<br>dxdf = cos( sin( x x ) ) = tan( x ) lne f ( ( x x ) ) dxdf e 1 x f ( x )<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

5/ 12

## EXERCISE 2: PRODUCT RULE

- Use the product rule to differentiate the following function:

_g_ ( _x_ ) = sin( _x_ ) exp( _x_ )

<!-- Start of picture text -->
The Product Rule<br>df dv<br>dx =  u dx +  vdu dx<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

6/ 12

## SOLUTION 2: PRODUCT RULE

- **Step 1** : Split the function and substitute

_u_ ( _x_ ) = sin( _x_ ) _v_ ( _x_ ) = exp( _x_ )

<!-- Start of picture text -->
The Product Rule<br>df dv<br>dx =  u dx +  vdu dx<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>du dv<br>x 1<br>dx = cos( x ) dx = exp( x )<br>x n nx n− 1<br>Apply the product rule and substitute back in: e x e x<br>e kx ke kx<br>dg e f ( x ) df<br>dx = cos( x ) exp( x ) + exp( x ) sin( x ) ln ( x ) dx e 1 x f ( x )<br>= exp( x )(cos( x ) + sin( x )) sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

7/ 12

## EXERCISE 3: QUOTIENT RULE

- Use the quotient rule to differentiate the following function:

_h_ ( _x_ ) =<sup>_x −x_2</sup> 1 + 8 _x_<sup>2</sup>

<!-- Start of picture text -->
The Quotient Rule<br>df v du dx − u dv dx<br>dx = v 2<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

8/ 12

## SOLUTION 3: QUOTIENT RULE

<!-- Start of picture text -->
The Quotient Rule<br>u ( x ) =  x − x 2 v ( x ) = 1 + 8 x 2 df v du dx − u dv dx<br>dx = v 2<br><!-- End of picture text -->

- **Step 1** : Split the function:

### ▶ **Step 2** : Differentiate:

<!-- Start of picture text -->
du dv<br>dx = 1  − 2 x dx = 16 x<br><!-- End of picture text -->

- **Step 3** : Apply the product rule and substitute back in:

<!-- Start of picture text -->
dh (1 + 8 x 2)(1  − 2 x )  − 16 x ( x − x 2)<br>dx = (1 + 8 x 2 ) 2<br>= 1  − 2 x  + 8 x 2  − 16 x 3  − 16 x 3 + 16 x 3<br>(1 + 8 x 2 ) 2<br>= 1  − 2 x − 8 x 2<br>(1 + 8 x 2 ) 2<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

9/ 12

## PROPERTIES OF DERIVATIVES

- To finish up, we can use derivatives to tell us something about the function.

- We know that if

_dy dx_<sup>_>_0=</sup><sup>_⇒_</sup> function is increasing _dy dx_<sup>_<_0=</sup><sup>_⇒_</sup> function is decreasing

- We can then deduce the if

_dy dx_<sup>= 0</sup>

then the function must be changing direction.

- We will come across the important property a zero derivative has soon.

10/ 12

## PROPERTIES OF DERIVATIVES

<!-- Start of picture text -->
0.1 h'(x) < 0 h'(x) > 0 h(x)<br>▶ For the function: 0.0 x = 1/4<br> h'(x) = 0<br>h ( x ) = x − x 2<br>1 + 8 x 2 x = −1/2<br>dh 1  − 2 x − 8 x 2 −0.1  h'(x) = 0<br>dx = (1 + 8 x 2 ) 2<br>−0.2 h'(x) < 0<br>−1.00 −0.75 −0.50 −0.25 0.00 0.25 0.50 0.75 1.00<br>x<br>y<br><!-- End of picture text -->

11/ 12

## INTENDED LEARNING OUTCOMES

- (1) Apply the chain rule to differentiate composite functions in theoretical and real-world applications.

- (2) Apply the product rule to differentiate products of functions in theoretical and real-world applications.

- (3) Apply the quotient rule to differentiate products of functions in theoretical and real-world

applications.

12/ 12
