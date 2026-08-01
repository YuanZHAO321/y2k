---
title: "lecture3(2)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 3/lecture3(2).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 3 Lecture - Differentiating Combinations of Functions_

1/ 15

LAST WEEK...

- For a function, _y_ = _f_ ( _x_ ), that describes some process we are interested in, in one dimension, the derivative:

- It is interpreted as the rate of change of ‘y’ with respect to ‘x’. Lets imagine we are observing this change over a discrete interval, such that we could write this as an approximation:

_dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

2/ 15

## LAST WEEK...

- We can apply similar procedures to other common functions and start populating a list of rules.

- The more you practice these procedures, the easier it will become to apply them without looking them up.

- Use your math’s survival pack when needed!

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

3/ 15

## LAST WEEK...

- What happens when we have a sum of functions?

- Well luckily, the derivative of the sum is the sum of the derivatives!

- This means we can just differentiate each term individually

<!-- Start of picture text -->
dy<br>dx = 5 +  ex<br><!-- End of picture text -->

- We’ll see next week what happens when we have more complicated combinations of functions.

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

4/ 15

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

5/ 15

## INTENDED LEARNING OUTCOMES

- (1) Apply the chain rule to differentiate composite functions in theoretical and real-world applications.

- (2) Apply the product rule to differentiate products of functions in theoretical and real-world applications.

- (3) Apply the quotient rule to differentiate products of functions in theoretical and real-world

applications.

6/ 15

## EXAMPLE: HYDROSTATIC EQUATION

▶ Air density depends on pressure, _P_ , and temperature, _<u>P</u> T_ , through the ideal gas law, _ρ_ = _RαT_<sup>:</sup>

<!-- Start of picture text -->
dP g Function y  = f ( x ) Derivative dy dx<br>dz =  − RαT P constant 0<br>x 1<br>where  g  and  Rα are constants. x n nx n− 1<br>▶ This is a differential equation, and it has solution: e x e x<br>e kx ke kx<br>P ( z ) =  P 0 exp − g e f ( x ) dxdf ef ( x )<br>� RαT z � ln ( x ) 1 x<br>where  P 0 is the pressure at surface level cossin (( xx )) −cossin (( xx ))<br>▶ We can use differentiation to show that this is true<br>dP − g =  − P<br>dz =  − R g α P T 0 exp � RαT z � RαT P<br><!-- End of picture text -->

7/ 15

## THE CHAIN RULE

▶ So far, functions have matched one of the rules listed on the right hand side:

<!-- Start of picture text -->
f ( x ) = sin( x ) dxdf = cos( x ) Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>( x ) = sin(3 x  + 1) dxdf =??? lne f ( ( x x ) ) dxdf e 1 x f ( x )<br>sin ( x ) cos ( x )<br> f ( g ( x )), we, we cos ( x ) −sin ( x )<br><!-- End of picture text -->

- However, there are instances where no level of re-arranging will get to a form we can use.

▶ What happens when we get the following?

- When we have functions with functions _f_ ( _g_ ( _x_ )), we, we can use a nice mathematical trick to help here:

_df_<sup>_dfdfdgdfdg_</sup> _dx_<sup>=</sup> _dx_<sup>_×_1 =</sup> _dx_<sup>_×_</sup> _dg_<sup>=</sup> _dg_<sup>_×_</sup> _dx_

8/ 15

## THE CHAIN RULE

▶ This is known as the **Chain Rule** .

- Let’s see it in action:

- **Step 1** : Split the function and substitute

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

_df dx_<sup>= 3 cos(3</sup><sup>_x_+ 1)</sup>

<!-- Start of picture text -->
The Chain Rule<br>df df dg<br>dx = dg × dx<br><!-- End of picture text -->

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

9/ 15

## THE PRODUCT RULE

### ▶ What happens when we get the following?

_df f_ ( _x_ ) = _x_ exp(3 _x_ ) _dx_<sup>=???</sup>

### ▶ Let’s think of a simpler example:

### ▶ Can we just multiply the derivatives?

_u_ ( _x_ ) = _x_<sup>3</sup> = _⇒_<sup>_du_</sup> _dx_<sup>= 3</sup><sup>_x_2</sup> _v_ ( _x_ ) = _x_<sup>6</sup> = _⇒_<sup>_du_</sup> _dx_<sup>= 6</sup><sup>_x_5</sup> _df_<sup>_dudv_</sup> _dx_<sup>=</sup> _dx_<sup>_×_</sup> _dx_<sup>= (3</sup><sup>_x_2)(6</sup><sup>_x_5) = 18</sup><sup>_x_7</sup>

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

10/ 15

## THE PRODUCT RULE

- This is incorrect as from the table of common

|w that|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
|_df_<br>_dx_ <sup>= 9</sup><sup>_x_8</sup>|constant<br>_x_<br>_x_<sup>_n_</sup>|0<br>1<br>_nx_<sup>_n−_1</sup>|
|functions multiplied together,|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|<br>can use the**roduct rule**:|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|**p**|_e_<sup>_f_(</sup><sup>_x_)</sup>|_df_<br><sup>_ef_(</sup><sup>_x_)</sup>|
|_df_<br><sup>_dv_</sup><br><sup>_du_</sup>|_ln_(_x_)|_dx_<br>1<br>|
|_dx_ <sup>=</sup><sup>_u_</sup><br>_dx_ <sup>+</sup><sup>_v_</sup><br>_dx_|_sin_(_x_)|_x_<br>_cos_(_x_)|
|to increase the comlexit of the|_cos_(_x_)|_−sin_(_x_)|

differentials we know that

- When we have two functions multiplied together,

_f_ ( _x_ ) = _u_ ( _x_ ) _v_ ( _x_ ), we can use the **product rule** :

- This rule allows us to increase the complexity of the functions we study!

11/ 15

## THE PRODUCT RULE

▶ Let’s see it in action

_f_ ( _x_ ) = _x_ exp(3 _x_ )

- **Step 1** : Split the function:

_u_ ( _x_ ) = _x v_ ( _x_ ) = exp(3 _x_ )

- **Step 2** : Differentiate:

_du dv dx_<sup>= 1</sup> _dx_<sup>= 3 exp(3</sup><sup>_x_)</sup> ▶ **Step 3** : Apply the product rule and substitute back in: _df dx_<sup>= 3</sup><sup>_x_exp(3</sup><sup>_x_) + exp(3</sup><sup>_x_) = (3</sup><sup>_x_+ 1) exp(3</sup><sup>_x_)</sup>

<!-- Start of picture text -->
The Product Rule<br>df dv<br>dx =  u dx +  vdu dx<br><!-- End of picture text -->

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup><br>_e_<sup>_kx_</sup>|_e_<sup>_x_</sup><br>_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)|
|_cos_(_x_)|_−sin_(_x_)|

12/ 15

## THE QUOTIENT RULE

### ▶ What happens when we get the following?

▶ Let’s think of a simpler example:

### ▶ Can we just divide the derivatives?

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

13/ 15

## THE QUOTIENT RULE

- This is incorrect as from the table of common differentials we know that

|w that|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
|_df_<br>_dx_ <sup>=</sup><sup>_−_3</sup><sup>_x−_4</sup>|constant<br>_x_<br>_x_<sup>_n_</sup>|0<br>1<br>_nx_<sup>_n−_1</sup>|
|ctions dividing another function,|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|<sup>use the</sup><sup>**quotient rule**:</sup>|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|<br>_df_<br> <sup>_v du_</sup><br>_dx_ <sup>_−u dv_</sup><br>_dx_|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_|
|_dx_ <sup>=</sup> <br>_v_<sup>2</sup>|_sin_(_x_)|_cos_(_x_)|
|i h li f h|_cos_(_x_)|_−sin_(_x_)|

- This rule allows us to increase the complexity of the functions we study!

14/ 15

## THE QUOTIENT RULE

- Let’s see it in action

_f_ ( _x_ ) =<sup>3</sup><sup>_x_+ 1</sup> 6 _x −_ 1

- **Step 1** : Split the function:

_u_ ( _x_ ) = 3 _x_ + 1 _v_ ( _x_ ) = 6 _x −_ 1

- **Step 2** : Differentiate:

_du dv dx_<sup>= 3</sup> _dx_<sup>= 6</sup> Apply the product rule and substitute back in: _dxdf_<sup>=3(6</sup><sup>_x −_</sup> (6<sup>1</sup> _x_<sup><u>)</u></sup><sup>_−_</sup> _−_<sup>6</sup> 1<sup><u>(</u></sup> )<sup>32</sup><sup>_x_+ 1)</sup> = _−_ (6 _x −_ 9 1)<sup>2</sup>

- **Step 3** : Apply the product rule and substitute back in:

<!-- Start of picture text -->
The Quotient Rule<br>df v du dx − u dv dx<br>dx = v 2<br><!-- End of picture text -->

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

15/ 15
