---
title: "lecture4(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 4/lecture4(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 4 Lecture - Optimisation and Properties of Derivatives_

1/ 20

## LAST WEEK...

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

2/ 20

## LAST WEEK...

### ▶ Use the **Product Rule** to differentiate:

<!-- Start of picture text -->
The Product Rule<br>df dv<br>dx =  u dx +  vdu dx<br><!-- End of picture text -->

- **Step 1** : Split the function:

- **Step 2** : Differentiate:

_du dv dg_<sup>= 1</sup> _dx_<sup>= 3 exp(3</sup><sup>_x_)</sup>

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

3/ 20

## LAST WEEK...

### ▶ Use the **Quotient Rule** to differentiate:

_f_ ( _x_ ) =<sup>3</sup><sup>_x_+ 1</sup> 6 _x −_ 1

- **Step 1** : Split the function:

_u_ ( _x_ ) = 3 _x_ + 1 _v_ ( _x_ ) = 6 _x −_ 1

### ▶ **Step 2** : Differentiate:

_du dv dg_<sup>= 3</sup> _dx_<sup>= 6</sup> : Apply the product rule and substitute back in: 9 _f_ ( _x_ ) =<sup>3(6</sup><sup>_x −_1)</sup><sup>_−_6(3</sup><sup>_x_+ 1)</sup> = _−_ (6 _x −_ 1)<sup>2</sup> (6 _x −_ 1)<sup>2</sup>

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

4/ 20

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

5/ 20

## INTENDED LEARNING OUTCOMES

- (1) Describe the properties of derivatives in the analysis of functions.

- (2) Analyse the behavior of functions by applying differentiation in theoretical and real-world applications.

- (3) Solve differentiated functions to determine stationary values in theoretical and real-world applications.

- (4) Apply differentiation techniques to optimise functions in real-world problems.

6/ 20

## PROPERTIES OF DERIVATIVES

▶ For the last couple of weeks, we have been learning how to calculate derivatives of functions.

- Whilst telling us the rate of change of a function, derivatives can also be used to determine certain properties of a function!

- We now carry on with the topic of differentiation onto the topic of finding maxima and minima.

- This means to find the point on a curve that is either a maximum value or a minimum value. This turns out to be very useful.

- More generally maxima and minima are called stationary values or stationary values.

7/ 20

## PROPERTIES OF DERIVATIVES

- Finding **maximum** , **minimum** or **saddle point** of a function, or optimising a function, requires a number of steps:

- We see that for a function _f_ ( _x_ ):

   - If _f_<sup>_′_</sup> ( _x_ ) _>_ 0 then _f_ ( _x_ ) is increasing.

   - If _f_<sup>_′_</sup> ( _x_ ) _>_ 0 then _f_ ( _x_ ) is decreasing.

   - If _f_<sup>_′_</sup> ( _x_ ) = 0 it is likely that _f_ ( _x_ ) will be changing direction!

- Once we know where the these stationary values are for a function, further analysis can help

   - classify them.

8/ 20

## EXAMPLE: QUADRATIC FUNCTION

### ▶ Consider a quadratic function

_f_ ( _x_ ) =<sup>_x_2</sup> 2<sup>_−_5</sup><sup>_x_+ 2</sup>

▶ The thing to notice about the derivative from the graph, is that it is equal to zero at the point where _f_ ( _x_ ) is at its minimum (or stationary).

### ▶ Differentiate to find the stationary value

_df dx_<sup>=</sup><sup>_x −_5</sup>

<!-- Start of picture text -->
40<br>30<br>20<br>10<br>0<br>−10<br>−5 0 5 10 15<br>x<br>10<br>5<br>0<br>−5<br>−10<br>−5 0 5 10 15<br>x<br>f(x)<br>f(x)<br><!-- End of picture text -->

9/ 20

## EXAMPLE: QUADRATIC FUNCTION

<!-- Start of picture text -->
40<br>30<br>Find the minimum by setting the derivative to zero and 20<br>x = 5<br>df 10  f'(x) = 0<br>dx = 0 = ⇒ x − 5 = 0 = ⇒ x  = 5 0<br>This tells us that the minimum value does indeed occur −10<br>−5 0 5 10 15<br>x<br>10<br> f ( x ) at the stationary at the stationary<br>5<br>maximum and minimum) x = 5<br>0  f'(x) = 0<br>f (5) = 5 2 2 − 5  ×  5 + 2 = 10 . 5 −5<br>−10<br>−5 0 5 10 15<br>x<br>f(x)<br>f(x)<br><!-- End of picture text -->

- Find the minimum by setting the derivative to zero and solve:

- This tells us that the minimum value does indeed occur at _x_ = 5.

- We can evaluate the value of _f_ ( _x_ ) at the stationary at the stationary value (i.e. maximum and minimum)

10/ 20

## EXAMPLE: CUBIC FUNCTION

▶ Sometimes there can be more than one stationary value. Consider a cubic equation: _f_ ( _x_ ) =<sup>_x_</sup> 3<sup>3+ 2</sup><sup>_x_2</sup><sup>_−_5</sup><sup>_x_+ 1</sup>

▶ We can see that there is a point on the curve that where a minimum occurs ( _x_ = 2) and where a maximum occurs ( _x_ = _−_ 5), not immediately visible.

- Differentiate to find the stationary values:

_df dx_<sup>=</sup><sup>_x_2 + 4</sup><sup>_x −_5</sup>

<!-- Start of picture text -->
40<br>0<br>−40<br>−80<br>−10 −5 0 5<br>x<br>40<br>20<br>0<br>−10 −5 0 5<br>x<br>g(x)<br>g(x)<br><!-- End of picture text -->

11/ 20

## EXAMPLE: CUBIC FUNCTION

- Find the minimum and maximum by setting the derivative to zero and solve

_df dx_<sup>= 0=</sup><sup>_⇒x_2 + 4</sup><sup>_x −_5 = 0=</sup><sup>_⇒_(</sup><sup>_x −_1)(</sup><sup>_x_+ 5) = 0</sup>

- This tells us that two stationary values at _x_ = _−_ 5 and _x_ = 1.

▶ It’s more difficult when there are multiple stationary values to determine whether they are maxima, minima or saddle points, but for now, the plot confirms that _x_ = _−_ 5 and _x_ = 1 are a maximum and minimum respectively.

<!-- Start of picture text -->
x = −5<br>40  g'(x) = 0<br>0<br>x = 1<br>−40  g'(x) = 0<br>−80<br>−10 −5 0 5<br>x<br>x = −5 x = 1<br> g'(x) = 0  g'(x) = 0<br>40<br>20<br>0<br>−10 −5 0 5<br>x<br>g(x)<br>g(x)<br><!-- End of picture text -->

12/ 20

## EXAMPLE: cos( _x_ ) AND sin( _x_ )

### ▶ We know that from the laws of calculus that

_y_ = sin( _x_ ) = _⇒_<sup>_d_</sup> _dx_<sup>_<u>y</u>_= cos(</sup><sup>_x_)</sup>

- We can see that the properties of derivatives follow from plotting the two functions against each other:

   - cos( _x_ ) = 0 when sin( _x_ ) is stationary

   - cos( _x_ ) _>_ 0 when sin( _x_ ) is increasing

- cos( _x_ ) _<_ 0 when sin( _x_ ) is decreasing

13/ 20

## PROPERTIES OF DERIVATIVES

- In the two previous examples, we determined whether stationary values were maxima, minima, or saddle points from a plot. We could and strictly should verify this.

- Furthermore, both examples were simple enough that we could solve for zero just by rearranging.

- We’ll come to both of these issues next week!

- An informal way of checking for a maximum or a minimum is by using the properties of the

   - derivative.

14/ 20

## EXAMPLE: QUADRATIC FUNCTION

<!-- Start of picture text -->
40<br>30 f'(x) < 0 f'(x) > 0<br>20<br>f ( x ) = x 2 2 − 5 x  + 2 dxdf =  x − 5 10  f'x = 5(x) = 0<br>0<br> x  = 5, so evaluate the 5, so evaluate the<br>−10<br>−5 0 5 10 15<br>x<br>10<br>x  = 4 = ⇒ dx df (4) =  x − 5 =  − 1 f'(x) < 0<br>5<br>x = 5<br>x  = 6 = ⇒ dx df (6) = 6  − 5 = 1 0  f'(x) = 0<br>( x ) is decreasing when is decreasing when  x < <  5 and increasing −5<br> 5 so we do indeed have a minimum. f'(x) > 0<br>−10<br>−5 0 5 10 15<br>x<br>f(x)<br>f(x)<br><!-- End of picture text -->

### ▶ Let’s return to a quadratic function

- We had a stationary value at _x_ = 5, so evaluate the 5, so evaluate the derivative either side:

▶ Therefore _f_ ( _x_ ) is decreasing when is decreasing when _x < <_ 5 and increasing when _x >_ 5 so we do indeed have a minimum.

15/ 20

## OPTIMISATION

- Optimisation problems involve finding the best solution, often the maximum or minimum value(s) of a function given set of constraints.

- They are quite common in real-world applications:

   - (a) a function describing gross profit and a function describing costs, then you can optimise net profit for maximum gain!

   - (b) want to construct the largest box possible but have a limit on the size of a piece of cardboard, you can optimise the boxes volume!

- Derivatives and their properties play a crucial role in a wide range of problems such as

   - optimisation.

- We study a function to find the maxima and minima which "optimises" it, which can play a

   - vital role in decision making.

- Lets consider an example.

16/ 20

## EXAMPLE: GOLD SEAM PROBLEM

- You decide to mine a gold seam and want to decide on how long to mine it for to maximise your profits.

- The value of gold you can mine per day (in millions), _G_ , is a function of the number of days, _n_ , that you mine for

_G_ ( _n_ ) = 100 _−_<sup>100</sup> _n_ + 1

- The cost of renting the equipment to mine, _C_ ( _n_ ), increases with the number of days

_C_ ( _n_ ) = _n_

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

### ▶ Your profit is given by:

_P_ ( _n_ ) = _G_ ( _n_ ) _− C_ ( _n_ ) = 100 _−_<sup>100</sup> _n_ + 1<sup>_−n_</sup>

17/ 20

## EXAMPLE: GOLD SEAM PROBLEM

▶ Can we optimise the net profit? Yes, using differentiation and using its derivative to look for stationary values!

### ▶ Profit is given by

_P_ ( _n_ ) = 100 _−_<sup>100</sup> _n_ + 1<sup>_−n_</sup> _dP_ 10 _dn_<sup>= 0 +</sup> _dn_<sup>_d_</sup> � _n_ + 1 � _−_ 1

### ▶ Find the derivative

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

### ▶ Using the chain rule we see that

<!-- Start of picture text -->
d 10 10<br>dn � n  + 1 � =  − ( n  + 1) 2<br><!-- End of picture text -->

18/ 20

## EXAMPLE: GOLD SEAM PROBLEM

▶ So then _dP_ 100 _dn_<sup>=</sup> ( _n_ + 1)<sup>2</sup><sup>_−_1</sup> ▶ Where are the stationary values? Set the derivative to zero and solve!

<!-- Start of picture text -->
dP 100<br>dn = 0 = ⇒ ( n  + 1) 2 − 1 = 0<br>= ⇒ ( n  + 1) 2 = 100<br>= ⇒ n 2 + 2 n − 99 = 0<br>= ⇒ ( n  + 11)( n − 9) = 0<br><!-- End of picture text -->

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

19/ 20

## EXAMPLE: GOLD SEAM PROBLEM

▶ The stationary values are at _n_ = _−_ 11 and _n_ = 9. We ignore the first as we cannot have negative time! We can see from the graph that at _n_ = 9 _P_ ( _n_ ) is maximised!

- Therefore, we optimise the profit at 9 days so we should stop digging after that.

- We have determined whether stationary values

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

20/ 20
