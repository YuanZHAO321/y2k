---
title: "Revision_Integration"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 12/Revision_Integration.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

**Mathematics and Physics**

_Revision Lecture - Integration_

1/ 37

## WEEK 6

- Integration is the **reverse** of differentiation.

- Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values.

- The � symbol was introduced by Gottfried Wilhelm Leibniz in the 17th century to represent summation of infinitely many infinitesimally small quantities.

e.g. An equation that calculates the rate of change of temperature in the past, present or future

e.g. An equation that calculates the temperature in the past, present or future

2/ 37

## WEEK 6

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

3/ 37

## WEEK 6

▶ **Indefinite integration** (i.e. without limits) 3 _x_<sup>2</sup> _dx_ = _x_<sup>3</sup> + _d_ � ▶ **Definite integration** (i.e. with limits) 1 3 _x_<sup>2</sup> _dx_ = _x_<sup>3�1= 1</sup> �0 � 0<sup>= 13</sup><sup>_−_03</sup>

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

4/ 37

## WEEK 6

▶ The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay rate.

▶ This is a differential equation, and we used **separation of variables** to show that it has solution:

where _N_ 0 is the total number of nuclei in the sample at _t_ = 0.

5/ 37

## WEEK 7

- In this course, we focussed on Newton’s Second Law, which is given by the following equation:

where _F_ is the net force acting on a body that has a mass _m_ and therefore acceleration _a_ .

- This states acceleration of an object depends on the mass of the object and the amount of force applied.

- Newton’s second law can therefore be expressed as an ordinary differential equation:

6/ 37

## WEEK 7

- By examining the forces acting on objects we can formulate ODEs:

▶ Using separation of variables, we integrate these ODEs to calculate behaviours of our systems.

- Frictional forces will depend on the object, the system, its mass and how quickly it is moving.

7/ 37

## WEEK 8

- In some cases, we cant directly integrate by using the

<!-- Start of picture text -->
common laws, as we are faced with more complicated Derivative d dx y Integral y<br>combinations of functions such as  functions of 0 d<br>functions . constant constant × x  +  d<br>x 2<br>For example, what happens if we want to integrate x x n 2 +1+  d<br>x n n +1 +  d<br>dy e x e x +  d<br>y  = (3 x  + 2) 4 dx<br>� dx = � ke kx e kx +  d<br>This is where  integration by substitution  comes in. cos 1 x ( x ) sinln (( xx ) +) +  d d<br>Integration by substitution is essentially the reverse sin ( x ) −cos ( x ) +  d<br><!-- End of picture text -->

- For example, what happens if we want to integrate

- This is where **integration by substitution** comes in.

- Integration by substitution is essentially the reverse process of the chain rule in differentiation.

8/ 37

## WEEK 8

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

4. Differentiate with respect to the new variable _u_ :

9/ 37

## WEEK 8

### 5. Get an expression for _dx_ :

6. (If needed) Find the new limits of the integral:

When _x_ = _−_ 1 _, u_ = 3 _×_ ( _−_ 1) + 2 = _−_ 1 When _x_ = 1 _, u_ = 3 _×_ 1 + 2 = 5

7. Make the substitution in the original integral:

8. Integrate as usual:

10/ 37

## WEEK 8

- Hydrostatic Equation, with constant temperature requires integration via separation of variables:

- Hydrostatic Equation, with varying temperature requires integration by substitution:

11/ 37

## WEEK 9

- **Second-order ordinary differential equations** are ODEs that involve a **second-order**

   - **derivative** .

- We could devote an entire course looking at solving different types of second-order ODEs, but we will only concentrate on

where _a_ , _b_ and _c_ are constants.

- This is referred to as a **homogeneous, linear, second-order ODE** .

- Note that we can write the exact same expression using alternative notation as per the following equation:

12/ 37

## WEEK 9

- To solve these second-order ODEs we first write out the **auxiliary** equation:

- Find roots of the quadratic equations using:

- If _λ_ 1 and _λ_ 2 are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

- If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

13/ 37

## WEEK 9

- To find the values of the constants _A_ and _B_ , we use information such as _y_ = 0 and _y_ = 1 when _x_ = 0.

- These are called **initial conditions** , and they tell us the value of the solution and/or its derivatives at a specific point, allowing for a unique solution to the differential equation.

- This will lead us to solving simultaneous equations.

### ▶ Once we

14/ 37

## WEEK 9

- Fick’s and Fourier’s Laws describe the transfer of mass and heat.

- If we assume steady state, we get second-order ODEs which we can simply integrate twice

- We can use boundary conditions to solve this and find an expression.

- **Boundary value problems** differ from **initial value problems** as we specify upper and lower boundary conditions are specified (i.e, when _x_ = _x_ 0 and _x_ = _x_ 1).

- This gives us more information this means that we have to make the solution meet at both points.

15/ 37

## 2023-24 PAST PAPER

▶ Select the correct integral (i.e. � _f_ ( _x_ ) _dx_ ) of the following function ( _f_ ( _x_ )) from the list given below. Please show your working:

4 _x_<sup>3</sup> _−_ 2 _x_ + 5

- (a) _x_<sup>4</sup> _− x_<sup>2</sup> + 5 _x_ + _C_

- (b) _x_<sup>4</sup> _−_ 2 _x_<sup>2</sup> + 5 _x_ + _C_

- (c) _x_<sup>4</sup> _− x_<sup>2</sup> + 5 + _C_

- (d) 3 _x_<sup>4</sup> _− x_<sup>2</sup> + 5 _x_

16/ 37

## 2023-24 PAST PAPER

### ▶ Perform indefinite integration:

- So the answer is (a).

17/ 37

## 2023-24 PAST PAPER

▶ Integrate the following expression and give your answer to 3 decimal places:

### ▶ Perform definite integration:

18/ 37

## 2023-24 PAST PAPER

- A body of mass _m_ kilograms rests on a slope that has an angle of inclination of 30 degrees.

▶ Calculate the speed of this body after 10 seconds, assuming the initial velocity is 0 _m/s_ and the earths gravitation constant is _g_ = 9 _._ 8. For this problem you need to write all the forces acting on the body in the form of Newtons second law:

Where _F_ is the total force acting on a body of mass _m_ , leading to the change in velocity<sup>_<u>dv</u>_</sup> _dt_<sup>.You</sup> can then integrate this equation and evaluate it the given initial conditions

19/ 37

## 2023-24 PAST PAPER

- The total forces acting towards the earth is _F_ = _mg_ but as it is in on an incline, we need to take account for this. Using trigonometry, we can write these as follows:

_F_ = _mg_ sin(30)

- Write out the full ODE:

<!-- Start of picture text -->
m dv = mg  sin(30)<br>dt<br>dv<br>= g  sin(30)<br>dt<br><!-- End of picture text -->

20/ 37

## 2023-24 PAST PAPER

- At time _t_ = 0, velocity is 0 _m/s_ and at time 10, velocity is _v_ . Use separation of variables and integrate:

21/ 37

## 2023-24 PAST PAPER

- At time _t_ = 10, a force is suddenly applied to the body but opposite to the direction of travel.

- We are told this force is directly proportional to the mass _m_ via a coefficient _α_ where _α_ = 8 _._ 5.

- The new force is thus given as _F_ = _αm_ . Draw a schematic diagram that displays all the forces

now acting on the body

- Determine how long it takes for the vehicle to stop, to 2 decimal places.

22/ 37

## 2023-24 PAST PAPER

23/ 37

## 2023-24 PAST PAPER

- There is a force _F_ = _αm_ now acting in the opposite direction of travel so the total forces acting on the object are:

- Write out the new ODE:

<!-- Start of picture text -->
m dv = mg  sin(30)  − αm<br>dt<br>dv<br>= g  sin(30)  − α<br>dt<br><!-- End of picture text -->

24/ 37

## 2023-24 PAST PAPER

▶ At time _t_ = 0, velocity is 49 _m/s_ and at time _t_ , velocity is 0 _m/s_ . Use separation of variables and integrate:

25/ 37

## 2023-24 PAST PAPER

- The following equation described the rate of change in a population _P_

Where _α_ is a coefficient that determines a contribution according to births, whilst _β_ a coefficient that determines the contribution from natural deaths.

- Integrate the equation to arrive at the following equation that describes how _P_ varies with time, if _P_ 0 represents the population value when _t_ = 0:

26/ 37

## 2023-24 PAST PAPER

▶ Use separation of variables and indefinite integration:

▶ At time _t_ = 0, _P_ = _P_ 0:

- Substitute and rearrange:

27/ 37

## 2023-24 PAST PAPER

### ▶ We are now told the birth rate is constant, such that:

Where _ψ_ represents this constant. To integrate this expression, you will need to use integration using a substitution, creating a new variable _u_ = _ψ − βP_ equal to arrive at the following expression:

28/ 37

## 2023-24 PAST PAPER

- Use separation of variables:

- Let’s use _u_ = _ψ − βP_ as a substitution. Lets rearrange for _P_ , differentiate in terms of _u_ and find an expression for _dP_ :

- Use these to make the substitution:

29/ 37

## 2023-24 PAST PAPER

### ▶ Now we can evaluate using the basic laws of integration:

▶ At time _t_ = 0, _u_ = _U_ 0 = _ψ − βP_ 0:

- Substitute and rearrange:

30/ 37

## 2023-24 PAST PAPER

31/ 37

## 2023-24 PAST PAPER

- The hydrostatic equation allows us to calculate the variation in pressure _P_ with height _z_ in the atmosphere:

Where _Rα_ = 287 _Jkg_<sup>_−_1</sup> _K_<sup>_−_1</sup> . We have been told that the value for _α_ could be either 0.01 or 0.02. We want to know what difference this makes in the final pressure at a height of 1400m.

- Integrate the hydrostatic equation using a substitution, when _α_ = 0 _._ 01. This should lead you to derive the following value for the pressure at 1400m:

32/ 37

## 2023-24 PAST PAPER

- At _z_ = 0, _P_ = 100000 and at _z_ = 1400, _P_ = _P_ . Use separation of variables:

- Use integration by substitution with _u_ = _Ts − αz_ as a substitution. Lets rearrange for _z_ , differentiate in terms of _u_ and find an expression for _du_ :

- Alter the limits:

33/ 37

## 2023-24 PAST PAPER

### ▶ Use these to make the substitution:

### ▶ Now we can evaluate using the basic laws of integration:

34/ 37

## 2023-24 PAST PAPER

### ▶ Rearrange for final expression:

▶ Plugging in _α_ = 0 _._ 01, _Ts_ = 290 and _Rα_ = 287 gives us:

35/ 37

## 2023-24 PAST PAPER

▶ What is the percentage difference in pressure at 1400m when we change _alpha_ = 0 _._ 01 to _α_ = 0 _._ 02. Use 5 significant digits for the value of _P_ at 1400m as we have done for part (a) and 1 decimal place for the percentage difference.

36/ 37

## 2023-24 PAST PAPER

- In the previous part we arrived at the solution:

- Percentage difference is given by:

100 _×_<sup>84083</sup><sup>_−_84454</sup> = _−_ 0 _._ 4% 84454

37/ 37
