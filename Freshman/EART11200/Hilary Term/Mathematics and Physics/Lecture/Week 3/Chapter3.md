---
title: "Chapter3"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 3/Chapter3.pdf"
type: pdf
---

# 3. Differentiating combinations of functions

## 3.1 Overview

We saw Chapter 2 that for a sum of functions, the **derivative of the sum** is equal to the **sum of the derivatives** of the individual functions.

However, in many cases we are faced with more complicated combinations of functions such as **functions of functions**

or **products of functions**

or **quotients of functions**

_y_ . Another scenario arises where we wish to obtain a derivative of a function that does not fit under any of the criteria we use in our common rules of differentiation. In other words it does not look like we can obtain an analytical derivative and we may need to use a numerical approach (like we saw in Chapter 1). We will now look at expanding the laws of differentiation to deal with these new types of functions.

42

Chapter 3. Differentiating combinations of functions

## 3.2 Functions of functions

**functions of functions** such as:

An example of this would be _y_ = ln(2 _x_ ) where we can split this into two functions, _u_ ( _x_ ) = ln( _x_ ) and _v_ ( _x_ ) = 2 _x_ . How do we obtain the derivative _dx_<sup>_dy_?Luckily,thereare</sup> properties of derivatives that we can use to slightly modify

and make it look like things we have seen before and differentiate as normal. This is called the chain rule and is best illustrated with an example. One of our common rules of differentiation shows us that the derivative function of the natural logarithm (i.e. _y_ = ln( _x_ ) is given as follows:

But what if our function looked slightly different? Let’s return to _y_ = ln(2 _x_ ). What is the derivative?

It is tempting to assume the answer would be _dx_<sup>_dy_=</sup> 2<sup><u>1</u></sup> _x_<sup>wouldn’t it?We know that this is</sup> wrong since we can rewrite _h_ ( _x_ ) = ln(2 _x_ ) = ln(2)+ ln( _x_ ) and therefore we see that

Fortunately, we have the **chain rule** . We can re-write the derivative of a function of a function such that it resembles a form we can derive an analytical derivative from. In this case, what if we assumed we could replace the expression 2 _x_ by a new variable _z_ . Our expression now reads:

We are not quite done, however. The chain rule allows us to treat derivatives in the same way we can multiply fractions. We **chain** together operations. Formally, it states that to get the derivative of a function, _f_ , which can be written as a function of another function, _g_ ( _x_ ) you differentiate the function, _f_ , wrt the function _g_ and multiply the result by the derivative of _g_ with respect to _x_ :

43

This tells us that we first obtain the analytical derivative of our function _f_ with respect to a new variable _g_ and then multiply the derivative of our new variable _g_ with respect to our original variable _x_ . Can you see how the terms _dg_ cancel out?

**Example 3.1** : Differentiate _y_ = (3 _x_ + 1)<sup>2</sup> . We could expand the bracket and differentiate as we have seen before:

or we could use _chain rule_ . Let

and differentiate as usual

Therefore using the chain rule formula and substitution the solution is:

which is what we expected!

**Example 3.2** : Differentiate _y_ = _↓_ 13 _x_<sup>2</sup> _↔_ 6 _x_ + 8. There is no obvious way to differentiate this using methods we have used before, we must use _chain rule_ . Let

and differentiate as usual

Therefore using the chain rule formula and substitution the solution is:

## 3.3 Products of functions

In many cases we are faced with the **product of two, or more, functions** . We might described a general case where we have two functions multiple as :

Chapter 3. Differentiating combinations of functions

44

where _u_ is a function that varies only with respect to variable _x_ and _v_ is also a function that varies only with respect to _x_ . How do we obtain the derivative _dx_<sup>_dy_?Using the tools we have</sup> met so far, then we might first attempt to expand terms and separate variables. But what if we decided that the derivative could be calculated by simply multiplying the associated derivatives from each function. So, we might assume we can use the formula:

This would be useful if our functions were somewhat complex but could be treated in isolation i.e. we did not want to expand all of the terms. Let us look at a relatively simple example to see which is a valid approach, one where we can access the expression _u_ ( _x_ ) _v_ ( _x_ ). If we assume _u_ ( _x_ ) = _x_<sup>3</sup> and _v_ ( _x_ ) = _x_<sup>6</sup> then we know that:

From this we can obtain the derivative as follows:

But what if we had chosen to use the approach written in align 3.2. We would arrive at the following formula:

which is wrong! We saw that it is wrong as our expansion leads to a derivative of 9 _x_<sup>8</sup> . So here we can see that we have to be careful when working with products of functions.

Fortunately, in cases where we cant easily expand our expression, there is the **product rule** which states that to get the derivative of a function, _y_ , which can be written as the _product_ of two functions, _u_ and _v_ we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and calculate:</sup>

45

**Example 3.3** : Differentiate _y_ = (3 _x_ + 1)<sup>2</sup> . We could expand the bracket and differentiate as we have seen before:

or we could use _product rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:

which is what we expected!

**Example 3.4** : Differentiate _y_ = _x_ exp ( _↔_ 3 _x_ ). There is no obvious way to differentiate this using methods we have used before, we must use _product rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:

## 3.4 Quotients of functions

What if we **divided one function by another** ? We find similar problems. We might described a general case where we have two functions multiple as :

where _u_ is a function that varies only with respect to variable _x_ and _v_ is also a function that varies only with respect to _x_ . How do we obtain the derivative _dx_<sup>_dy_?Using the tools</sup>

Chapter 3. Differentiating combinations of functions

46

we have met so far, then we might first attempt to simplify into one expression. But what if we decided that the derivative could be calculated by simply dividing the associated derivatives from each function? We might assume we can use the formula:

Again, this would be useful if our functions were somewhat complex but could be treated in isolation i.e. we did not want to expand and simplify all of the terms. Let us look at a relatively simple example to see which is a valid approach, one where we can access the expression _u_ ( _x_ ) _v_ ( _x_ ). If we assume _u_ ( _x_ ) = _x_<sup>3</sup> and _v_ ( _x_ ) = _x_<sup>6</sup> then we know that:

Once again we can rearrange this expression and arrive at the correct derivative through the following:

But what if we had chosen to use the approach written in align 3.5? We would arrive at the following formula:

which is wrong! We saw that it is wrong as our expansion leads to a derivative of _↔_ 3 _x_<sup>_↔_4</sup> . So here we can see that we have to be careful when working with fractions of functions.

Fortunately, in cases where we cant easily expand and simplify our expression, there is the **quotient rule** which states that to get the derivative of a function, _y_ , which can be written as the _quotient_ of two functions, _u_ and _v_ we calculate<sup>_<u>du</u>_</sup> _dx_<sup>and</sup> _dx_<sup>_<u>dv</u>_and calculate:</sup>

**Example 3.5** : Differentiate _y_ =<sup><u>3</u></sup><sup>_<u>x</u>_</sup> _x_<sup><u>+21.</u>Wecouldsplitthisupintotwofractionsand</sup> differentiate,

47

or we could use _quotient rule_ . Let

and differentiate as usual

Therefore using the quotient rule formula the solution is:

which is what we expected!

**Example 3.6** : Differentiate _y_ =<sup><u>3</u></sup> _x_<sup>2</sup><sup>_<u>x</u>_</sup> +<sup><u>+</u></sup> 1<sup><u>1.</u>There is no obvious way to differentiate this using</sup> methods we have used before. We must use _Quotient Rule_ . Let

and differentiate as usual

Therefore using the product rule formula the solution is:
