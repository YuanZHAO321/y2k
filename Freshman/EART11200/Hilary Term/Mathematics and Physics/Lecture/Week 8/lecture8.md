---
title: "lecture8"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 8/lecture8.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 8 Lecture - Integration By Substitution_

1/ 21

## LAST WEEK...

- We can reverse some common derivatives, we arrive at the following functions.

- The more you practice these procedures, the easier it will become to apply them without looking them up.

- Use your math’s survival pack when needed!

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

2/ 21

## LAST WEEK...

- In this course, we focus on Newton’s Second Law, which is given by the following equation:

where _F_ is the net force acting on a body that has a mass _m_ and therefore acceleration _a_ .

- This states acceleration of an object depends on the mass of the object and the amount of force applied.

- Newton’s second law can therefore be expressed as an ordinary differential equation:

3/ 21

## LAST WEEK...

- By examining the forces acting on objects we can formulate ODEs:

▶ Using separation of variables, we integrate these ODEs to calculate behaviours of our systems.

- Frictional forces will depend on the object, the system, its mass and how quickly it is moving.

4/ 21

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

5/ 21

## INTENDED LEARNING OUTCOMES

- (1) Explain the concept of integration by substitution and its relationship to the chain rule in differentiation.

- (2) Apply integration by substitution on indefinite integrals to solve theoretical and real-world problems.

- (3) Apply integration by substitution on definite integrals to solve theoretical and real-world

   - problems.

6/ 21

## INTEGRATION: COMMON LAWS

- In Week 6, we introduced rules that allow us to directly integrate certain basic functions if we can recognize their forms.

- There may be a need to rearrange the equation, often by using techniques like separation of variables (e.g., rearranging _N_ and _t_ ).

- Like differentiation, the integral of a sum is equal to the sum of the integrals of the individual functions.

_dy_<sup>=</sup><sup>_⇒y_=</sup> _u_ ( _x_ ) _dx_ + _v_ ( _x_ ) _dx dx_<sup>=</sup><sup>_u_(</sup><sup>_x_) +</sup><sup>_v_(</sup><sup>_x_)</sup> � �

<!-- Start of picture text -->
Derivative d dx y Integral y<br>0 d<br>constant constant × x  +  d<br>x 2<br>x 2 +  d<br>x n +1<br>x n n +1 +  d<br>e x e x +  d<br>ke kx e kx +  d<br>1 x ln ( x ) +  d<br>cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

7/ 21

## INTEGRATION: COMMON LAWS

<!-- Start of picture text -->
▶ In some cases, we cant directly integrate by using these<br>rules, as we are faced with more complicated Derivative d dx y Integral y<br>combinations of functions such as  functions of 0 d<br>functions . constant constant × x  +  d<br>x 2<br>▶ For example, what happens if we want to integrate x x n 2 +1+  d<br>x n n +1 +  d<br>dy e x e x +  d<br>y  = (3 x  + 2) 4 dx<br>� dx = � ke kx e kx +  d<br>▶ This is where  integration by substitution  comes in. cos 1 x ( x ) sinln (( xx ) +) +  d d<br>▶ Integration by substitution is essentially the reverse sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

- Integration by substitution is essentially the reverse process of the chain rule in differentiation.

8/ 21

## THE CHAIN RULE

- Use the **Chain Rule** to differentiate:

_f_ ( _x_ ) = sin(3 _x_ + 1)

- **Step 1** : Split the function and substitute

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

_f_ ( _x_ ) = 3 cos(3 _x_ + 1)

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

9/ 21

## INTEGRATION BY SUBSTITUTION

- Let’s return to the example where we want to evaluate

- At first glance, it may appear that this resembles the derivative of some function, allowing us to integrate directly.

- What if we replace the expression in the brackets with another variable such that we can integrate using the rules we already know?

_y_ = _u_<sup>4</sup> _dx_ �

10/ 21

## INTEGRATION BY SUBSTITUTION

- Well, if we are integrating with respect to a new variable _u_ , we need to get rid of all instances of

_x_ .

- Since _dx_ relates to _x_ , we need to rewrite it in terms of _u_ .

- This step ensures that the integral is entirely in terms of the new variable.

- When the integral contains a factor like _ax_ + _b_ , substituting _u_ = _ax_ + _b_ often simplifies the problem.

- Let’s show how integration by substitution works in full.

11/ 21

## INTEGRATION BY SUBSTITUTION

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

12/ 21

## INTEGRATION BY SUBSTITUTION

### 5. Get an expression for _dx_ :

6. Make the substitution in the original integral

### 7. Integrate as usual:

8. Substitute the original expression back in to get the final expression:

13/ 21

## EXAMPLE: INTEGRATION BY SUBSTITUTION

▶ Lets evaluate the integral

- Let’s use _u_ = 3 _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

- Use these to make the substitution:

14/ 21

## EXAMPLE: INTEGRATION BY SUBSTITUTION

- Now we can evaluate using the basic laws of

integration:

1 3 � cos ( _u_ ) _du_ =<sup>1</sup> 3<sup>sin (</sup><sup>_u_) +</sup><sup>_c_</sup>

- Substituting _u_ = 3 _x_ + 4 back in gives us:

_y_ = 3<sup>1sin (3</sup><sup>_x_+ 4) +</sup><sup>_c_</sup>

- You can differentiate using the chain rule to verify that this works.

<!-- Start of picture text -->
Derivative d dx y Integral y<br>0 d<br>constant constant × x  +  d<br>x 2<br>x 2 +  d<br>x n +1<br>x n n +1 +  d<br>e x e x +  d<br>ke kx e kx +  d<br>1 x ln ( x ) +  d<br>cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

15/ 21

## INTEGRATION BY SUBSTITUTION

- This is integration by substitution for **indefinite integrals** .

- In many cases, we want to find the **area under a curve** so the integral has limits:

- We need to perform **definite integration** in this case.

- We calculate the integral (using integration by substitution) then evaluate the integral using new limits under the substitution.

- Let’s show how definite integration by substitution works in full.

16/ 21

## INTEGRATION BY SUBSTITUTION

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

17/ 21

## INTEGRATION BY SUBSTITUTION

5. Get an expression for _dx_ :

6. Find the new limits of the integral:

When _x_ = _−_ 1 _, u_ = 3 _×_ ( _−_ 1) + 2 = _−_ 1

When _x_ = 1 _, u_ = 3 _×_ 1 + 2 = 5

7. Make the substitution in the original integral

8. Integrate as usual:

18/ 21

## EXAMPLE: INTEGRATION BY SUBSTITUTION

▶ Lets evaluate the integral

- Let’s use _u_ = _x_ + 10 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

_u_ = _x_ + 10 = _⇒ x_ = _u −_ 10 = _⇒ du_<sup>_dx_= 1=</sup><sup>_⇒dx_=</sup><sup>_du_</sup> When _x_ = _−_ 9 _, u_ = _−_ 9 + 10 = 1 When _x_ = 1 _, u_ = 1 + 10 = 11

- Find the new limits:

19/ 21

## EXAMPLE: INTEGRATION BY SUBSTITUTION

### ▶ Use these to make the substitution:

<!-- Start of picture text -->
1 1 11 1<br>= ⇒<br>� − 9 x  + 10 dx �1 u du<br>▶ Now we can evaluate using the basic laws of<br>integration:<br><!-- End of picture text -->

<!-- Start of picture text -->
11 1<br>= [ln( u )] 11 1<br>�1 u du<br>= ln(11)  − ln(1)<br>= ln(11) = 2 . 398<br><!-- End of picture text -->

<!-- Start of picture text -->
Derivative d dx y Integral y<br>0 d<br>constant constant × x  +  d<br>x 2<br>x 2 +  d<br>x n +1<br>x n n +1 +  d<br>e x e x +  d<br>ke kx e kx +  d<br>1 x ln ( x ) +  d<br>cos ( x ) sin ( x ) +  d<br>sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

20/ 21

## EXAMPLE: INTEGRATION BY SUBSTITUTION

- So we see that we can integrate more complicated functions using substitution.

- We substitute so that the integration becomes simple so we can use our table of integrals.

- Why does this matter? If the physics of the system requires another formulation, a substitution might be needed.

- For example, the Hydrostatic Equation, but with Temperature varying with altitude:

<!-- Start of picture text -->
dP P 1 1<br>dz =  − Ra � Tsurface − 0 . 01 z � g = ⇒ � P dP  =  − R g a � Tsurface − 0 . 01 z dz<br><!-- End of picture text -->

21/ 21
