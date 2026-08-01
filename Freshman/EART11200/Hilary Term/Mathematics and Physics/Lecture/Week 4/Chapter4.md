---
title: "Chapter4"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 4/Chapter4.pdf"
type: pdf
---

# 4. Optimisation and Properties of Derivatives

## 4.1 Overview

In Chapters 2 and 3, we have been calculating derivatives of functions. Whilst telling us the rate of change of a function, derivatives can also be used to determine certain properties of a function and how it behaves. We now carry on with the topic of differentiation onto the topic of **properties of derviatives** and using them to **find maxima and minima** of functions.

## 4.2 Properties of a derivative

Remember, the derivative of a function at a given point represents the gradient of a function at that point, indicating the rate of change. Therefore, we can use the derivative to know where a function is increasing, decreasing or neither. We can see that if the rate of change is negative,

then the function is decreasing and that if the rate of change is positive,

then the function is increasing. If the derivative is zero,

then it is likely the function will be changing direction either side. This means that the point on the function where the derivative is either a **maximum value** , **minimum value**

60

Chapter 4. Optimisation and Properties of Derivatives

or a **saddle point** . This turns out to be a very useful property and more generally we call these **stationary values** or **stationary points** . Once we know where the these stationary points are for a function, further analysis can help classify them. There will be more on this in the next Chapter, but for now, once you find where the derivatives are 0 you can then explore regions either side to determine if the gradient is positive or negative. Let’s consider some examples.

**Example 4.1** : Let’s consider the quadratic function

This function is shown in the top panel of Figure 4.1, over the range: _→_ 5 _< x <_ 15. We can see that there is a point on the curve that where the minimum occurs ( _x_ = 5 in the plot, but note that it is not obvious). Now lets differentiate the function _f_ ( _x_ ) and look at how it behaves:

The derivative function is shown in the bottom panel of Figure 4.1, over the range: _→_ 5 _< x <_ 15.

<!-- Start of picture text -->
40<br>f(x)=x 2 /2−5x+2<br>20<br>0<br>−20<br>−5 0 5 10 15<br>x<br>10<br>f’(x)=x−5<br>5<br>0<br>−5<br>−10<br>−5 0 5 10 15<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 4.1:** Top: _y_ changing as a function of _x_ . Bottom: Derivative value for the same function, also varying as a function of _x_

61

The thing to notice about the gradient function, _f_<sup>_↑_</sup> ( _x_ ), is that it is equal to zero at the point where _f_ ( _x_ ) is a minimum. Therefore we can find the minimum of _f_ ( _x_ ) by differentiating it and setting it to zero:

we can then solve _x →_ 5 = 0 to get that _x_ = 5. This tells us that the minimum value occurs at _x_ = 5. We can evaluate the value of _f_ at the stationary value (i.e. maximum and minimum) _f_ (5) =<sup><u>5</u></sup> 2<sup>2</sup><sup>_→_5</sup><sup>_._5+2 =</sup><sup>_→_10</sup><sup>_._5.</sup>

**Example 4.2** : Sometimes there can be more than one stationary point. Let’s consider the cubic function

This function is shown in the top panel of Figure 4.2, over the range: _→_ 10 _< x <_ 5. We can see that there is a point on the curve that where a minimum occurs ( _x_ = 2) and where a maximum occurs ( _x_ = _→_ 5), again not immediately visible. Now lets differentiate the function _f_ ( _x_ ) and look at how it behaves:

_d f_<sup>_f ↑_(</sup><sup>_x_) =</sup><sup>_x_2 +4</sup><sup>_x→_5</sup> _dx_<sup>=</sup>

<!-- Start of picture text -->
f(x)=x 3 /3+2x 2 −5x+1<br>40<br>20<br>0<br>−10 −5 0 5<br>x<br>100<br>f’(x)=x 2 +4x−5<br>50<br>0<br>−50<br>−10 −5 0 5<br>x<br>f(x)<br>f’(x)<br><!-- End of picture text -->

**Figure 4.2:** Top: _y_ changing as a function of _x_ . Bottom: Derivative value for the same function, also varying as a function of _x_

62

Chapter 4. Optimisation and Properties of Derivatives

The derivative function is shown in the bottom panel of Figure 4.2, over the range: _→_ 10 _< x <_ 5. If we set the gradient function to zero we have a quadratic equation:

which we can solve either by the quadratic formula, or by factorisation:

so that the two solutions are _x_ = 1 and _x_ = _→_ 5 (as shown in the Figure 4.2).

Sometimes it will not always be possible to solve an equation equal to zero by rearranging or factorising, due to the complexity of the function. We then must use an algorithm to find the stationary values. We will explore this topic in the next Chapter.

1. Differentiate the function, to find the gradient function, _f_<sup>_↑_</sup> ( _x_ ) or _dx_<sup>_dy_</sup>

2. Set the gradient function to zero and solve for _x_ .

3. Substitute _x_ into _f_ ( _x_ ) to get what the value of the stationary points are.

We could (and strictly should) verify that we have found a minimum and maximum point. We will again see this more in next Chapter, but a quick way of doing this is to evaluate _f_ ( _x_ ) for _x_ just a little bit more and just a little bit less than the stationary value. Returning to Example 4.1, we can try _f_ (4 _._ 5), which is equal to _→_ 10 _._ 375 and _f_ (5 _._ 5) which is also equal to _→_ 10 _._ 375. Both of these values, are greater than the stationary value, so this tells us that the stationary value is indeed a minimum. If we had found a maximum we would find that _f_ ( _x_ ) either side of the stationary point to be less than the value of the stationary point. More generally, we can use properties of a derivative. We can see that when _x <_ 5, then _f_<sup>_↑_</sup> ( _x_ ) _<_ 0 and when _x >_ 5, then _f_<sup>_↑_</sup> ( _x_ ) _>_ 0, so we see that the stationary value is a minimum.

## 4.3 Optimisation

value(s) of a function given set of constraints. They are quite common in areas such as

- <sup>Business and Economics:</sup>

- <sup>Physics and Engineering:Minimize energy or optimize the performance of systems.</sup>

- <sup>Geometry:Find dimensions that maximize area or volume subject to constraints.</sup>

Derivatives and their properties play a crucial role in a wide range of problems such as optimisation. We can study a function to find the maxima and minima which "optimises" a function, which can play a vital role in decision making.
