---
title: "lecture2(4)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 2/lecture2(4).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 2 Lecture - Introduction to Differentiation_

1/ 21

## LAST WEEK...

- For a function, _y_ = _f_ ( _x_ ), that describes some process we are interested in, in one dimension, the derivative:

_f_<sup>_′_</sup> ( _x_ ) =<sup>_dy_</sup> _dx_

- It is interpreted as the rate of change of ‘y’ with respect to ‘x’.

- Lets imagine we are observing this change over a discrete interval, such that we could write

   - this as an approximation:

_dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

2/ 21

## LAST WEEK...

### ▶ Last week we looked at the quadratic function:

- We want the derivative at _x_ = 16.

- Assume, for now, no analytical function can be derived.

### ▶ **Euler’s Backward Method**

_dy_ = lim ∆ _<u>y yx − yx−</u>_ ∆ _x dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 ∆ _x_

3/ 21

## LAST WEEK...

### ▶ Last week we looked at the quadratic function:

- We want the derivative at _x_ = 16.

- Assume, for now, no analytical function can be derived.

### ▶ **Euler’s Forward Method**

_dy_ = lim ∆ _<u>y yx</u>_ +∆ _x −_ _<u>yx</u> dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 ∆ _x_

4/ 21

## LAST WEEK...

### ▶ Last week we looked at the quadratic function:

- We want the derivative at _x_ = 16.

- Assume, for now, no analytical function can be derived.

### ▶ **Central Differences Method**

_dy_ = lim ∆ _<u>y yx</u>_ +∆ _x −_ _<u>yx−</u>_ ∆ _x dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 2∆ _x_

5/ 21

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

6/ 21

## INTENDED LEARNING OUTCOMES

(1) Describe the concept of differentiation and explain its significance in calculus.

(2) Identify and interpret common notation used in differentiation.

- (3) Apply common laws of differentiation to solve theoretical and real-world problems.

7/ 21

## EXAMPLE: RADIOACTIVE DECAY

- The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay rate.

- It basically says that the change in the number of nuclei in time is proportional to the number or nuclei present.

- This is a differential equation and it has a solution:

where _N_ 0 is the number of nuclei in the sample. Note that I sometimes write _e_<sup>_x_</sup> as exp( _x_ ), they mean the same thing.

8/ 21

## EXAMPLE: RADIOACTIVE DECAY

9/ 21

## WHAT IS CALCULUS?

- Its is also a language and a way of reasoning.

- In this course, we will learn to use specific notation when we construct that reasoning and solve several physical laws.

- Differentiation goes from right to left!

10/ 21

## DIFFERENTIATION

▶ Whilst we can find the slope of the curve ‘graphically’, or ‘numerically’, we want the most accurate solution if possible.

∆ _<u>y</u>_ 1<sup>∆</sup><sup>_<u>y</u>_2</sup> ∆ _x_ 1<sup>=</sup> ∆ _x_ 2 _dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

- We need a formulaic way of deriving this value.

- There are rules we can rely on!

11/ 21

## DIFFERENTIATION

<!-- Start of picture text -->
▶ If we could derive expressions for the<br>approximation, what if we could find a<br>general rule?<br><!-- End of picture text -->

<!-- Start of picture text -->
y ′ = dy lim ∆ y<br>dx = ∆ x→ 0 ∆ x<br><!-- End of picture text -->

<!-- Start of picture text -->
A line with a non−constant gradient<br>5000<br>4000 f(x)=2x 3 −20x 2 +x+4000 @X=0 ∆  Y ∆  X ∆  Y<br>@X=−5 ∆  X @X=5<br>∆  Y<br>3000<br>∆  X<br>2000<br>1000 mmm123: : :  ∆∆∆  Y /  Y /  Y /  ∆∆∆  X=351.0 X=1.0 X=−49.0<br>0<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>1500<br>Its gradient<br>1000 f’(x)=6x 2 −40x+1<br>500<br>0<br>−500<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

12/ 21

## EXAMPLE: LINEAR FUNCTION

- Let’s derive a derivative for a straight line.

- The equation of a straight line can be expressed as the

following:

_y_ = _ax_

where _a_ is a constant.

- Lets find an expression for ∆<sup>∆</sup> _x_<sup>_<u>y</u>_</sup>

∆ _x_<sup>.</sup>

- If on the graph we start at ( _x, y_ ) and shift ∆ _x_ on the

_x_ -axis

_y_ + ∆ _y_ = _a_ ( _x_ + ∆ _x_ )

- = _ax_ + _a_ ∆ _x_

13/ 21

## EXAMPLE: LINEAR FUNCTION

- Let’s take away _y_ = _ax_

_y_ + ∆ _y − y_ = _ax_ + _a_ ∆ _x − ax_ ∆ _y_ = _a_ ∆ _x_

- Dividing by ∆ _x_ gives us

∆ _<u>y</u>_ ∆ _x_<sup>=</sup><sup>_a_</sup> ▶ If ∆ _x →_ 0 then ∆<sup>∆</sup> _x_<sup>_<u>y</u>→d_</sup> _dx_<sup>_<u>y</u>_and then the analytical</sup> derivative is

_dy dx_<sup>=</sup><sup>_a_</sup>

14/ 21

## EXAMPLE: QUADRATIC FUNCTION

▶ Let’s derive a derivative for a quadratic function.

- The equation of a quadratic function can be expressed

as the following:

_y_ = _ax_<sup>2</sup>

where _a_ is a constant.

- Lets find an expression for ∆<sup>∆</sup> _x_<sup>_<u>y</u>_</sup>

∆ _x_<sup>.</sup>

- If on the graph we start at ( _x, y_ ) and shift ∆ _x_ on the

_x_ -axis

_y_ + ∆ _y_ = _a_ ( _x_ + ∆ _x_ )<sup>2</sup>

- = _ax_<sup>2</sup> + 2 _ax_ (∆ _x_ ) + _a_ (∆ _x_ )<sup>2</sup>

15/ 21

## EXAMPLE: QUADRATIC FUNCTION

- Let’s take away _y_ = _ax_<sup>2</sup>

_y_ + ∆ _y − y_ = _ax_<sup>2</sup> + 2 _ax_ (∆ _x_ ) + _a_ (∆ _x_ )<sup>2</sup> _− ax_<sup>2</sup> ∆ _y_ = 2 _ax_ (∆ _x_ ) + _a_ (∆ _x_ )<sup>2</sup>

- Dividing by ∆ _x_ gives us

∆ _<u>y</u>_ ∆ _x_<sup>= 2</sup><sup>_ax_+</sup><sup>_a_∆</sup><sup>_x_</sup> ▶ If ∆ _x →_ 0 then<sup>∆</sup> ∆<sup>_<u>y</u>_</sup> _x_<sup>_→d_</sup> _dx_<sup>_<u>y</u>_and then the analytical</sup> derivative is

_dy dx_<sup>= 2</sup><sup>_ax_</sup>

16/ 21

## DIFFERENTIATION - COMMON LAWS

||**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|---|
|▶Based on that initial analysis, a rule which we can|_a_<br>_ax_|0<br>_a_|
|apply to any such function falls out in that if_y_=_x_<sup>_n_</sup>|_ax_<sup>2</sup>|2_ax_|
|then<br>|_ax_<sup>3</sup><br>|3_ax_<sup>2</sup><br>|
|_dy_<br>_dx_ <sup>=</sup><sup>_nxn−_1</sup>|_ax_<sup>4</sup><br>_x_<sup>_n_</sup>|4_ax_<sup>3</sup><br>_nx_<sup>_n−_1</sup>|
||_ax_<sup>_n_</sup>|_anx_<sup>_n−_1</sup>|

17/ 21

## DIFFERENTIATION - COMMON LAWS

- We can apply similar procedures to other common functions and start populating a list of rules.

- The more you practice these procedures, the easier it will become to apply them without looking them up.

- Use your math’s survival pack when needed!

- In class this week you will practice using all of these, and also have questions on the weekly assessment related to them.

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

18/ 21

## DIFFERENTIATION - COMMON LAWS

### ▶ What happens when we have a sum of functions?

_y_ = 5 _x_ + _e_<sup>_x_</sup>

- Well luckily, the derivative of the sum is the sum of the derivatives!

- This means we can just differentiate each term individually

_dy dx_<sup>= 5 +</sup><sup>_ex_</sup>

- We’ll see next week what happens when we have more complicated combinations of functions.

<!-- Start of picture text -->
Function y  = f ( x ) Derivative dy dx<br>constant 0<br>x 1<br>x n nx n− 1<br>e x e x<br>e kx ke kx<br>e f ( x ) df<br>dx ef ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) −sin ( x )<br><!-- End of picture text -->

19/ 21

## DIFFERENTIATION - COMMON LAWS

- The process by which a nucleus of an unstable atom emits energy to reach a more stable state. The abundance of atoms in these different states are described using the following function:

where _N_ 0 is the number of nuclei in the sample.

- For which we can derive two important derivative functions:

- Notice how we have used the rule for obtaining derivatives of exponential functions and then simplified to show the instantaneous decay is proportional to the existing abundance.

- Why highlight ‘instantaneous’?

20/ 21

## YOUR GROWING SKILLS LIBRARY

21/ 21
