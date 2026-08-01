---
title: "Chapter5"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 5/Chapter5.pdf"
type: pdf
---

# 5. Second Order Derivatives & Root Finding

## 5.1 Overview

In Chapters 2–4, we learned how to calculate derivatives of functions, which can be used tells us a rate of change and help us identify various properties and behaviors of functions. In this Chapter, we conclude our study of differentiation by examining the further properties of functions through the **second-order derivative** and exploring how derivatives can be applied to locate the **roots of functions** .

## 5.2 Second-order derivatives

In the previous Chapter, we explored the **properties of derivatives** and how to use them to identify the **stationary values** of functions. These properties are invaluable for optimising functions or processes. However, to determine whether a stationary value represents a maximum or a minimum, we relied on either (a) looking the function’s plot or (b) evaluating the original function on either side of the stationary value. There is, however, a formal method for verifying this, which involves something called the **second-order derivative** .

Up to this point, we have only differentiated functions once. For a given function _f_ ( _x_ ), its derivative is expressed as:

This is referred to as the . However, differentiation can be carried out multiple times. By differentiating a function again, we obtain the **second-order derivative** ,

Chapter 5. Second Order Derivatives & Root Finding

76

The second-order derivative has some very interesting and useful properties. Previously we saw that the first-order derivative, _f_<sup>_→_</sup> ( _x_ ) tells us about the rate of change of a function, _f_ ( _x_ ). The second-order derivative, _f_<sup>_→→_</sup> ( _x_ ), goes a step further by telling us how the rate of change, _f_<sup>_→_</sup> ( _x_ ), itself is changing. This has many applications in physics, such as investigating stationary values or determining steady state, but to understand why its useful, imagine you’re driving:

1. Distance is how far you’ve traveled over time (call this _x_ = _f_ ( _t_ ))

2. Speed tells us how fast you’re traveling at any given moment. It’s the rate at which your distance changes over time. Mathematically, it’s the first-order derivative of distance:

3. Acceleration measures how quickly your speed is increasing or decreasing. It’s the rate of change of velocity over time. Mathematically, this is the second derivative of distance (or the first derivative of velocity):

## Stationary values

These properties of second-order derivative make them very useful for understanding the nature of stationary points, which are the points where _f_<sup>_→_</sup> ( _x_ ) = 0. Here’s how _f_<sup>_→→_</sup> ( _x_ ) helps us classify these points:

- <sup>If</sup><sup>_f →→_(</sup><sup>_x_)</sup><sup>_<_0, then</sup><sup>_f_(</sup><sup>_x_) has a local maximum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f →→_(</sup><sup>_x_)</sup><sup>_>_0, then</sup><sup>_f_(</sup><sup>_x_) has a local minimum at the stationary value</sup><sup>_x_</sup>

- <sup>If</sup><sup>_f →→_(</sup><sup>_x_) = 0, then it is not possible to conclude anything about the point</sup><sup>_x_.It could</sup> be saddle point (neither a maximum nor a minimum) so we need to either visually inspect the stationary value or or further evaluation of _f_ ( _x_ ) is needed.

Let’s return to an example from the previous Chapter.

**Example 5.1** : Let’s consider the cubic function

This function is shown in the top panel of Figure 4.2, over the range: _↑_ 10 _< x <_ 5. In the previous Chapter, we differentiated this function to find:

77

By solving the quadratic equation, we determined the stationary points at _x_ = _↑_ 5 and _x_ = 1. From the graph, these points appear to be a maximum and a minimum, respectively. To confirm this, let’s examine the second derivative:

Now, we evaluate the second derivative at the stationary points:

Since _f_<sup>_→→_</sup> ( _x_ ) _<_ 0 at _x_ = _↑_ 5 and _f_<sup>_→→_</sup> ( _x_ ) _>_ 0 at _x_ = 1, we can confirm these stationary values are a local maximum and minimum respectively.

## Steady state

You may not be familiar with the concept of **steady-state** . When a system is in steady-state, the key variables that describe the system’s behavior do not change over time. In a chemical system, this means that even though processes are happening that could cause change, the system’s variables stay the same. For this to happen, there must be a continuous flow of materials through the system.

Let’s look at an example using Figure 5.1. Imagine water is being poured into a container that has an outlet on the side. At first, when the water level is below the outlet, the water level in the container rises over time, as shown in (a). But once the water level reaches a certain height, the rate at which water is entering the container equals the rate at which it is leaving through the outlet. At this point, the water level stops rising and stays constant, as shown in (b). This is when the system has reached a steady state.

To describe the total volume of water in the system, let’s denote it as _w_ . In our differential equation, we aim to express how this total volume changes. We can say that the rate of change of the water volume remains constant, either with respect to time or space. This rate of change can be written as:

This equation means that the rate at which the total volume of water _w_ is a function of time and multiple sources and sinks of water which I have expressed as _x_ 1, _x_ 2. Using the above definition of steady state, here the rate of change does not change over time, we can take the derivative of the equation above:

78

Chapter 5. Second Order Derivatives & Root Finding

**Figure 5.1:** Diagram showing a system in (a) transient state and (b) steady state.

This equation tells us that the second derivative of _w_ with respect to time is zero. In other words, the rate of change of the volume of water is not changing—it remains constant. This implies that there is a steady flow, and the total amount of water in the system remains constant. Let us work through an example.

**Example 5.2** : Imagine an object moving under constant acceleration. Mathematically, we can express the fact that acceleration is constant by saying:

This means the rate of change of acceleration is zero. Since acceleration is the rate of change of velocity (see above), we can also write this as:

This tells us that the velocity is not changing in a way that would cause acceleration to vary. If we had an expression for velocity as a function of time, we could differentiate that expression and check if this is true. Take a hypothetical example where the velocity is given by

where _t_ is time (in seconds) and _a_ is a constant (in _m/s_<sup>_↑_2</sup> . We can show that the secondorder derivative is 0 through the following steps:

Since _!_ is a constant, the acceleration does not change over time. that the acceleration is constant, and the second derivative of velocity with respect to time is zero, as expected and the system is in steady state.

79

**Figure 5.2:** Function that varies non-linearly with _x_ and example tangents at different points. Credit to `https://tutorial.math.lamar.edu/Classes/CalcI/NewtonsMethod.aspx`

## 5.3 Finding roots of equations: Newton-Raphson method

We’ve been discussing how derivatives help us understand change. So far, most of our examples have been a combination of hypothetical and real-world examples on using derivatives to calculate the gradient (or slope) of a line. While this is a useful concept, it can sometimes be difficult to see how it applies to real-world situations. When we start learning about integration, we’ll see that we can reverse the process of differentiation. This allows us to calculate actual values (or "absolute values") from the past and predict future values.

But derivatives have other practical uses too. For example, one important application is **finding the roots** of a function, which is where a **function equals zero** . You have encountered these when finding stationary values! Take a look at Figure 5.2, which shows a typical function _y_ = _f_ ( _x_ ). Our function line clearly shows that when _x_ = 0, _y_ has a negative value and as _x_ increases, _y_ increases. At some point, the function crosses the _x_ -axis and becomes zero.

However, consider the function:

In this case, it’s difficult to find where _f_ ( _x_ ) = 0 using simple algebra. Instead, we could iteratively insert values for _x_ and gradually work towards smaller and smaller values for _y_ . By doing this repeatedly, we could gradually get closer to the root. However, this approach

80

Chapter 5. Second Order Derivatives & Root Finding

is not only time-consuming and laborious, but also impossible to visualise for complex functions. What if there were a better way? What if we could use the information provided by the function’s gradient (or slope), that is, the tangent line to help us find the root more efficiently?

Imagine our first value for _x_ is denoted as _x_ 0. At this point, the value of the function _f_ ( _x_ 0) _>_ 0, and we can calculate the slope (or gradient) at _x_ 0, which we write as _f_<sup>_→_</sup> ( _x_ 0). This slope represents the tangent line to the curve at _x_ 0. Now, follow the tangent line from _x_ 0 until it crosses the x-axis. The tangent crosses the x-axis and arrives at another value for _x_ which we shall denote as _x_ 1. We can write the equation of the tangent line as follows:

_y_ = 0:

Rearranging to get _x_ 1:

So, _x_ 1 is the new estimate for the root of the function. Next, to find _x_ 2, we repeat the same process, using _x_ 1 as the new starting point and get:

As we continue this process, the values of _x_ will get closer and closer to the true root. However, we may never reach an exact value of _y_ = 0. Instead, we define a tolerance level for what we consider as _y_ = 0 or the percentage change in _x_ . For example, we may stop the iterations if _y_ is smaller than a certain threshold (e.g., _y <_ 0 _._ 001) or if the change in _x_ is very small (e.g., less than 0.01%). This depends on the nature of the problem you are trying to solve. There is no guarantee this method will converge to a root. Indeed there are cases where each iteration will get worse and worse. However it is good and simple method for root finding in cases where we cannot easily access an analytical solution. The general formula for the Newton-Raphson method is:

the function. Let’s consider an example.

81

**Example 5.3** : Suppose we want to find the root of this equation to an accuracy of 6 decimal places:

Since it is not feasible to solve _f_ ( _x_ ) = 0 through simple rearrangement, we employ Newton’s method. This requires the derivative of _f_ ( _x_ ), which is:

To arrive at the value for _x_ at the root, we need an initial guess. This can be important. We are told, on this occasion, the root exists somewhere between _x_ = 3 and _x_ = 4. If we start at _x_ 0 = 3 _._ 5, what is the value for _x_ 1? Using Newton’s method, the next approximation, _x_ 1, is computed as:

In the class examples, you are asked to proceed with this problem until you arrive at an approximation for the root which is _↗_ 3.275601.
