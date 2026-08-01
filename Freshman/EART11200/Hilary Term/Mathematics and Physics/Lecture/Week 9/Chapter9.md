---
title: "Chapter9"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 9/Chapter9.pdf"
type: pdf
---

# 9. Second-Order Ordinary Differential Equations

## 9.1 Overview

In Chapters 6–8, we explored the process of integration, which is the inverse of differentiation and a powerful tool for calculating the area under curves. This has been really useful in understanding various properties and behaviors of systems, such as those described by Newton’s Laws of Motion. However, our focus so far has been primarily on first-order derivatives (i.e., _dx_<sup>_dy_).In this Chapter, we conclude our study of integration by examining</sup> **second-order ordinary differential equations** .

## 9.2 Second-order Differential Equations

_S_ econd-order ordinary differential equations are ordinary differential equations (ODEs) that involve a _second-order derivative_ . We could devote an entire course looking at solving different types of second-order ODEs, a general form is given by:

Here, _a_ ( _x_ ), _b_ ( _x_ ), _c_ ( _x_ ) and _d_ ( _x_ ) are general functions of the variable _x_ , referred to as coefficients. In fact, we can simplify the above expression by writing _a_ ( _x_ ), _b_ ( _x_ ) and _c_ ( _x_ ) as constant coefficients (which we will only ever look at in this course):

This equation is classified as a **linear second-order ODEs** because the second derivative, _d_<sup>2</sup> _<u>y</u>_<sup>If the value of</sup><sup>_d_(</sup><sup>_x_) = 0 we can also say the equation is</sup> _dx_<sup>2, is raised to the power of 1.</sup> **homogeneous** , whilst if _d_ ( _x_ ) _→_ = 0 the equation is calles **non-homogeneous** . In this course

140

Chapter 9. Second-Order Ordinary Differential Equations

we will briefly look at methods for solving **homogeneous, linear, second-order ODEs** which resemble the following expression:

Please note that we can write the exact same expression using alternative ODE notation as per the following equation:

where _a_ , _b_ and _c_ remain the same constants. In every problem so far, we have wanted to arrive at a general analytical solution from integrating a differential equation. How do we deal with a second-order ODE as above?

Fortunately, there is a general form we can use if the equation to be solved has the same form. Notice how it looks like we might be able to use the approach to solving quadratic equations, but how do we find a value for _y_ . Lets just jump to an educated guess and assume the expression for _y_ is going to be:

where _!_ is a constant with an unknown value. If we differentiate (twice) this expression we can arrive at two expressions:

Lets now substitute these expressions back into our general differential equation as follows:

Because _e_<sup>_!x_</sup> cant be zero, it is safe to divide through to acquire a quadratic in _!_ :

This is called the **auxiliary** equation or **characteristic** equation. When you encounter a **homogeneous second-order ODE** , you can jump straight to this point and follow the procedure below.

Looks like we have a quadratic equation. If can solve this, we can get to a value of _!_ which we can use to find a solution to the second-order ODE. Remember that we can solve (or find roots of) quadratic equations using the following formula:

141

When we solve a quadratic expression we will arrive at 2 roots, which we can call _!_ 1 and _!_ 2.

Since there are two roots to the auxiliary equation, the general solution to the second-order ODE will be a combination of the two function. If _!_ 1 and _!_ 2 are real and not equal ( _!_ 1 _→_ = _!_ 2 then we can write a general solution as:

If our two roots are real and equal (i.e. _!_ 1 = _!_ 2) then we use the formula:

We don’t consider what happens when the two roots are not real (i.e. _b_<sup>2</sup> _↓_ 4 _ac <_ 0) in this course. In both general solutions, we have added two new constants _A_ and _B_ as we are combining multiple solutions we need to know how much each will contribute to the final solution. To calculate their values, we need some initial conditions or boundary conditions in _y_ (we’ll see this later).

**Example 9.1** : Imagine we are asked to solve the following equation:

We can see that this is a linear, homogeneous, second-order ODE. Firstly, we write out the auxiliary equation:

Secondly, we need to check what the values for _!_ 1 and _!_ 2 are to understand what solution is needed. To do this, by using the **auxiliary** equation we know we have a quadratic as follows. Find the roots ( _!_ 1 and _!_ 2) of this equation:

so we have roots _!_ 1 = 1 and _!_ 2 = 5. Since they are real and distinct then the solution will have form

142

Chapter 9. Second-Order Ordinary Differential Equations

Thirdly, we plug the values of _!_ 1 and _!_ 2

and this is our general solution to the problem.

The next question is how to calculate the values for constants _A_ and _B_ ? We need more information to constrain these values such as _y_ = 0 and _y_ = 1 when _x_ = 0. These are called **initial conditions** , and they tell us the value of the solution and/or its derivatives at a specific point, allowing for a unique solution to the differential equation. For example, for<sup>_dyf_(</sup><sup>_x_), an initial condition might be</sup><sup>_y_=</sup><sup>_y_0 at</sup><sup>_x_=</sup><sup>_x_0.You will have seen examples</sup> _dx_<sup>=</sup> when solving the radioactive decay equation, hydrostatic equation and Newton’s Laws of Motion. This will lead us to solving simultaneous equations. Do you recall how you solve simultaneous equations? If we want to calculate two unknowns we need to formulate two expressions that provide us with an ability to re-arrange and isolate.

**Example 9.2** : Let’s return to the previous example:

We wrote out the auxiliary equation and found the roots to arrive at the general solution our general solution to the problem:

Suppose that we are told that _y_ = 0 and _y_<sup>_↑_</sup> = 1 when _x_ = 0 then we use this information to find _A_ and _B_ . Write out _y_ and _y_<sup>_↑_</sup> :

Plug in the initial conditions in to _y_ and _y_<sup>_↑_</sup> to get:

This leaves us with a system of simultaneous equations which we can solve. Take Equation 9.1 from Equation 9.2 gives us:

Substitute _B_ =<sup><u>1</u></sup> 4<sup>into Equation 9.1 gives us:</sup>

Then the full general solution is given by:

143

## 9.3 Applied boundary value problems and steady-state

In the last section, we dived into general solutions of second-order ODEs and captured some definitions and an approach to solve special cases. In this section, we can ground some of this is reality and take a look look at how these types of equations are used in real-world physical theories, therefore, then when we solve second-order ODEs, it tells us about the state of the system we are interested in. We also get back to the process of integration rather than working through a known solution as the previous section.

Examples of second-order ordinary differential equations are:

- <sup>**Kinematics**:Acceleration (</sup><sup>_a_) as the rate of change of the rate of change of location</sup> ( _x_ ) in time ( _t_ ),<sup>_<u>d</u>_</sup> _dt_<sup>22</sup><sup>_<u>x</u>_.</sup>

- <sup>**Forces and motion**:Newton’s second law of motion:</sup><sup>_F_=</sup><sup>_ma_.</sup>

- <sup>**Fick’s law**:Steady-state mass diffusion:</sup><sup>_<u>d</u>_</sup> _dt_<sup>2</sup><sup>_<u>C</u>_2= 0.</sup>

- <sup>**Fourier’s law**:Steady-state heat transfer:</sup><sup>_<u>d</u>_</sup> _dt_<sup>2</sup><sup>_<u>T</u>_2= 0.</sup>

These equations look different to the previous section. In some ways, they look easier because they offer us a starting point to begin the process of integration. Indeed, to solve second-order ODEs as we have here, we often have to integrate the equation twice. Firstly to get the first gradient and secondly to get the solution. Let’s look at some examples.

**Example 9.3** : Suppose we want to use Newton’s second law of motion to derive the equation of motion (distance versus time) of an object moving down a ramp inclined at 30<sup>_≃_</sup> , starting with velocity _v_ = 0. We will not consider air resistance or friction. Remember that (see Chapter 7 Example 2) if the gravitational force is given by _mg_ (where _m_ is the object’s mass and _g_ is the gravitational constant) then the force dragging the block down the slope ( _F_ 2) and the normal force ( _F_ 1) can be written as:

Furthermore, remember that when using Newton’s second law of motion, we need to determine the net forces that pull or push a body along a surface. Why are second-order ODEs relevant here? Remember, we can write Newtons second law of motion as follows:

Each expression is equivalent to the other. If we integrate the second equation ( _F_ = _m_<sup>_<u>dv</u>_</sup> _dt_<sup>),</sup> we can arrive at an expression of velocity ( _v_ ) as a function of time ( _t_ ). However, we have been asked to derive an expression of distance ( _x_ ) as a function of time. This means we

Chapter 9. Second-Order Ordinary Differential Equations

144

would need to integrate our expression for _v_ again, given that _v_ =<sup>_<u>dx</u>_</sup> _dt_<sup>.To solve this problem</sup> we have to integrate twice. Lets see this in action. As there is no friction acting on object the total forces on the object are _F_ = _mg_ sin (30<sup>_≃_</sup> ). We integrate to get the velocity ( _v_ ) of this object ( _v_ from 0 to _v_ and _t_ from 0 to _t_ ):

We integrate again to get the distance travelled ( _x_ ) of this object ( _x_ from 0 to _x_ and _t_ from 0 to _t_ ):

So the velocity increases linearly and the distance quadratically in this problem.

The ODEs that have been covered so far are called **initial value problems** . This is where we specify some initial values (i.e. when _x_ = 0, _v_ = 0, _t_ = 0), and we solve the ODE to find something about our process in the future or a certain distance away. Other kinds of ODEs are called **boundary value problems** , where upper and lower boundary conditions are specified (i.e, when _x_ = _x_ 0 and _x_ = _x_ 1). This gives us more information this means that we have to make the solution meet at both points. The two we will cover are Fick’s and Fourier’s laws, which are laws of mass diffusion and heat conduction.

**Example 9.4: Fourier’s Law.** Fourier stated that the flux of heat through a substance is proportional to the negative gradient of temperature in the substance (i.e. heat flows from hot to cold). We can express this, known as Fouriers law, as a differential equation:

where _T_ is the temperature and _x_ the distance variable.

**Example 9.5: Fick’s Law.** Fick also found that the law that governs transport of mass by _Brownian motion_ (i.e. random thermal motion) moves from high concentrations to low concentrations. We can express this, known as Fick’s law, as a differential equation:

where _J_ is the mass _C_ is the concentration of mass (e.g. mass of pollutant / gas or particulate) and _D_ is a diffusion coefficient which depends on the properties of the substance that is diffusing.

145

For both of these equations, we assume steady state conditions. Remember from Chapter 5, a system is in steady-state when the key variables that describe the system’s behavior do not change over time (i.e. _f_ ( _x_ ) = _c_ where _c_ is constant). See Figure 9.1, consider the situation where water is poured into a container which has an outlet part on the side of the container. At first when the water level is below the outlet, the water level in the container rises with time. However, when the water level reaches a certain height, the amount of water entering the tank and the amount of discharged water are balanced and the water level remains constant. The system has reached a steady state. If the system is in steady state, we can differentiate again to get a derivative equal to zero (i.e.<sup>_d_</sup> _dx_<sup>_<u>f</u>_= 0.In Fick’s and</sup> Fourier’s Law, we specify that the rate of change remains constant, either over space or time, we can rewrite them as:

These are **second-order ODEs** . Similar to Exercise 3, we will need to integrate them twice to arrive at expressions for concentrations and temperatures as a function of distance, however as you will see in the exercises, we will specify boundary conditions rather than intial conditions.

**Figure 9.1:** Diagram showing a system in (a) transient state and (b) steady state.
