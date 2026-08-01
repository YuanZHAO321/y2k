---
title: "Chapter2"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 2/Chapter2.pdf"
type: pdf
---

# 2. Introduction to Differentiation

## 2.1 Overview

Take a look at the graph of the function _f_ ( _x_ ) = 2 _x_<sup>3</sup> _→_ 20 _x_<sup>2</sup> + _x_ + 4000 in Figure 2.1. Clearly it can be seen that the gradient of this line is not constant with _x_ . For example:

1. at _x_ = _→_ 5 the gradient is quite steep and positive.

2. at _x_ = 0 the gradient is almost zero.

3. at _x_ = 5 the gradient is fairly shallow and negative.

<!-- Start of picture text -->
A line with a non−constant gradient<br>5000<br>f(x)=2x 3 −20x 2 +x+4000 @X=0 ∆  X<br>4000 ∆  Y ∆  Y<br>∆  X<br>@X=−5 @X=5<br>∆  Y<br>3000<br>∆  X<br>2000<br>m :  ∆  Y /  ∆  X=351.0<br>1000 mm12: :  ∆∆  Y /  Y /  ∆∆  X=1.0 X=−49.0<br>3<br>0<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>1500<br>Its gradient<br>1000 f’(x)=6x 2 −40x+1<br>500<br>0<br>−500<br>−10 −8 −6 −4 −2 0 2 4 6 8 10<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 2.1:** Top shows the function _f_ ( _x_ ) = 2 _x_<sup>3</sup> _→_ 20 _x_<sup>2</sup> + _x ↑_ 4000; bottom shows the gradient _dx_<sup>_dy_,</sup> or _f_<sup>_↓_</sup> ( _x_ ), which is positive until about _x_ = 0, negative until about _x_ = 6 and positive thereafter.

28

Chapter 2. Introduction to Differentiation

You could find the gradient at every point by drawing a tangent to the line at that point and determining how much _y_ changes for a given change in _x_ , like we did in Chapter 1. However, we can use **differentiation** to find a function that describes the gradient, which we will call<sup>_dy_In this case the function 6</sup><sup>_x_2</sup><sup>_→_40</sup><sup>_x_+1 describes the gradient of</sup><sup>_f_(</sup><sup>_x_).This</sup> _dx_<sup>.</sup> is shown in the bottom panel of Figure 2.1, labelled as _f_<sup>_↓_</sup> ( _x_ ) which is often used in place of<sup>_dy_Once we have</sup><sup>_dy_</sup> _dx_<sup>.</sup> _dx_<sup>, we can evaluate it for any value of</sup><sup>_x_to find the gradient.</sup>

## 2.2

We use How can we arrive at the formula used to generate the line in the bottom figure? the rules of **differentiation** . These rules are central to the application of calculus. We do not cover the derivation of all rules here; rather we learn how and where to apply them. You should treat these rules as an engineer might treat a screwdriver or hammer. Please keep a copy of your crib sheet nearby throughout the course. You can use this to determine which rule to apply for a given problem that requires differentiation. For now, let us take a look at a straight line and quadratic.

**Figure 2.2:** A hypothetical curve with a _y_ value that increases non linearly as _x_ increases. The gradient at points _P_ and _Q_ are different.

In Figure 2.2 _P_ and _Q_ . These position have coordinates, or values for _x_ and _y_ as ( _x, y_ ) and ( _x_ + ! _x_ 1 _, y_ + ! _y_ 1) respectively. In other words, position _Q_ is found by movement along from _P_ by an increment given by ! _x_ 1 and ! _y_ 1. We want to derive an expression for _dx_<sup>_dy_, and we keep</sup> referring to approximating this using a finite difference approach (please refer to week 1). However, the choice of the increment used to arrive at this approximation is important. You can tell from our figure that we will arrive at a different gradient if we used a combination of increments ! _x_ 1 and ! _y_ 1 compared with ! _x_ 2 and ! _y_ 2. If this isn’t clear, please ask in class. As our increment gets smaller and smaller, we get closer to the accurate value for<sup>_dy_.</sup>

_dx_<sup>.</sup>

29

Indeed, we can write the following equation:

which states that as our increment, ! _x_ tends to 0, we arrive at our derivative value. This gives us a mechanism for deriving a formula for our gradient. For example, take the straight line displayed in Figure 2.3.

### Derivative of a straight line

**Figure 2.3:** A hypothetical curve with a _y_ value that increases linearly as _x_ increases. The gradient at points _P_ and _Q_ are the same so we expect our gradient, thus derivative, to be constant.

The equation of a straight line can be expressed as the following:

where the constant _a_ is our gradient. We know our derivative _dx_<sup>_dy_should therefore be equal</sup> to _a_ . But can we show this through a derivation? Using the equation of the straight line we can work through the following steps to arrive at an expression for !<sup>!</sup> _x_<sup>_<u>y</u>_:</sup>

If we then subtract _y_ = _ax_ from both sides we get :

Rearranging this gives us:

If we let ! _x ↔↗_ 0 then we see that

So perhaps if we can keep deriving expressions for !<sup>!</sup> _x_<sup>_<u>y</u>_wecanseeifthatexpression</sup> simplifies as ! _x_ tends to 0 and identify a pattern which we could wrap up in a general rule.

30

Chapter 2. Introduction to Differentiation

Derivative of a quadratic line

**Figure 2.4:** A hypothetical curve with a _y_ value that increases quadratically as _x_ increases. The gradient at points _P_ and _Q_ are different.

The equation of a quadratic can be expressed as the following:

In Figure 2.4 we again position two points on our curve. Let us derive an expression for ! _<u>y</u>_ ! _x_<sup>in moving between these points by substituting the</sup><sup>_x_and</sup><sup>_y_coordinates and isolating</sup> expressions for ! _x_ and ! _y_ :

Lets subtract _y_ = _ax_<sup>2</sup> from both sides of the equation:

Now let’s divide the equation by ! _x_ :

If we let ! _x ↔↗_ 0 then we see that

If we repeat this procedure for higher order polynomials, we calculate that the gradient function for some simple functions of _x_ by **multiplying the original function of** _x_ **by its power** and **reducing the power that** _x_ **is raise to by 1** :

31

## 2.3 Common differentials

What if we didn’t have a polynomial in _x_ ? There are many other types of functions, so we will also need expressions for other common types of functions. Table 2.1 we list all of the common differentials you will use in this course. Learning how to apply them is a key aspect of the problems we will encounter.

**Table 2.1:** List of common differentials

<!-- Start of picture text -->
Function  y  = f ( x ) Derivative dx dy<br>constant 0<br>x 1<br>x n nx n→ 1<br>e x e x<br>e kx ke kx<br>d f<br>e f ( x )<br>dx e f ( x )<br>ln ( x ) 1 x<br>sin ( x ) cos ( x )<br>cos ( x ) →sin ( x )<br><!-- End of picture text -->

## 2.4 Differentiating sums of functions

So far we have seen how to differentiate simple functions (see Table 2.1. What happens when we have a sum of functions such as:

It turns out that differentiation is invariant to sums of functions. This means that when you differentiate the sum of two or more functions:

the **derivative of the sum** is equal to the **sum of the derivatives** of the individual functions.

Therefore, using the list of common derivatives, we see that the derivative of _y_ = 2 _x_<sup>2</sup> + 3 _x_ is:

We’ll see what happens when we get more complicated combinations of functions (i.e. functions of functions, products, fractions) in the next Chapter!
