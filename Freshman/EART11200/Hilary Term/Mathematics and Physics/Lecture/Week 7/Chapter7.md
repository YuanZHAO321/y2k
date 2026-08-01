---
title: "Chapter7"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 7/Chapter7.pdf"
type: pdf
---

# 7. Integration using Newton’s Laws

## 7.1 Overview

In Chapter 6, we presented Integration as the reverse of differentiation. We discussed **definite** and **indefinite** integration and solving **ordinary differential equations (ODEs)** . We continue that here but focus on Newtons laws of motion as a special case.

## 7.2 Newtons laws of motion

Before the 20th century, our understanding of the physical world was built entirely on classical mechanics. More specifically - **Newtonian Physics** . This framework emerged from the collective efforts of the "Scientific Revolution", spanning figures like Nicolaus Copernicus, Galileo Galilei, and Isaac Newton.

`Philosophiae Naturalis Principia Mathematica (1687)` , commonly known as the `Principia` . In 1543, Nicolaus Copernicus proposed a heliocentric model of the universe, placing the Sun rather than Earth at its center. This radical idea laid the groundwork for subsequent contributions by Galileo, Johannes Kepler, and René Descartes, who collectively challenged and replaced the Aristotelian worldview.

In the `Principia` , Newton formulated **three laws** to explain planetary motion, in order to explain why the orbits of the planets are ellipses rather than circles. These laws, however, extend far beyond planetary motion, offering a universal framework for understanding force and motion. Newton’s laws are as follows:

108

Chapter 7. Integration using Newton’s Laws

1. **Law of Inertia:** A body at rest or moving at a constant speed in a straight line will remain in that state unless acted upon by an external force.

2. **Law of Force and Momentum:** The rate of change of a body’s momentum is directly proportional to the force applied, with the change occurring in the same direction as the force (i.e. if a force acts on a body, that body will experience a change in momentum). This is captured in equations you see throughout this course.

3. **Law of Action and Reaction:** When two bodies interact, they exert forces on each other that are equal in magnitude and opposite in direction. You will have likely come across this law before; also known as the law of action and reaction.

In a number of our problems, we solve Newtons second law to predict how fast or far a body will travel down an incline. Since gravity is pulling the body downwards, why doesn’t the body move through the surface? Well, in very simplistic terms the surface applies an equal and opposite force to the body resting on it. In reality, molecular forces that dictate the properties of both the object and surface also play a role but these laws are adequate to explain our observed motion.

## 7.3 Newtons second law of motion

For the remainder of this Chapter, we focus on Newton’s second laws. In this law, we see that acceleration of an object depends on the mass of the object and the amount of force applied. This concerns a change in momentum. Newton’s second law of motion is given by the following equation:

where _F_ is the net force acting on a body that has a mass _m_ and therefore acceleration _a_ .

In Chapter 5, we discussed second-order derivatives and observed that acceleration ( _a_ ) is the rate of change of velocity ( _v_ ), while velocity ( _v_ ) is the rate of change of position or distance ( _x_ ).Newton’s second law can therefore be expressed as an ordinary differential equation:

where these expressions are equal, and we use the fact that _a_ = _v dx_<sup>_<u>dv</u>_for the final expression</sup> (because _v_ =<sup>_<u>dx</u>_</sup> _dt_<sup>, so</sup><sup>_v_</sup> _dx_<sup>_<u>dv</u>_=</sup><sup>_<u>dv</u>_</sup> _dt_<sup>, which is equal to</sup><sup>_a_).</sup>

To help understand how this works, imagine a plane moving through the atmosphere. The plane has a constant mass _m_ and its momentum depends on its velocity _V_ , which is controlled solely by the plane (i.e., there are no external forces acting on it). The change in velocity between any two time points is _m_ ( _V_ 1 _→V_ 0). If we define force as the rate of

109

change of momentum with respect to time, then:

This resembles the calculation of a gradient from Chapter 1! As seen in Chapters 2, taking the limit as _t_ 1 _→ t_ 0 _↑_ 0, this becomes us the derivative:

By formulating the total forces acting on an object, we can then solve the ODE to as a function of time to tell us something about the processes.

In multiple cases we are presented with problems where an object experiences multiple forces, acting in multiple directions. We will always need to ensure we understand the balance of each for as an algebraic formulation. Let’s work through two examples which you can see Figure 7.1.

**Figure 7.1:** Schematic illustrating forces acting on a body (left) falling downwards and (right) placed on an incline

**Example 7.1: Object Falling in a Vacuum .** Consider an object falling in a vacuum, as shown on the left side of Figure 7.1. In this scenario, the object experiences only Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center. If we assume an object is falling in a vacuum, can we prove that a brick fall the same distance as a feather in the same amount of time? Yes! In a vacuum, there is no air resistance, so the only force acting on the object is gravity, proportional to its mass ( _mg_ ). This allows us to model the motion using a first-order ordinary differential equation (ODE) for velocity:

Canceling the mass ( _m_ ) gives:

Using separation of variables, we can re-write our expression as an integral so we can calculate velocity as a function of time. We integrate to find the velocity, assuming the

110

Chapter 7. Integration using Newton’s Laws

object starts from rest ( _v_ = 0) at _t_ = 0:

Thus, the velocity of any object in a vacuum increases linearly with time, regardless of its mass, therefore, all objects fall at the same velocity with respect to time. However, we want to show that all objects fall the same distance with respect to time. Remember that, velocity is the rate of change for the distance

Integrating again, and assuming the object starts from _x_ = 0 at _t_ = 0, we get:

This final expression for distance shows that all objects fall the same distance (quadratically) in the same amount of time in a vacuum, regardless of their mass.

**Example 7.2: Object on an Incline.** Consider an object resting on an incline, as shown on the right side of Figure 7.1. Again, the object experiences only Earth’s gravitational force, which acts vertically from the center of the object toward the Earth’s center. Assuming the triangle is a hard object, the forces can be resolved into two components: (i) the force dragging the block down the slope (labeled as _F_ 2) and (ii) the force acting perpendicular to the slope known as the normal force (labeled as _F_ 1). If the gravitational force is given by _mg_ (where _m_ is the object’s mass and _g_ is the gravitational constant), what is the magnitude of both _F_ 1 and _F_ 2? Using trigonometry, we can write these as follows:

We can see that there is an obvious directional component to the motion of this object ( _F_ 2). Assuming that there is no friction acting against the object, we expect the block to travel down the incline. This means the force _F_ 2 can be used to formulate our ODE:

Canceling the mass ( _m_ ) gives:

Using separation of variables, we can re-write our expression as an integral so we can calculate velocity as a function of time. We integrate to find the velocity, assuming the object starts from rest ( _v_ = 0) at _t_ = 0:

111

Thus, the velocity of an object on an incline increases linearly with time. The rate of increase depends on the incline’s angle ( _!_ ) but is independent of the object’s mass.

Both of these examples are simplified. We could derive a general expression for _v_ as a function of _t_ ? What if the object was moving at _t_ = 0? What if there was another force acting in the opposite direction? You will see examples of this in the exercises.

**Example 7.3: Drag forces on a droplet.** We can apply Newton’s second law of motion to a case where we have an object moving through a fluid. As that object moves and displaces the fluid, the object will experience varying drag forces that can reduce the objects velocity. We experience this ourselves as we move faster through the air. Fluid dynamics is a very large area of research in itself, but we can at least use some suggested formulations that capture this drag as a function of velocity and environmental conditions. Figure 7.2 shows streamlines of fluid flow around a sphere as it moves through a fluid. As the difference in speed between the object and fluid increases, so will the nature of the forces that dictate motion. These forces include contributions from shear viscosity, eddy viscosity and stagnation pressure. In Physics, we often use dimensionless variables that give us an idea of when these change and by how much. In fluid dynamics, the Reynolds number (often denoted _Re_ ), captures this change. We do not cover that in our course. For now we can assume that, for a droplet moving through the atmosphere, the drag force on a sphere which is moving through air is approximately equal to

where _r_ is the sphere’s radius, _vrel_ is the velocity it is moving through the air and _#_ = 1 _._ 2 kg m<sup>_→_3</sup> is the density of air. How might we balance this force with the force acting on the droplet due to gravity?

**Figure 7.2:** Schematic illustrating forces acting on a a sphere moving through a fluid with varying velocity and thus Reynolds number. Taken from `https://cfdflowengineering.com/ cfd-modeling-of-flow-over-a-cylinder/`
