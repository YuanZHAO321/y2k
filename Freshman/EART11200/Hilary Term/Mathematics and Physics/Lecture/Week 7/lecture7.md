---
title: "lecture7"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 7/lecture7.pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 7 Lecture - Integration using Newton’s Laws_

1/ 20

## LAST WEEK...

- Integration is the **reverse** of differentiation.

- Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values.

- The � symbol was introduced by Gottfried Wilhelm Leibniz in the 17th century to represent summation of infinitely many infinitesimally small quantities.

e.g. An equation that calculates the rate of change of temperature in the past, present or future

e.g. An equation that calculates the temperature in the past, present or future

2/ 20

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

3/ 20

## LAST WEEK...

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

4/ 20

## LAST WEEK...

▶ The equation describing radioactive decay is:

▶ This is a differential equation, and we used **separation of variables** to show that it has solution:

where _N_ 0 is the total number of nuclei in the sample at _t_ = 0.

5/ 20

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

6/ 20

## INTENDED LEARNING OUTCOMES

- (1) Understand and describe Newton’s Laws of Motion to explain the relationship between force, mass, and acceleration in physical systems.

- (2) Apply Newton’s Second Law to formulate ordinary differential equations (ODEs) that model the motion of objects in various contexts.

- (3) Use integration to solve ODEs and determine physical behaviour in real-world problems.

7/ 20

## NEWTON’S LAWS

- Before the 20th century, our understanding of the physical world was built entirely on classical mechanics. More specifically - **Newtonian Physics** .

- This framework emerged from the collective efforts of the

   - "Scientific Revolution".

- Still an active area of theoretical and experimental physics.

- In the Principia, Newton formulated **three laws** to explain planetary motion, in order to explain why the orbits of the planets are ellipses rather than circles.

- These laws extend far beyond planetary motion, offering a framework for understanding force and motion.

8/ 20

## NEWTON’S LAWS

- **Law of Inertia:** A body at rest or moving at a constant speed in a straight line will remain in that state unless acted upon by an external force.

- **Law of Force and Momentum:** The rate of change of a body’s momentum is directly proportional to the force applied, with the change occurring in the same direction as the force (i.e. if a force acts on a body, that body will experience a change in momentum).

▶ **Law of Action and Reaction:** When two bodies interact, they exert forces on each other that are equal in magnitude and opposite in direction. You will have likely come across this law before; also known as the law of action and reaction.

9/ 20

## NEWTON’S SECOND LAW

- In this course, we focus on Newton’s Second Law, which is given by the following equation:

where _F_ is the net force acting on a body that has a mass _m_ and therefore acceleration _a_ .

▶ Acceleration of an object depends on the mass of the object and the amount of force applied.

- In Week 5, we discussed second-order derivatives and observed that acceleration ( _a_ ) is the rate of change of velocity ( _v_ ), while velocity ( _v_ ) is the rate of change of position or distance ( _x_ ).

- Newton’s second law can therefore be expressed as ordinary differential equations:

10/ 20

## NEWTON’S SECOND LAW

- To help understand how this works, imagine a plane moving through the atmosphere.

- The plane has a constant mass _m_ and its momentum depends on its velocity _V_ , which is

controlled solely by the plane (i.e., there are no external forces acting on it).

- The change in velocity between any two time points is _m_ ( _V_ 1 _− V_ 0). If we define force as the rate of change of momentum with respect to time, then:

- This resembles the calculation of a gradient from Week 1!

11/ 20

## NEWTON’S SECOND LAW

- As seen in Chapters 2, taking the limit as _t_ 1 _− t_ 0 _→_ 0, this becomes us the derivative:

- By formulating the total forces acting on an object, we can then solve the ODE to as a function of time to tell us something about the processes.

- How do we determine the forces acting on a body, thus write our ODE?

12/ 20

## EXAMPLE: BALL FALLING IN A VACUUM

- Consider an object falling in a vacuum.

▶ The object experiences only Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center.

- Therefore we see that _Ff_ = 0 and _Fg_ = _mg_ where _g_ = 9 _._ 8 is

   - the gravitational constant.

- If we assume an object is falling in a vacuum, can we prove that a brick fall the same distance as a feather in the same amount of time? Yes!

13/ 20

## EXAMPLE: BALL FALLING IN A VACUUM

- We add up all the forces in the direction of travel and minus

the forces in the opposite direction:

_F_ = _mg_

- This allows us to model the motion using a first-order

ordinary differential equation (ODE) for velocity:

_mg_ = _m_<sup>_dv_</sup> _dt_

- Canceling the mass ( _m_ ) gives:

_dv dt_<sup>=</sup><sup>_g_</sup>

14/ 20

## EXAMPLE: BALL FALLING IN A VACUUM

▶ Using separation of variables, we can re-write our expression as an integral so we can calculate velocity as a function of time.

- We integrate to find the velocity, assuming the object starts from rest ( _v_ = 0) at _t_ = 0:

- Thus, the velocity of any object in a vacuum increases linearly with time, regardless of its mass, therefore, all objects fall at the same velocity with respect to time.

15/ 20

## EXAMPLE: BALL FALLING IN A VACUUM

▶ However, we want to show that all objects fall the same distance with respect to time. Remember that, velocity is the rate of change for the distance so we get the following ODE

- Integrating again, and assuming the object starts from _x_ = 0 at _t_ = 0, we get:

▶ This shows that all objects fall the same distance (quadratically) over the same amount of time in a vacuum, regardless of their mass.

16/ 20

## EXAMPLE: OBJECT ON AN INCLINE

- Consider an object resting on an incline.

- The object experiences only Earth’s gravitational force,

which acts vertically from the center of the object toward the Earth’s center (i.e. _Fg_ = _mg_ )

- The forces can be resolved into two components:

   - the force acting perpendicular to the slope ( _F_ 1).

   - the force dragging the block down the slope ( _F_ 2).

- What is the magnitude of both _F_ 1 and _F_ 2?

- Using trigonometry, we can write these as follows:

_F_ 1 = _mg_ cos( _θ_ ) _F_ 2 = _mg_ sin( _θ_ )

17/ 20

## EXAMPLE: OBJECT ON AN INCLINE

- Assuming that there is no friction acting against the object, we expect the block to travel down the incline.

- We add up all the forces in the direction of travel and minus

the forces in the opposite direction:

- This means the force _F_ 2 can be used to formulate our ODE:

- Canceling the mass ( _m_ ) gives:

18/ 20

## EXAMPLE: OBJECT ON AN INCLINE

- Using separation of variables, we can integrate and calculate the velocity as a function of time. We integrate to find the velocity, assuming the object starts from rest ( _v_ = 0) at _t_ = 0:

- Thus, the velocity of an object on an incline increases linearly with time.

- The rate of increase depends on the incline’s angle ( _θ_ ) but is independent of the object’s mass.

19/ 20

## NEWTON’S SECOND LAW

### ▶ Both of these examples are simplified.

   - Could we derive a general expression for _v_ as a function of _t_ ?

   - What if the object was moving at _t_ = 0?

   - What if there was another force acting in the opposite direction?

- Frictional forces will depend on the fluid the object is moving through, its mass and how quickly it is moving.

- You will see examples of this in the practical and the exercises.

20/ 20
