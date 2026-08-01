---
title: "Chapter6"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 6/Chapter6.pdf"
type: pdf
---

# 6. Introduction to Integration

## 6.1 Overview

Throughout Chapters 1–5, we considered at differentiation as a topic. This is the process of finding a rate of change (or gradients) of functions or processes. However, there may be times where we want to do the opposite, i.e. we know the rate of change but want to know the volume or total change over an interval. For example, we might know how fast a car is traveling and we want to know how far that car has traveled over time. This is where **integration** comes in.

## 6.2 Integration as the reverse of differentiation

Integration is the **reverse** of differentiation (Figure 6.1). Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values. For example, if a derivative function tells us how much the volume of water in a tank is changing over time, integrating that function tells us how much water is in the tank at a given time or how much the volume of water has changed over a specific time period.

To integrate a differential equation therefore requires us to reverse the steps taken to get to that point. At first glance, this seems like an impossible task since it is likely we did not generate the differential equation. However you will start to recognise forms of equations and what steps you therefore need to carry out.

Let us keep the water example for now to explore this using a graph. If we consider the

94

Chapter 6. Introduction to Integration

**Figure 6.1:** Interplay between differentiation and integration throughout this course.

flow rate of water through a hole we might obtain a graph similar to Figure 6.2. The top graph plots the rate of change as a function of time, thus the derivative function. Look at the middle part, between 30 and 70 seconds. Here the rate of change is constant. So, after 1 second, the water has increased by a fixed amount. In the next second, the water increases by the same amount. Now we can consider working out the area under the curve to arrive at the total amount. Indeed, if we want to describe how the volume of water in the system changes with time, _t_ , then we can calculate it from the above graph by finding the area under the graph from _Time_ = 0 to any time, _t_ . For Fig. 6.2 we can find the area by adding up areas of triangles and rectangles.

Often flow rate curves are not as simple as in Fig. 6.2. Fig. 6.3 shows the curve _f_ ( _x_ ) = _→_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ and a schematic of how to estimate the area under the curve. Basically it shows that we can split the area into lots of smaller rectangles, with a base of length ! _x_ and a height equal to _f_ ( _x_ ), the value of the function at _x_ . The area of each rectangle is then _f_ ( _x_ ) _↑_ ! _x_ and the area of the curve is the sum of all of these rectangles. This is a **numerical approximation** method, similar to central differences method for differentiation, representing a manual integration of the function.

We can use (analytical) _integration_ to a function that describes the area under the curve. In this case the function<sup>_→_</sup><sup><u>0</u></sup><sup>_<u>.</u>_</sup><sup><u>1</u></sup><sup>_<u>x</u>_3</sup> + 5 _x_<sup>2</sup> describes the area under the curve between 3 _x_ = 0 and _x_ . This is shown in the bottom graph of Figure 6.3.

Because integration can be seen as a _summing up_ of lots of smaller rectangles we write it formally with an S-shaped symbol:

95

<!-- Start of picture text -->
300<br>250<br>200<br>150<br>100 Area=base ×  height<br>50 Area=0.5base ×  height × Area=0.5base ×  height ×<br>0<br>0 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>4<br>2  x 10<br>1.5 Area under the curve<br>1<br>0.5<br>0<br>0 10 20 30 40 50 60 70 80 90 100<br>Time (seconds)<br>Flow rate (milli−litres per second)<br>Total volume (milli−litres)<br><!-- End of picture text -->

**Figure 6.2:** Top shows a graph of flow rate of a substance vs time; bottom shows the volume of that substance vs time (i.e. the area under the top curve). We see that the volume increases at a non-constant rate at first, but between 30 and 70 seconds the volume increases according to a straight line. After 70 seconds the volume increases at a non-constant rate, before leveling off

**Figure 6.3:** Top shows the function _f_ ( _x_ ) = _→_ 0 _._ 1 _x_<sup>2</sup> + 10 _x_ . The schematic shows a way of estimating the area under the curve by dividing the area into lots of rectangles. Bottom shows a function describing the area from _Time_ = 0 to a later time, _t_ .

96

Chapter 6. Introduction to Integration

here the � symbol represents a ‘summing up’. The _dx_ represents the length of the base of each rectangle (i.e. ! _x_ ) and the sub and super-scripts on the � are known as _limits of integration_ . In this example it means find the area under the curve between 0 and _x_ .

The _integral_ of some simple functions of _x_ are shown below:

|Function|Integral|
|---|---|
|constant|_constant ↑x_+_d_|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|2_x_<sup>4</sup>|2_x_<sup>5</sup><br>5 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|

where _d_ is a constant. So we see that given these simple functions of _x_ we can calculate the integral of them by **raising the power of** _x_ **by 1** and **dividing by the new power that** _x_ **is raised** . Why do we add the constant, _d_ ? Well, integration is the opposite of differentiation (remember differentiation of a constant is zero) and differentiation "loses" any constant that might have been present in the original function so we add this in. For standard integration we cannot say what the constant is: it can take on any value so we just call it a **constant** . For this reason it is called . **indefinite integration**

To find the **area under a curve** we have to perform between limits. This means that we calculate the integral (as in the table above) then evaluate the integral for two values of _x_ , and calculate the difference.

**Example 6.1** : Let’s find the area under the curve _y_ = _x_<sup>2</sup> from _x_ = 1 to _x_ = 2. We write the integration out as follows:

note that we calculate the integral and then evaluate the function by putting in both limits and calculating the difference.

97

Note that when calculating a difference the constant in the integration, _d_ , disappears so we do not have to consider it.

|Differential equation <sup>_dy_</sup><br>_dx_|Integral,_y_|
|---|---|
|constant|_constant ↑x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup><br>_ax_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_ax_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_)+_d_|
|_cos_(_x_)|_sin_(_x_)+_d_|
|_sin_(_x_)|_→cos_(_x_)+_d_|

## 6.3 Solving Ordinary Differential Equations (ODEs)

Now we can change our narrative a little with regards to solving problems in Physics. So far, we have been given _f_ ( _x_ ) and asked to find<sup>_d_</sup> _dx_<sup>_<u>f</u>_, but now we are starting with</sup><sup>_d_</sup> _dx_<sup>_<u>f</u>_instead.</sup> We often refer to<sup>_d_</sup> _dx_<sup>_<u>f</u>_as</sup><sup>**Ordinary Differential Equations (ODEs)**.</sup>

The theoretical base of many of the processes we are interested in are written in the form of ODEs. To predict values or properties in the past or future, we can integrate ODEs either without limits, or between specific limits. In this Chapter, we solve the ODEs that describe radioactive decay and Newtons laws of motion, following some algebraic exercises.

The radioactive decay and hydrostatic equation have the same algebraic formulation. They are both equations that describe a logarithmic change in one variable as a function of another. Why is that? By looking at the **ODE** that describes a rate of change:

then we know the solution to this general equation will take the form of the following equation:

In the following, we relate the derivative with the analytical integrals. For more information you may refer to Chapter 11 that covers all of the physical theories we cover in this course.

98

Chapter 6. Introduction to Integration

**Example 6.2: The radioactive decay equation.** For _!_ and _∀_ decay we can apply the radioactive decay equations. The law states that the number of decays per unit time is proportional to the number of unstable nuclei:

where _# N_ is the number of unstable nuclei. This is a constant for a specific isotope and kind of law is quite common in physics. It is to be expected since if you have more unstable nuclei you would expect to observe more decays per second and vice versa. Another statement of this law is that the number of unstable nuclei decays away with time:

where _N_ 0 is the number of unstable nuclei at time _t_ = 0. The constant _#_ is used to characterise how quickly the unstable nucleus decays. To get this solution, we use a technique called **separation of variables** . We rearrange the decay equation so that all _N_ ’s are on one side and all _t_ ’s are on the other and then integrate both sides:

_N_

Then multiply both sides by _dt_

Then integrate both sides

The integral � <u>1</u> _x_<sup>_dx_is equal to ln</sup><sup>_x_so we have</sup>

and if we say at _t_ = 0, _N_ = _N_ 0 we get that _c_ = ln _N_ 0, we therefore obtain

as the solution to Newton’s radioactive equations.

99

**Example 6.3: The hydrostatic equation.** The density of air depends on the pressure, _<u>P</u> P_ , and temperature of the air, _T_ , (through the ideal gas law): _∃_ = _RaT_<sup>, where</sup><sup>_Ra_= 287 J</sup> kg<sup>_→_1</sup> K<sup>_→_1</sup> . So we can write:

We can use separation of variables and integration again to show that the solution to this ODE is:

In actual fact the assumption that the temperature is constant is not true as it usually decreases with height in the atmosphere at about 10<sup>_↓_</sup> C km<sup>_→_1</sup> (i.e. a drop of 10<sup>_↓_</sup> C for every km). When we take into account that temperature drops with altitude the hydrostatic equation becomes:

which has an analytical solution of:

but we need some fancier integration techniques, which we will see later, to be able to show this!
