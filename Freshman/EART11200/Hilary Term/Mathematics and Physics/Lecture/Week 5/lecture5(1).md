---
title: "lecture5(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 5/lecture5(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 5 Lecture - Second-order Derivatives and Root Finding_

1/ 23

## LAST WEEK...

- Finding **maximum** , **minimum** or **saddle point** of a function, or optimising a function, requires a number of steps:

- We see that for a function _f_ ( _x_ ):

   - If _f_<sup>_′_</sup> ( _x_ ) _>_ 0 then _f_ ( _x_ ) is increasing.

   - If _f_<sup>_′_</sup> ( _x_ ) _<_ 0 then _f_ ( _x_ ) is decreasing.

   - If _f_<sup>_′_</sup> ( _x_ ) = 0 it is likely that _f_ ( _x_ ) will be changing direction!

- Once we know where the these stationary values are for a function, further analysis can help

classify them.

2/ 23

## LAST WEEK...

- Finding stationary values requires a number of steps:

   1. Differentiate _f_ ( _x_ ) to find the gradient function _f_<sup>_′_</sup> ( _x_ ) = _dx_<sup>_dy_</sup>

   2. Set the derivative to zero, _dx_<sup>_dy_= 0 and solve for</sup><sup>_x_</sup>

   3. If necessary, we substitute the stationary values, _x_ , into the function, _f_ ( _x_ ).

- Once you find where the derivatives are equal to 0 you can explore regions either side to determine if the gradient is positive or negative, and where the function is increasing or decreasing.

- This can tell us whether the stationary point is a maximum, minimum and/or inflection point. But, there is a more formal way to do this!

3/ 23

## LAST WEEK...

- Finding stationary points (maximum or minimum)

proves useful to optimise functions or processes.

- Last week, we saw an example where we wanted to maximise profits from gold mining.

- The net profit from mining, _P_ , as a function of days, _n_ , was given by:

_P_ ( _n_ ) = _G_ ( _n_ ) _− C_ ( _n_ ) = 100 _−_<sup>100</sup> _n_ + 1<sup>_−n_</sup>

- To find the day where we have maximised (i.e. optimise) our profit, we look for stationary values

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

_dP_ 100 _dn_<sup>=</sup> ( _n_ + 1)<sup>2</sup><sup>_−_1 = 0</sup>

4/ 23

## LAST WEEK...

- Rearranging this equation showed us that there are

   - stationary values at _n_ = _−_ 11 and _n_ = 9. We ignore _n_ = _−_ 11 as we cannot have negative time!

- We can see from the graph that at _n_ = 9, _P_ is maximised!

- Therefore, we optimise the profit at 9 days so we should stop mining after that.

- We can see that this is a maximum from the plot, but we could/should check this.

<!-- Start of picture text -->
4<br>10  x 10<br>5<br>0 Gross profit, G<br>Costs, C<br>Net profit, P<br>−5<br>0 20 40 60 80 100<br>Days of the project, n<br>Amount in pounds<br><!-- End of picture text -->

5/ 23

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

6/ 23

## INTENDED LEARNING OUTCOMES

(1) Explain the concept and significance of second-order derivatives in the analysis of functions.

(2) Compute second-order derivatives of functions to classify stationary values as maxima, minima, or saddle points in optimisation problems.

- (3) Describe steady-state systems in physical and mathematical modeling.

- (4) Apply Newton’s Method to find the roots of complex functions in numerical problem-solving.

7/ 23

## SECOND-ORDER DERIVATIVES

- Differential equations have an "order".

- Up to this point, we have only differentiated functions, _f_ ( _x_ ) once:

- This is known as the **first-order derivative** .

- Differentiation can be carried out multiple times.

- By differentiating again, we obtain the **second-order derivative** which is defined as:

- For example, later in the course you will solve differential equations of the form:

8/ 23

## SECOND-ORDER DERIVATIVES

- The second-order derivative has some very interesting and useful properties.

- Previously we saw that the first-order derivative, _f_<sup>_′_</sup> ( _x_ ) tells us about the rate of change of a function, _f_ ( _x_ ).

- The second-order derivative, _f_ ( _x_ ), goes a step further by telling us how the rate of change, _f_<sup>_′_</sup> ( _x_ ), itself is changing.

- You can find a cars acceleration by finding out the second derivative (i.e. the rate of change of speed with respect to time) of the distance travelled with respect to the time):

   - Distance travelled at time _t_ : _x_ = _f_ ( _t_ ).

   - Velocity at time _t_ : _v_ = _f_<sup>_′_</sup> ( _t_ ).

   - Accelaration at time _t_ : _a_ = _f_<sup>_′′_</sup> ( _t_ )

9/ 23

## SECOND-ORDER DERIVATIVES

- Second-order derivatives have interesting properties

and can be used to confirm whether a stationary point is a maximum or minimum point!

- We see that for a stationary value _x_ for the function

_f_ ( _x_ ):

- If _f_<sup>_′′_</sup> ( _x_ ) _<_ 0 the stationary value is a maximum

- If _f_<sup>_′′_</sup> ( _x_ ) _>_ 0 the stationary value is a minimum

- If _f_<sup>_′′_</sup> ( _x_ ) = 0 it is not possible to conclude anything about

   - the stationary value.

- If we’re in the situation that _f_<sup>_′′_</sup> ( _x_ ) = 0, then it is

potentially a saddle point. Need to investigate using the properties of the first-order derivative.

10/ 23

## EXAMPLE: QUADRATIC FUNCTION

- Last week, we found the stationary value of the following quadratic:

<!-- Start of picture text -->
40<br>30 f'(x) < 0 f'(x) > 0<br>20<br>x 2<br>2 − 5 x  + 2 10  f'x = 5(x) = 0<br>0<br>−10<br>5 = 0 = ⇒ x  = 5 −5 0 5 10 15<br>x<br>10<br> x  = 5 which we can see is a 5 which we can see is a f'(x) < 0<br>5<br>x = 5<br>0  f'(x) = 0<br>d 2 f −5<br>dx 2 = 1 f'(x) > 0<br>−10<br>−5 0 5 10 15<br> x  = 5 is a minimum 5 is a minimum x<br>f(x)<br>f(x)<br><!-- End of picture text -->

▶ We found a stationary value at _x_ = 5 which we can see is a 5 which we can see is a minimum. Confirm it by looking at the second-order derivative:

▶ Since _dx_<sup>_d_22</sup><sup>_<u>f</u>>_0 then we confirm that</sup><sup>_x_= 5 is a minimum 5 is a minimum</sup>

11/ 23

## EXAMPLE: CUBIC FUNCTION

<!-- Start of picture text -->
x = −5<br>40  g'(x) = 0 g'(x) < 0<br>0<br>f ( x ) = x 3 3 + 2 x 2  − 5 x  + 1 −40  g'(x) = 0x = 1<br>−80 g'(x) > 0 g'(x) > 0<br>−10 −5 0 5<br>df x = −5 x x = 1<br>dx =  x 2 + 4 x − 5  g'(x) = 0 g'(x) < 0  g'(x) = 0<br>df 40<br>dx = 0 = ⇒ ( x − 1)( x  + 5) = 0<br>20<br> x  =  − 5 and  x  = 1 1<br>0<br>g'(x) > 0 g'(x) > 0<br>−10 −5 0 5<br>x<br>g(x)<br>g(x)<br><!-- End of picture text -->

- Last week, we found the stationary value of the following cubic:

- The function has a stationary points at _x_ = _−_ 5 and _x_ = 1 1 which we see are maximum and minimum respectively.

12/ 23

## EXAMPLE: CUBIC FUNCTION

- Confirm if it is by looking at the second order derivative:

_df dx_<sup>= 2</sup><sup>_x_+ 4</sup>

- Evaluate the second order derivatives at the stationary points:

_df_<sup>_df_</sup> = 2 _×_ 1 + 4 = 6 _dx_<sup>(</sup><sup>_−_5) = 2</sup><sup>_×_(</sup><sup>_−_5) + 4 =</sup><sup>_−_6</sup> _dx_<sup>(1)</sup>

▶ Since _dx_<sup>_d_22</sup><sup>_<u>f</u><_0 at</sup><sup>_x_=</sup><sup>_−_5 then we confirm it is a maximum.</sup>

- Since _dx_<sup>_d_22</sup><sup>_<u>f</u>>_0 at</sup><sup>_x_= 1 then we confirm it is a minimum.</sup>

<!-- Start of picture text -->
x = −5<br>40  g'(x) = 0 g'(x) < 0<br>0<br>x = 1<br>−40  g'(x) = 0<br>−80 g'(x) > 0 g'(x) > 0<br>−10 −5 0 5<br>x<br>x = −5 x = 1<br>g'(x) < 0<br> g'(x) = 0  g'(x) = 0<br>40<br>20<br>0<br>g'(x) > 0 g'(x) > 0<br>−10 −5 0 5<br>x<br>g(x)<br>g(x)<br><!-- End of picture text -->

13/ 23

## STEADY STATE

- You may not be familiar with the concept of **steady-state** .

- When a system is in steady-state, the key variables that describe the system’s behavior do not change over time.

- In a chemical system, we might observe that the systems variables remain constant despite ongoing processes that would lead to change. This requires there is flow through the system.

- Consider the situation where water is poured into a container which has an outlet part on the side of the container.

14/ 23

## STEADY STATE

▶ If a system is in steady-state, the variables that define the behaviour of the system do not change with time. What does this mean mathematically?

- We can say that the rate of change of the water volume remains constant, either with respect to time or space.

- Suppose the rate of change can be written as:

_dV dt_<sup>=</sup><sup>_f_(</sup><sup>_t, x_1</sup><sup>_, x_2)</sup>

15/ 23

## STEADY STATE

▶ This equation describes the rate at which the total volume of water _V_ is a function of time and multiple sources and sinks of water.

▶ Using the definition of steady state, the rate of change is constant over time, we can take the derivative again to show that:

<!-- Start of picture text -->
d 2 V<br>dt 2 = 0<br><!-- End of picture text -->

16/ 23

## EXAMPLE: CAR TRAVELLING AT CONSTANT SPEED

- Imagine you are in a car that is travelling down the

   - motorway.

- The equation describing the distance travelled (in miles) by

   - time is given by:

- Is this system in steady state?

- Let’s take the first- and second-order derivative:

- As<sup>_<u>dx</u>_</sup> _dt_<sup>(the velocity) is constant and</sup><sup>_<u>d</u>_</sup> _dt_<sup>22</sup><sup>_<u>x</u>_(the acceleration) is</sup> zero, then the car is in steady state!

17/ 23

## ROOT FINDING

- We keep discussing the importance of derivatives to understand change and most of our examples have been a combination of hypothetical and real-world examples designed to calculate the gradient of a line.

- One application involves finding the roots of a function: calculating when a function has a value of 0.

- In the examples you have seen, you can factorise this out easily, by rearranging an equation, or by hand.

- In many cases this will not be possible. For example, how do you solve:

- In this case, it’s difficult to find where _f_ ( _x_ ) = 0 using simple algebra.

18/ 23

## ROOT FINDING

- We could look at the plot and iteratively look for values

until we get close to _f_ ( _x_ ) = 0

- Time consuming and laborious, but also impossible to visualise for complex functions.

- What if we could somehow use the trajectory information provided by gradients, thus tangent lines, in some way?

- Imagine our first value for _x_ is denoted as _x_ 0. We see that

   - _f_ ( _x_ 0) _>_ 0 and we have a gradient (and tangent line),

_dy dx_<sup>(</sup><sup>_x_0) =</sup><sup>_f ′_(</sup><sup>_x_0)</sup>

- We can use this to follow the tangent line from the curve to

   - the x-axis.

19/ 23

## ROOT FINDING

- We could look at the plot and iteratively look for values

until we get close to _f_ ( _x_ ) = 0

- Time consuming and laborious, but also impossible to visualise for complex functions.

- What if we could somehow use the trajectory information provided by gradients, thus tangent lines, in some way?

- Imagine our first value for _x_ is denoted as _x_ 0. We see that

   - _f_ ( _x_ 0) _>_ 0 and we have a gradient (and tangent line),

_dy dx_<sup>(</sup><sup>_x_0) =</sup><sup>_f ′_(</sup><sup>_x_0)</sup>

- We can use this to follow the tangent line from the curve to

   - the x-axis.

20/ 23

## ROOT FINDING

- The tangent crosses the _x_ -axis and arrives at another value

for _x_ which we shall denote _x_ 1.

- We can write this as an equation:

_y_ = _f_ ( _x_ 0) + _f_<sup>_′_</sup> ( _x_ 0)( _x_ 1 _− x_ 0)

- We can see on our graph that when, in this equation, _y_ = 0,

then _x_ = _x_ 1. So we can find our value for _x_ 1 by setting _y_ = 0 and re-arranging:

21/ 23

## ROOT FINDING

- This leads us to Newtons Method for Root Finding:

- We do this iteratively and we can see on the right this gets

   - us closer and closer to the root.

- You may never reach an exact value for _f_ ( _x_ ) = 0 so we pick a threshold.

- For example, if y is less than 0.001 or values for _xn_ do not

   - change by more than 0.01%.

- This depends on the nature of the problem you are trying to

   - solve.

22/ 23

## EXAMPLE: ROOT FINDING

- Let’s consider the example where we want to find roots of:

- To use Newtons Method, we take the derivative:

- To find a root, we need an initial guess. This can be important. But for now, let’s start at _x_ 0 = 3 _._ 5:

_x_ 1 = _x_ 0 _−_<sup>_<u>f</u>_</sup><sup><u>(</u></sup><sup>_x_0)</sup> _f_<sup>_′_</sup> ( _x_ 0)<sup>= 3</sup><sup>_._5</sup><sup>_−_</sup> 19<sup>3</sup><sup>_._</sup> _._<sup>6154</sup> 1154<sup>= 3</sup><sup>_._3109</sup> ▶ In the weekly exercises, you will be asked to proceed with this problem until you arrive at an approximation for the root which is _x ≈_ 3 _._ 275601.

23/ 23
