---
title: "practical1_soln(3)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 1/practical1_soln(3).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 1 Practical - Calculating Gradients (Solutions)_

1/ 12

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

2/ 12

## INTENDED LEARNING OUTCOMES

- (1) Discuss the role of calculus in broader mathematical and physical contexts.

- (2) Apply Euler’s Backward Method to analyse rates of change in mathematical functions and real world applications.

- (3) Apply Euler’s Forward Method to analyse rates of change in mathematical functions and real world applications.

- (4) Apply Central Differences Method to analyse rates of change in mathematical functions and

   - real world applications.

3/ 12

## EXERCISE 1: REARRANGING EXPRESSIONS

- In many cases we will be required to rearrange formulae.

▶ Rearranging formulae is a way of changing the subject of a formula.

- This can help us determine a missing value when we know other values within a formula.

- To change the subject of a formula is to rewrite the formula so a single unknown variable is equal to the rest of it.

- For example, if _y_ = _~~√~~ x_ + 2 then we can rearrange to make _x_ the subject (i.e. _x_ = _y_<sup>2</sup> _−_ 2)

4/ 12

## EXERCISE 1: REARRANGING EXPRESSIONS

- The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _λ_ is called the decay rate.

- This is a differential equation, and it has solution:

where _N_ 0 is the total number of nuclei in the sample at _t_ = 0.

- The half-life is the time it takes for the number of unstable nuclei to decrease by one half (i.e. at _t_ 1 _/_ 2, then _N_ ( _t_ 1 _/_ 2) = _N_ 0 _/_ 2.

- Show that the decay rate is

_λ_ =<sup>ln(2)</sup> _t_ 1 _/_ 2

5/ 12

## SOLUTION 1: REARRANGING EXPRESSIONS

<!-- Start of picture text -->
▶ Equating and rearranging gives<br><!-- End of picture text -->

6/ 12

## EXERCISE 2: CALCULATING GRADIENTS

- The plot shows the following function between _x_ = 0 and _x_ = 6:

_y_ = _x_<sup>2</sup> _−_ 8 _x_ + 12

and the rate of change (i.e. the derivative):

_dy dx_<sup>= 2</sup><sup>_x −_8</sup>

- We want to compare the analytical and numerical derivative.

<!-- Start of picture text -->
10<br>5<br>0<br>−5<br>0 1 2 3 4 5 6<br>x<br>Function Derivative<br>y<br><!-- End of picture text -->

7/ 12

## EXERCISE 2: CALCULATING GRADIENTS

- We want to use the **approximation methods** discussed in lectures:

### ▶ **Euler’s Backward Method** :

- **Euler’s Forward Method** :

<!-- Start of picture text -->
dy = lim ∆ y yx − yx− ∆ x<br>dx ∆ x→ 0 ∆ x ≡ ∆ lim x→ 0 ∆ x<br>dy = lim ∆ y yx +∆ x − yx<br>dx ∆ x→ 0 ∆ x ≡ ∆ lim x→ 0 ∆ x<br><!-- End of picture text -->

- **Central Differences Method** :

_dy_ = lim ∆ _<u>y yx</u>_ +∆ _x −_ _<u>yx−</u>_ ∆ _x dx_ ∆ _x→_ 0 ∆ _x_<sup>_≡_</sup> ∆<sup>lim</sup> _x→_ 0 2∆ _x_

8/ 12

## EXERCISE 2: CALCULATING GRADIENTS

<!-- Start of picture text -->
Function: y  =  x 2 − 8 x  + 12<br>dy<br>Derivative: dx = 2 x − 8<br>Backward: ∆ y yx − yx− ∆ x<br>∆ x = ∆ x<br>Forward: ∆ y yx +∆ x − yx<br>∆ x = ∆ x<br>Central: ∆ y yx +∆ x − yx− ∆ x<br>∆ x = 2∆ x<br><!-- End of picture text -->

9/ 12

## SOLUTION 2: CALCULATING GRADIENTS

- Filling in the table using the three numerical an analytical methods yields somewhat different results.

<!-- Start of picture text -->
Function: y  =  x 2 − 8 x  + 12<br>dy<br>Derivative: dx = 2 x − 8<br>Backward: ∆ y yx − yx− ∆ x<br>∆ x = ∆ x<br>Forward: ∆ y yx +∆ x − yx<br>∆ x = ∆ x<br>Central: ∆ y yx +∆ x − yx− ∆ x<br>∆ x = 2∆ x<br><!-- End of picture text -->

10/ 12

## SOLUTION 2: CALCULATING GRADIENTS

- As we know the analytical derivative, we can compare against the numerical.

- At a step size of 1 using the backward method yields a pretty large error.

- As we decrease the step size we get a lower error and closer to the analytical derivative and therefore we see that:

11/ 12

## INTENDED LEARNING OUTCOMES

- (1) Discuss the role of calculus in broader mathematical and physical contexts.

- (2) Apply Euler’s Backward Method to analyse rates of change in mathematical functions and real world applications.

- (3) Apply Euler’s Forward Method to analyse rates of change in mathematical functions and real world applications.

- (4) Apply Central Differences Method to analyse rates of change in mathematical functions and

   - real world applications.

12/ 12
