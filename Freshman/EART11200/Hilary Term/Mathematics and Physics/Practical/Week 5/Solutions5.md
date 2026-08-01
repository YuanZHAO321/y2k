---
title: "Solutions5"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 5/Solutions5.pdf"
type: pdf
---

84

Chapter 5. Second Order Derivatives & Root Finding

# Solutions

**Question 5.1** :

- (a) For the first-order derivative (from Chapter 3 Question 5.4(a)), we split the function and differentiated using the chain rule:

Apply the chain rule:

For the second-order derivative (from Chapter 3 Question 5.4(d)), we split the function and differentiate using the quotient rule:

Apply the quotient rule:

- (b)

Therefore the second-order derivative is provided by the following expression:

- (c) For the first-order derivative (from Chapter 3 Question 5.2(a)), we split the function and differentiated using the product rule:

85

Apply the product rule:

To compute the second-order derivative, note that the first term, _exp_ ( _x_ ), remains unchanged due to the exponential derivative rule. For the second term, _xexp_ ( _x_ ), the product rule must be applied again. Interestingly, this term is the same structure as the original function, allowing us to substitute it back and simplify further, yielding:

- (d) Our final equation is the hydrostatic equation. For the first-order derivative (from Chapter 2 Question 5.8), we that this is an exponential function with multiple constants so:

To obtain the second derivative,<sup>_<u>d</u>_2</sup><sup>_<u>P</u>_, we again recognise there are multiple constants</sup> _dz_<sup>2</sup> and retain those that multiple an expression involving z:

which we can further simplify to the following:

Alternatively, notice that we can write

so then

**Question 5.2** : Find the stationary values of the following functions:

- (a)

86

Chapter 5. Second Order Derivatives & Root Finding

and solve _f_<sup>_↗_</sup> ( _x_ ) = 0 to find stationary points

So we see two stationary values at _x_ = _↔_ 6 and _x_ = _↔_ 5. We then use the second derivative to classify the stationary values. The second derivative is:

At the stationary values, the second derivative is:

so _x_ = _↔_ 6 is a maximum and _x_ = 5 is a minimum.

(b)

and solve _f_<sup>_↗_</sup> ( _x_ ) = 0 to find stationary points

So we see a stationary value at _x_ = 0. We then use the second derivative to classify the stationary point. The second derivative is:

At the stationary values, the second derivative is:

Since _f_<sup>_↗↗_</sup> (0) = 0, we cannot classify the stationary point using the second derivative test. Instead, consider the behaviour of _f_ ( _x_ ) = _x_<sup>3</sup> :

- <sup>For</sup><sup>_x <_0,</sup><sup>_f ↗_(</sup><sup>_x_)</sup><sup>_>_0, indicating</sup><sup>_f_(</sup><sup>_x_) is increasing.</sup>

- <sup>For</sup><sup>_x >_0,</sup><sup>_f ↗_(</sup><sup>_x_)</sup><sup>_>_0, indicating</sup><sup>_f_(</sup><sup>_x_) is still increasing.</sup>

Thus, _x_ = 0 is a saddle point.

**Question 5.3** : In this Question 5.we are asked to find a root within a specified accuracy, assuming it is between _x_ = 4 and _x_ = 6 for the following function:

87

As we saw in Chapter 5, we need to first derive our derivative function which, in this case, is:

We iterate through the Newton method:

until our only changes at an accuracy greater than 6 decimal places (i.e. we can stop at the chosen level of tolerance).

so the root of _f_ ( _x_ ) to 6 decimal places is 3.275601.

**Question 5.4** : In this Question 5.we are asked to find a root after two iterations of Newtons method. However, you may choose your own stopping criteria for practice

- (a) We need to derive the derivative of the function

which takes the form:

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 5:

so the root of _f_ ( _x_ ) after two iterations is 5.71875.

- (b) We need to derive the derivative of the function

88

Chapter 5. Second Order Derivatives & Root Finding

which takes the form:

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 2:

so the root of _f_ ( _x_ ) after two iterations is 2.219185.

(c) We need to derive the derivative of the function

To differentiate _h_ ( _x_ ) = _xcos_ ( _x_ ) we split the function and differentiate using the product rule:

Apply the product rule:

so we see that

We then apply the Newton method twice:

with a starting guess of _x_ 0 = 1:

so the root of _f_ ( _x_ ) after two iterations is 0.744094.

89

**Question 5.5** : In this Question 5.we are asked to find all the roots to 3 decimal places for the following function:

In this problem we have been given a figure to help us decide on where to start our initial guess for each root. Since we have 3 roots (according to what we can see), it makes sense to select values near these points. We have been given _x_ 0 = _↔_ 3 _._ 5 and _x_ 0 = 4 _._ 5 as starting values but there is also a root near zero so lets also use _x_ 0 = 0 as the final starting value to check this. We need to derive the derivative of _f_ ( _x_ ), which takes the form:

We then apply the Newton method:

for each starting guess until the root is accurate within 3 decimal places:

- <sup>For</sup><sup>_x_</sup> 0<sup>=</sup><sup>_↔_3</sup><sup>_._5:</sup>

- <sup>For</sup><sup>_x_</sup> 0<sup>= 4</sup><sup>_._5:</sup>

so the three roots of _f_ ( _x_ ) to 3 decimal places are -3.442, 0.066 and 4.376. Please note that the following solution is dependent on the starting guess so your results may change. You may even find your value grows! So care is needed when there are multiple roots.

**Question 5.6** : We need to prove that an industrial incinerator emissions

90

Chapter 5. Second Order Derivatives & Root Finding

are in steady state. To do this we differentiate, the

Verify this by taking the second derivative

**Question 5.7** : We need to prove that a system

are in steady state. To do this we differentiate, the

which is constant, so the system is in steady state. Verify this by taking the second derivative

## **Question 5.8** :

(a)

is at its minimum, which corresponds to a stationary point. tiate _P_ ( _x_ ) and set the derivative equal to zero:

Since this equation cannot be solved algebraically, we use Newton’s method to approximate the root. It’s important to note that we are solving for the root of<sup>_<u>dP</u>_</sup> _dx_<sup>,</sup> not _P_ ( _x_ ). Let us define _f_ ( _x_ ) =<sup>_<u>dP</u>_</sup> _dx_<sup>, and compute its derivative:</sup>

Using Newton’s method, the iterative formula is:

91

Starting with an initial guess of _x_ 0 = 3, we iterate until the values converge to an accuracy of three decimal places:

Thus, the root of _f_ ( _x_ ) to three decimal places is _x_ = 2 _._ 833. Therefore, the profit is at its minimum when approximately 2833 units are sold.

- (b) We use the second derivative to classify stationary values. We already calculated the second derivative in the last part through Newton’s method:

so at the 2.833 the second derivative is

Since the second derivative is positive, then the profit is definitively minimised at 2.833.
