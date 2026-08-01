---
title: "Chapter10"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 10/Chapter10.pdf"
type: pdf
---

# 10. Vectors and Partial Differentiation

## 10.1 Overview

Now that we have concluded the topics Differentiation (Chapters 1–5) and Integration (Chapters 6–9) , we should note that these topics have been centred around a function in one variable or dimension (i.e. _y_ = _f_ ( _x_ )). We differentiated or integrated in terms of that one variable:

In many cases, we may need to work in more than one dimension (e.g. in space) such as _f_ ( _x, y_ ) = _x_<sup>2</sup> + _y_<sup>2</sup> , therefore, in this Chapter we look at **scalar fields** , **vectors** and **partial differentiation** .

## 10.2

In mathematics and physics, a **scalar** is a function of two or more variables (i.e. _f_ ( _x, y_ )) that assigns a single scalar value (a number) to every point in a space. Scalar fields represent a single value at different positions. They have magnitude but no direction and can be represented with a colour plot (e.g. temperature over a city, or for example wind speed – but not direction). In essence, they are functions in higher dimensions than we have seen thus far (i.e. _f_ ( _x_ )). Take a look at the 2-D scalar fields displayed in Figure 10.1.

These figures show three scalar fields: _f_ ( _x, y_ ) = _x_<sup>2</sup> , _f_ ( _x, y_ ) = _xy_ , and _f_ ( _x, y_ ) =<sup><u>1</u></sup> 2 � _x_<sup>2</sup> + _y_<sup>2�</sup> . Which ones are which? Try to explain why. In the plots white represents high values and black low values.

158

Chapter 10. Vectors and Partial Differentiation

**Figure 10.1:** Three scalar fields: _f_ ( _x, y_ ) = _x_<sup>2</sup> , _f_ ( _x, y_ ) = _xy_ , and _f_ ( _x, y_ ) =<sup><u>1</u></sup> 2 � _x_<sup>2</sup> + _y_<sup>2�</sup>

## 10.3 Vectors

Now take a look at the plots in Figure 10.2 which represent . Can you see the similarity? Imagine these are wind fields, as you might see on a weather forecast. In the vector fields we can determine there is a direction, or flow. The magnitude of that direction can either be taken from the length of the arrow, or by referring to the scalar fields from the plots above. Which vector fields can be aligned to the scalar fields in Figure 10.1?

The left and middle vector field could both relate to the left hand scalar field. So you see here, these vector fields given opposite flow but have the same magnitude as a function of distance. SO how do we represent a vector field algebraically?

<!-- Start of picture text -->
10<br>10 10<br>5<br>5 5<br>0 0 0<br>−5 −5<br>−5<br>−10 −10<br>−10<br>−10 −5 0 5 10 −10 −5 0 5 10 −10 −5 0 5 10<br>x x x<br>y y y<br><!-- End of picture text -->

**Figure 10.2:** Vector fields, from which we can determine there is a direction, or flow. The magnitude of that direction can either be taken from the length of the arrow, or by referring to the scalar fields from the plots in Figure 10.1.

### Vector notation

**Vectors** have **magnitude** and **direction** . We can use a simply graph to illustrate the concept. Consider Figure 10.3. Each line in this figure represents the same vector, but a different starting position. Wherever the starting position is, each vector moves 2 units to the left and 5 units up. If we write this procedure in vector form we write:

159

**Figure 10.3:** Vector fields. In this figure we use the same vector to draw a line but vary the starting position in each case.

Notice the distinction in style between the variable and the brackets. Specifically, the notation _→↑_ 2 _,_ 5 _↓_ is fundamentally different from writing ( _↑_ 2 _,_ 5). The former conveys information about the magnitude and direction of a vector, while the latter represents a point in space defined by coordinates. A vector can be written more generally as:

where the constants _a_ 1 and _a_ 2 describe shifts along the horizontal and vertical axes, respectively, based on the assumed coordinate system.

Now, imagine this vector represents movement from point _A_ to _B_ . In this case, we write the vector as _AB_<sup>_ω_</sup> . In two-dimensional space, if point _A_ has coordinates _A_ = ( _x, y_ ) and point _B_ has coordinates _B_ = ( _x_ + _a_ 1 _, y_ + _a_ 2), the vector _AB_<sup>_ω_</sup> describes the displacement. Note the difference in notation between vectors and coordinates. The same principle extends to three-dimensional systems. If the vector becomes:

then the coordinates of points _A_ and _B_ can be written as _A_ = ( _x, y, z_ ) and _B_ = ( _x_ + _a_ 1 _, y_ + _a_ 2 _, z_ + _a_ 3), respectively, representing the vector _AB_<sup>_ω_</sup> .

More generally, the direction indicated by the arrow over the vector, as in _AB_<sup>_ω_</sup> , specifies movement from point _A_ to _B_ along a straight line. If the coordinates of _A_ and _B_ are given as _A_ = ( _a_ 1 _, a_ 2 _, a_ 3) and _B_ = ( _b_ 1 _, b_ 2 _, b_ 3), the vector _ωv_ describing _AB_<sup>_ω_</sup> is:

160

Chapter 10. Vectors and Partial Differentiation

Conversely, if our vector now starts at _B_ and moves to _A_ , thus _BA_<sup>_ω_</sup> , then we can write:

Using a **start minus end** approach. You can practice these operations in the exercises.

### Unit vectors and vector magnitude

In our set of problems we consider vectors in Cartesian form, that is broken down into components along _x_ , _y_ and _z_ of a Cartesian domain. The component along _x_ is component _i_ ˆ, along _y_ is component _j_ ˆ and along _z_ is component _k_ ˆ. _i_ ˆ, _j_ ˆ and _k_ ˆ are all called unit vectors and have length equal to 1.For example, take a look at the following vector:

This tells us that, whatever process is described using this vector, for every movement 4 units along the x axis there is 3 units of movement along the y axis. In our example, _i_<sup>ˆ</sup> and _j_ ˆ represent what we call a unit vector so has a magnitude of 1. Note that this is equivalent to writing

from above.

The size of a vector (or its magnitude) can be calculated by taking the square root of all of the square its components (i.e. Pythagoras’ theorem). So if _a_ ¯ = _a_ 1 _i_<sup>ˆ</sup> + _a_ 2 _j_<sup>ˆ</sup> + _a_ 3 _k_<sup>ˆ</sup> , then the magnitude, _|_ ¯ _a|_ :

A vector that has length that points in the same direction as a general vector _a_ ¯ is called the unit vector of _a_ ¯. It is calculated by dividing all components of _a_ ¯ by the magnitude of _a_ ¯.

### Vector arithmetic

Vectors can be added or subtracted (add or subtract by component) or multiplied by a scalar (constant). For example, Figure 10.4 demonstrates adding two vectors _a_ and _b_ to create a new vector. When adding vectors, you simply add the components for _i_<sup>ˆ</sup> and _j_<sup>ˆ</sup> .

Given the vectors _ωa_ = _→a_ 1 _, a_ 2 _, a_ 3 _↓_ and<sup>_ω_</sup> _b_ = _→b_ 1 _, b_ 2 _, b_ 3 _↓_ the addition of the two vectors is given by the following formula:

_ω_ Subtraction is similar. Given the vectors _a_ = _→a_ 1 _, a_ 2 _, a_ 3 _↓_ and<sup>_ω_</sup> _b_ = _→b_ 1 _, b_ 2 _, b_ 3 _↓_ the subtraction of the two vectors is given by the following formula:

161

**Figure 10.4**

This can be harder to visualise. In Figure 10.5 you can see that if we consider we are adding the negative version of vector<sup>_ω_</sup> _b_ to _ωa_ (thus _ωa_ + ( _↑_<sup>_ω_</sup> _b_ ) since we are performing an extraction), then you can visualise the net direction of travel:

**Figure 10.5:** Visualisation of vector addition. Credit to `https://tutorial.math.lamar.edu/ Classes/CalcII/VectorArithmetic.aspx`

Imagine a situation where a unit vector described the direction of travel every second across a two dimensional grid. If we knew the object was travelling at 15 metes per second, how might we find the absolute position over 1 second? We would multiple the unit vector by the speed. Combined, this new vector represents the velocity of the object. Take a look at Figure 10.6. We have 3

162

Chapter 10. Vectors and Partial Differentiation

_ω_ vectors that have been derived from the vector _a_ = _→_ 2 _,_ 4 _↓_

**Figure 10.6:** Visualisation of vector and scalar multiplication. Credit to `https://tutorial. math.lamar.edu/Classes/CalcII/VectorArithmetic.aspx`

These lines can be written as the following scalar multiplications:

Noting that when we multiply our original vector by a negative number, we simply reverse the direction of travel.

## 10.4 Partial Differentiation

For the vast majority of this course, we have dealt with differentiation of functions in one dimension, or of one variable (i.e. _y_ = _f_ ( _x_ )). We now think about differentiation of functions of two (or more) variables (i.e. scalar field), _z_ = _f_ ( _x, y_ ), which now depend on _x_ and _y_ .

For a one dimensional curve the gradient _dx_<sup>_dy_is fairly straight forward.When there are more</sup> than one dimension we have to use something else to denote the gradient. The standard that is used is called ‘grad’, which is defined for a scalar field and can be written _grad_ ( _f_ ) or also written ! _f_ . We note that ! _f_ (where _f_ = _f_ ( _x, y, z_ ) is a scalar field) is actually a vector. In Cartesian coordinates it is:

So the gradient has magnitude and direction. To describe the movement of mass, for example, this is important information. Notice the change in the derivative symbol. Specifically, let us highlight the gradient along the x axis:

Up to this point in our course, we have been using the expression:

_d f dx_

163

The change is important. The new expression is called a _partial differential equation_ . When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant. We are only interested in information along the axis given by the variable in the denominator. We can get a feel for this through the exercises and solutions provided in the later stages of today’s material.

Even when we do not use vector notation, the partial derivatives of a function can be derived. Take the following example:

where we have defined a function that varies with respect to both _x_ and _y_ . We have been asked to find the rate of change of the function at a set of coordinates given by ( _a, b_ ). Conceptually we will need to hold _y_ constant and vary _x_ to determine the gradient along the _x_ axis a vice versa. Indeed, if we were using the method of finite difference, we could use the following assumption:

Of course, we don’t need to use finite difference in this instance since we can apply one of our rules of differentiation.

**Example 10.1** :

If we take _y_ as constant then we can derive the following expression for the partial derivative of _f_ with respect to _x_ :

Note that the second term disappears here as it has no _x_ within it. For the partial derivative of _f_ with respect to _y_ , we arrive at the following:

Putting this into vector form gives us:

Chapter 10. Vectors and Partial Differentiation

164

or in the form:

We can use this to calculate the magnitude of the gradient at any given point.

We could go even further and take second partial derivatives of _f_ to obtain get !<sup>2</sup> _f_ which would mean partial differentiating with respect to _x_ and _y_ :

as we are differentiating twice with respect to all combinations of the variables, !<sup>2</sup> _f_ becomes a matrix which has amazing properties in mathematics and physics, but this is outside the remit of this course!

Furthermore, integrating partial differential equations analytically can only be done for simple cases and requires knowledge of Fourier methods, which are outside of the remit of this course. Nearly all modern weather forecast models use approximate methods to find solutions of **partial differential equations** .
