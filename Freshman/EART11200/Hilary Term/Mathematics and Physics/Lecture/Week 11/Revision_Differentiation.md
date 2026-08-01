---
title: "Revision_Differentiation"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 11/Revision_Differentiation.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Revision Lecture - Differentiation_

1/ 43

## WEEK 1

- For a function, _y_ = _f_ ( _x_ ), that describes some process we are interested in, in one dimension, the derivative:

_f_<sup>_′_</sup> ( _x_ ) =<sup>_dy_</sup> _dx_

- It is interpreted as the rate of change of ‘y’ with respect to ‘x’.

- Lets imagine we are observing this change over a discrete interval, such that we could write

   - this as an approximation:

_dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

2/ 43

## WEEK 1

### ▶ We looked at the quadratic function:

2 _x −_ 10 _y_ =<sup>_~~√~~_</sup> _x_ + � 3 �

- We want the derivative at _x_ = 16.

- Assume, for now, no analytical function can be derived.

### ▶ **Euler’s Backward Method**

_dy_ = lim ∆ _<u>y yx − yx−</u>_ ∆ _x dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 ∆ _x_

3/ 43

## WEEK 1

### ▶ We looked at the quadratic function:

- We want the derivative at _x_ = 16.

- Assume, for now, no analytical function can be derived.

### ▶ **Euler’s Forward Method**

_dy_ = lim ∆ _<u>y yx</u>_ +∆ _x −_ _<u>yx</u> dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 ∆ _x_

4/ 43

## WEEK 1

- We see that using a step-size of ∆ _x_ = 0 _._ 25 that the estimated gradient:

▶ Euler’s Backward Method:<sup>∆</sup> ∆<sup>_<u>y</u>_</sup> _x_<sup>=</sup><sup>_−_1</sup><sup>_._1071</sup>

- The analytical derivative happens to be given by the following:

▶ At _x_ = 4,<sup>_d_</sup> _dx_<sup>_<u>y</u>_(4) =</sup><sup>_−_1</sup><sup>_._08333 so we can estimate the accuracy of each method!</sup>

5/ 43

## WEEK 2

- For a function, _y_ = _f_ ( _x_ ), that describes some process we are interested in, in one dimension, the derivative:

- It is interpreted as the rate of change of ‘y’ with respect to ‘x’. Lets imagine we are observing this change over a discrete interval, such that we could write this as an approximation:

_dy_ ∆ _<u>y</u>_<sup>lim</sup> _dx_<sup>=</sup> ∆ _x→_ 0 ∆ _x_

6/ 43

## WEEK 2

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

7/ 43

## WEEK 2

- What happens when we have a sum of functions?

_y_ = 5 _x_ + _e_<sup>_x_</sup>

- Well luckily, the derivative of the sum is the sum of the derivatives!

- This means we can just differentiate each term individually

_dy dx_<sup>= 5 +</sup><sup>_ex_</sup>

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1<br>|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup>|_e_<sup>_x_</sup>|
|_e_<sup>_kx_</sup>|_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)<br>_cos_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)<br>_−sin_(_x_)|

8/ 43

## WEEK 3

### ▶ Use the **Chain Rule** to differentiate:

_f_ ( _x_ ) = sin(3 _x_ + 1)

- **Step 1** : Split the function and substitute

- **Step 2** : Differentiate:

|_df_<br>_dg_ <sup>= cos(</sup><sup>_g_)</sup><br>_dg_<br>_dx_|<sup>= 3</sup>|
|---|---|
|e product rule and<br>_f_(_x_) =3cos(3_x_+|sub<br>1)|

- **Step 3** : Apply the product rule and substitute back in:

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

9/ 43

## WEEK 3

### ▶ Use the **Product Rule** to differentiate:

_f_ ( _x_ ) = _x_ exp(3 _x_ )

<!-- Start of picture text -->
The Product Rule<br>df dv<br>dx =  u dx +  vdu dx<br><!-- End of picture text -->

- **Step 1** : Split the function:

- **Step 2** : Differentiate:

_du dv dx_<sup>= 1</sup> _dx_<sup>= 3 exp(3</sup><sup>_x_)</sup>

- **Step 3** : Apply the product rule and substitute back in:

_f_ ( _x_ ) = 3 _x_ exp(3 _x_ ) + exp(3 _x_ ) = (3 _x_ + 1) exp(3 _x_ )

|**Function** **_y_ =** **_f_(****_x_)**|**Derivative** <sup>**_dy_**</sup><br>**_dx_**|
|---|---|
|constant|0|
|_x_|1|
|_x_<sup>_n_</sup>|_nx_<sup>_n−_1</sup>|
|_e_<sup>_x_</sup><br>_e_<sup>_kx_</sup>|_e_<sup>_x_</sup><br>_ke_<sup>_kx_</sup>|
|_e_<sup>_f_(</sup><sup>_x_)</sup><br>_ln_(_x_)<br>_sin_(_x_)|_df_<br>_dx_<sup>_ef_(</sup><sup>_x_)</sup><br>1<br>_x_<br>_cos_(_x_)|
|_cos_(_x_)|_−sin_(_x_)|

10/ 43

## WEEK 3

### ▶ Use the **Quotient Rule** to differentiate:

_f_ ( _x_ ) =<sup>3</sup><sup>_x_+ 1</sup> 6 _x −_ 1

- **Step 1** : Split the function:

_u_ ( _x_ ) = 3 _x_ + 1 _v_ ( _x_ ) = 6 _x −_ 1

- **Step 2** : Differentiate:

_du dv dx_<sup>= 3</sup> _dx_<sup>= 6</sup> : Apply the product rule and substitute back in: 9 _f_ ( _x_ ) =<sup>3(6</sup><sup>_x −_1)</sup><sup>_−_6(3</sup><sup>_x_+ 1)</sup> = _−_ (6 _x −_ 1)<sup>2</sup> (6 _x −_ 1)<sup>2</sup>

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

11/ 43

## WEEK 4

- Finding stationary values requires a number of steps:

   1. Differentiate _f_ ( _x_ ) to find the gradient function _f_<sup>_′_</sup> ( _x_ ) =<sup>_d_</sup> _dx_<sup>_<u>y</u>_</sup>

   2. Set the derivative to zero, _dx_<sup>_dy_= 0 and solve for</sup><sup>_x_</sup>

   3. If necessary, we substitute the stationary values, _x_ , into the function, _f_ ( _x_ ).

- Once you find where the derivatives are equal to 0 you can explore regions either side to determine if the gradient is positive or negative, and where the function is increasing or decreasing.

- This can tell us whether the stationary point is a maximum, minimum and/or inflection point. But, there is a more formal way to do this!

12/ 43

## WEEK 5

▶ Differential equations have an "order".

- Up to this point, we have only differentiated functions, _f_ ( _x_ ) once:

_f_<sup>_′_</sup> ( _x_ ) =<sup>_df_</sup> _dx_

- This is known as the **first-order derivative** .

- Differentiation can be carried out multiple times.

- By differentiating again, we obtain the **second-order derivative** which is defined as:

_f_<sup>_′′_</sup> ( _x_ ) =<sup>_d_</sup> _df_ =<sup>_d_2</sup><sup>_<u>f</u>_</sup> _dx_ � _dx_ � _dx_<sup>2</sup>

13/ 43

## WEEK 5

- Second-order derivatives have interesting properties and can be used to confirm whether a stationary point is a maximum or minimum point!

- We see that for a stationary value _x_ for the function _f_ ( _x_ ):

   - If _f_<sup>_′′_</sup> ( _x_ ) _<_ 0 the stationary value is a maximum

   - If _f_<sup>_′′_</sup> ( _x_ ) _>_ 0 the stationary value is a minimum

   - If _f_<sup>_′′_</sup> ( _x_ ) = 0 it is not possible to conclude anything about the stationary value.

- If we’re in the situation that _f_<sup>_′′_</sup> ( _x_ ) = 0, then it is potentially a saddle point. Need to investigate using the properties of the first-order derivative.

14/ 43

## WEEK 5

- You may not be familiar with the concept of **steady-state** .

- When a system is in steady-state, the key variables that

describe the system’s behavior do not change over time:

<!-- Start of picture text -->
dV<br>= ⇒ d 2 V<br>dt =  f ( t, x 1 , x 2) dt 2 = 0<br><!-- End of picture text -->

15/ 43

## WEEK 5

- In many cases, it will not be possible to calculate when a function has a value of 0. Important for stationary values.

- For example, how do you solve:

- Use Newton’s Method for Root Finding:

- We pick a starting guess _x_ 0 and apply this formula iteratively until we reach some threshold.

16/ 43

## WEEK 11

### ▶ A **scalar field** is a function of two or more variables

- Scalar fields represent a single value at different positions.

- They have **magnitude but no direction** and can be represented with a colour plot.

- A **vector field** is a mathematical function that assigns a vector to each point in space.

- They have **magnitude and direction** as we can determine a direction, or flow and the magnitude from the length of the arrow.

17/ 43

## WEEK 11

- Each line in this figure represents the same vector, but a different starting position.

- Wherever the starting position is, each vector moves 2

units to the left and 5 units up.

- If we write this procedure in vector form we write:

_v_ = _⟨−_ 2 _,_ 5 _⟩_

- Notice the distinction in style between the variable and

the brackets.

- Specifically, _⟨−_ 2 _,_ 5 _⟩_ is fundamentally different from

writing ( _−_ 2 _,_ 5).

18/ 43

## WEEK 11

- The magnitude of a vector is calculated by taking the square root of all of the square its components

   - (i.e. Pythagoras’ theorem):

- Vectors can be added or subtracted (add or subtract by component) or multiplied by a scalar (constant).

- Given the vectors _a_ = _⟨a_ 1 _, a_ 2 _⟩_ and _b_ = _⟨b_ 1 _, b_ 2 _⟩_ :

19/ 43

## WEEK 11

- We now think about differentiation of functions of two (or more) variables (i.e. scalar field),

   - _z_ = _f_ ( _x, y_ ), which now depend on _x_ and _y_ .

- For a one dimensional curve the gradient<sup>_d_</sup> _dx_<sup>_<u>y</u>_is fairly straight forward.</sup>

- When using more than 1D, we have to use something else to denote the gradient.

- The standard that is used is called ‘grad’, which is defined for a scalar field and can be written

- Note that _∇f_ (where _f_ = _f_ ( _x, y, z_ ) is a scalar field) is actually a vector.

20/ 43

## WEEK 11

▶ The gradient of a scalar field has magnitude and direction!

- Notice the change in the derivative symbol:

_∂f ∂x_

- Up to this point in our course, we have been using the expression:

- The change is important as this is called a **partial derivative** .

- When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant.

21/ 43

## WEEK 11

- The gradient has magnitude and direction!

- Notice the change in the derivative symbol:

_∂f_

_∂x_

- Up to this point in our course, we have been using the expression:

_df dx_

- The change is important as this is called a **partial derivative** and we move into using **partial differential equations** .

- When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant.

22/ 43

## 2023-24 PAST PAPER

### ▶ Select TRUE or FALSE to the following statements about differentiation.

(a) If _f_ ( _x_ ) = cos(2 _x_ ) then _dx_<sup>_df_= 2 sin(2</sup><sup>_x_)?</sup>

- False!

_df dx_<sup>=</sup><sup>_−_2 sin(2</sup><sup>_x_)</sup>

23/ 43

## 2023-24 PAST PAPER

### ▶ Select TRUE or FALSE to the following statements about differentiation.

(b) If _f_ ( _x_ ) = _e_<sup>_−_2</sup><sup>_x_</sup> then _dx_<sup>_df_=</sup><sup>_−e−_2</sup><sup>_x/_2?</sup>

- False!

_df dx_<sup>=</sup><sup>_−_2</sup><sup>_e−_2</sup><sup>_x_</sup>

24/ 43

## 2023-24 PAST PAPER

### ▶ Select TRUE or FALSE to the following statements about differentiation. (c) If _f_ ( _x_ ) = ln(2 _x_ ) then _dx_<sup>_df_= 1</sup><sup>_/_2</sup><sup>_x_?</sup>

- False!

25/ 43

## 2023-24 PAST PAPER

▶ Select TRUE or FALSE to the following statements about differentiation.

(d) If _f_ ( _x_ ) = 5 _x_<sup>_n_</sup> then _dx_<sup>_df_= 5</sup><sup>_nxn_?</sup>

- True!

26/ 43

## 2023-24 PAST PAPER

▶ Select TRUE or FALSE to the following statements about differentiation.

(e) If _f_ ( _x_ ) = sin( _x_ ) then _dx_<sup>_d_22</sup><sup>_<u>f</u>_=</sup><sup>_−_sin(</sup><sup>_x_)?</sup>

▶ True!

27/ 43

## 2023-24 PAST PAPER

### ▶ Using Newtons method, find the root of the following function:

correct to 3 decimal places. You may use a starting guess of _x_ 0 = _−_ 0 _._ 6. Recall that we can write Newtons formula for root finding, generally, as:

28/ 43

## 2023-24 PAST PAPER

- First, we need to find the derivative of _f_ ( _x_ ):

- Calculate the first guess ( _x_ 1):

_x_ 1 = _x_ 0 _−_<sup>_<u>f</u>_</sup><sup><u>(</u></sup><sup>_x_0)</sup> _f_<sup>_′_</sup> ( _x_ 0) = _−_ 0 _._ 6 _−_<sup>0</sup><sup>_._188811</sup> 1 _._ 748812<sup>=</sup><sup>_−_0</sup><sup>_._7079657</sup>

29/ 43

## 2023-24 PAST PAPER

- Calculate the second guess ( _x_ 2):

- Calculate the third guess ( _x_ 3):

- So the root of _f_ ( _x_ ) correct to 3 decimal places is _x_ = _−_ 0 _._ 703.

30/ 43

## 2023-24 PAST PAPER

### ▶ A gas leak is emitting Butane at a variable rate. The concentration equation is given below, where G is given in micrograms per cubic metre and the x-axis given in minutes.

▶ The associated equation for G is also given as:

_G_ ( _t_ ) = 3 + 14 _t −_ 5 _t_<sup>2</sup>

▶ Find the time at which the maximum concentration of emitted gas occurs.

31/ 43

## 2023-24 PAST PAPER

▶ We need to derive<sup>_<u>dG</u>_</sup> _dt_<sup>:</sup> _G_ ( _t_ ) = 3 + 14 _t −_ 5 _t_<sup>2</sup> = _⇒_<sup>_dG_</sup> _dt_<sup>= 14</sup><sup>_−_10</sup><sup>_t_</sup>

- To get the maximum we set the derivative to zero and solve for _t_

_dG dt_<sup>= 14</sup><sup>_−_10</sup><sup>_t_= 0=</sup><sup>_⇒_14</sup><sup>_−_10</sup><sup>_t_= 0=</sup><sup>_⇒t_= 1</sup><sup>_._4</sup>

32/ 43

## 2023-24 PAST PAPER

- Differentiate the following expressions with respect to x. Simplify your answer as much as possible:

33/ 43

## 2023-24 PAST PAPER

- **Step 1** : Split the function:

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

34/ 43

## 2023-24 PAST PAPER

- Differentiate the following expressions with respect to x. Simplify your answer as much as possible:

<!-- Start of picture text -->
x<br>g  =<br>√ x 2 + 4<br><!-- End of picture text -->

35/ 43

## 2023-24 PAST PAPER

- **Step 1** : Split the function:

▶ **Step 2** : Differentiate:

- **Step 3** : Apply the quotient rule and substitute back in:

36/ 43

## 2023-24 PAST PAPER

- Differentiate the following expressions with respect to x. Simplify your answer as much as possible:

_y_ =<sup>_e−x_2</sup> _x_

37/ 43

## 2023-24 PAST PAPER

▶ **Step 1** : Split the function: _u_ ( _x_ ) = _e_<sup>_−x_2</sup> _v_ ( _x_ ) = _x_ ▶ **Step 2** : Differentiate: _du dv dx_<sup>=</sup><sup>_−_2</sup><sup>_xe−x_2</sup> _dx_<sup>= 1</sup>

- **Step 3** : Apply the quotient rule and substitute back in:

_−_ 2 _x_<sup>2</sup> _e_<sup>_−x_2</sup> _− e_<sup>_−x_2</sup> _f_ ( _x_ ) = _x_<sup>2</sup> = _−e_<sup>_−x_2</sup> <u>(2</u> _x_<sup>2</sup> + 1) _x_<sup>2</sup>

38/ 43

## 2023-24 PAST PAPER

- A fuel tank has a slow releasing leak. We want to study the volume of fuel in the tank over time _t_ which can be described using the following equation:

where _V_ 0 = 10 is the volume of fuel (in _m_<sup>2</sup> ) and 0 _< t <_ 24 (in hours). What is the rate of the leak at 2 hours? Determine the rate analytically but also compare to a rate calculated numerically using central differences method with a time step ∆ _t_ of 30 minutes. Estimate the percentage error of the numerical result.

39/ 43

## 2023-24 PAST PAPER

- **Step 1** : Split the function:

- **Step 2** : Differentiate:

- **Step 3** : Apply the product rule and substitute back in:

40/ 43

## 2023-24 PAST PAPER

41/ 43

## 2023-24 PAST PAPER

- We can also find the rate at 2 hours numerically using the central differences method. We use a timestep of 30 minutes, so evaluate the Volume _V_ 0 at _t_ = 1 _._ 5 and _t_ = 2 _._ 5

- Calculate the rate numerically:

42/ 43

## 2023-24 PAST PAPER

- The rate has an error of 0.02716 which as a percentage is:

100 _×_<sup>_−_1</sup><sup>_._13079 + 1</sup><sup>_._10363</sup> = 2 _._ 46% _−_ 1 _._ 10363

43/ 43
