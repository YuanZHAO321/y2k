---
title: "Exercises2"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Practical/Week 2/Exercises2.pdf"
type: pdf
---

32

Chapter 2. Introduction to Differentiation

# Exercises

In the following exercises we can start to practice using them to derive derivative functions and thus calculate gradients. Please read the questions carefully before answering them. Throughout the course questions will be split and laid out as follows:

1. **Algebraic problems** : These questions are what I often call "pure" mathematical problems in the sense that they are not driven by a specific real word application. The functions might represent any given process in the earth system, however. The key point here is to continue practicing methods for differentiating.

2. **Real-world problems** : Here you are given a scenario that requires framing of a specific problem. You wont necessarily be asked to derive long derivatives here, but work with expressions of derivatives to get a better understanding of their role.

I would recommend you first try them without looking at crib sheets, but go back to that when you encounter any problems. For those who have not encountered the ! operator before, this represents a summation over the function given to the right hand side. For example, !<sup>4</sup> _x_ =1<sup>3</sup><sup>_x_is saying we need to sum the values obtained from from x=1 to x=4,</sup> stepping over increments of 1. In the problem provided below, try expanding the expression for a number of values before re-expressing your answer using the ! operator. Also note that an expression that uses<sup>_→_</sup> as the square root operator can be re-expressed using the <u>1</u> power<sup><u>1</u></sup> 2<sup>(i.e.</sup><sup>_→_</sup> _~~x~~_ = _x_ 2 ).

## Algebraic problems

**Question 2.1** : Differentiate the following functions with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>2</sup>

- (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup>

- (c) _h_ ( _x_ ) = 11 _x_<sup>1</sup>

**Question 2.2** : Differentiate the following polynomials with respect to _x_ :

- (a) _f_ ( _x_ ) = 5 _x_<sup>3</sup> + 2 _x_<sup>2</sup> + 3 _x_ + 5

- (b) _g_ ( _x_ ) = 10 _x_<sup>3</sup> + _x_ + 5

- (c) _h_ ( _x_ ) = 11 _x_<sup>5</sup> + 2 _x_<sup>4</sup> + 2 _x_<sup>3</sup> + _x_<sup>2</sup> + 3 _x_ + 2

- **Question 2.3** : Find the gradient of the following functions at the values of _x_ specified: (a) _f_ ( _x_ ) = _x_<sup>2</sup> _↑_ 3 _x_ at _x_ = 10

- (b) _f_ ( _x_ ) = 5 _x_<sup>5</sup> _↑_ 2 _x_ at _x_ = 0

- (c) _f_ ( _x_ ) = 10 _x ↑_ 3 _x_<sup>7</sup> at _x_ = _↑_ 2

33

**Question 2.4** : What function when differentiated gives the following [Hint: you will need to do the process of differentiation in reverse]:

- (a) _dx_<sup>_dy_= 2</sup><sup>_x_</sup>

- (b) _dx_<sup>_dy_=</sup><sup>_↑_3</sup><sup>_x_3</sup> (c) _dx_<sup>_dy_= 7</sup>

**Question 2.5** : Obtain the derivative of the following functions:

- (a) _y_ = 10 _x_ (5 _x_ + 3 _x_ )

- (b) _y_ = 50 _x_<sup>2</sup> + 30 _x_<sup>2</sup>

- (c) _y_ = 3 _ce_<sup>_ix_</sup>

- (d) _y_ =<sup>_~~→~~_</sup> _~~x~~_

- (e) _y_ = cos( _x_ )

- (f) _y_ = _e_<sup>5</sup><sup>_x_</sup>

- (g) _y_ = 3 _x_ + 5 _y_

- (h) _y_ = 2 _ln_ ( _x_ )

**Question 2.6** : Obtain the derivative of the following (slightly harder) functions:

- (a) _y_ = ! _i_ 3 _ce_<sup>_ix_</sup> <u>4</u> _<u>x</u>_

- (b) _y_ = ~~�~~ _!_

- (c) _y_ = cos( _x_ )+ sin( _x_ )

- (d) _y_ = _e_<sup>5</sup><sup>_x_+4</sup>

- (e) _y_ = _ln_ (2 _x_ )

- (f) _y_ = 4 _x_<sup>4</sup> + _e_<sup>_x_</sup> + sin( _x_ )

## Real-world problems

**Question 2.7** : The equation describing radioactive decay is:

where _N_ is the number of unstable nuclei, _t_ is time and _∀_ is called the decay constant. _∀_ =<sup><u>ln2</u></sup> _t_ 1 _/_ 2<sup>where</sup><sup>_t_1</sup><sup>_/_2 is the half-life of the sample.</sup>

The solution to equation 2.1 is

where _N_ 0 is the starting number of unstable nuclei (a constant).

In radioactive decay the number of unstable nuclei reduces with time. After a period of time known as the half-life. _t_ 1 _/_ 2, we have half the initial number of nuclei,<sup>_N_</sup> 2<sup><u>0</u>due</sup> to radioactive decay of the other nuclei. After another half-life we will have half those number of nuclei again (i.e.<sup>_N_</sup> 4<sup><u>0</u>).</sup>

34

Chapter 2. Introduction to Differentiation

This behaviour can also be described using:

where _n_ is the number of half-lifes that have elapsed.

- (a) Differentiate Equation 2.2 2.1.

- (b) A radioactive material has a half-life of _t_ 1 _/_ 2 = 30 years and there are 10 _,_ 000 nuclei in the sample. Using Equation 2.3, calculate how many nuclei there are after 90 years (i.e. 3 half-lifes).

- (c) Repeat the calculation using Equation 2.2.

**Question 2.8** : The hydrostatic equation describes how pressure changes with altitude in relation to other variables such as gravity and temperature. It is a fundamental principle in fluid mechanics and atmospheric science. We will use this a lot more later, but it has a similar formulation to the radioactive decay equation and is given (here) by

where _g_ , _Ra_ and _T_ are assumed to remain constant. Show that the following equation:

is a solution to the differential equation by differentiating and substituting it back into the differential equation.

**Question 2.9** : Imagine we are studying the volume of water in an ecosystem reservoir over time.

- (a) If we say that the volume of water in the system can be described as:

what is the drainage rate? Where _V_ 0 is the volume of water in our system when _t_ = 0, in _m_<sup>3</sup> . (take _V_ 0 = 1 _↓_ 10<sup>_↑_2</sup> )

- (b) In reality the water would drain at a non-constant rate. If we say that the volume of water in the reservoir can be described as:

what is the drainage rate at time 600s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using a finite difference method with a time step ∀ _t_ of 20 seconds, 10 seconds either side of 600s.

35

- (c) If we say that the volume of water in the sink can be described as:

what is the drainage rate at time 600s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using the finite difference method with a time step ∀ _t_ of 20 seconds, 10 seconds either side of 600s.

- (d) If we say that the volume of water in the sink can be described as:

what is the drainage rate at time 600 s? Use the process of differentiation to determine the gradient analytically, but also compare to a gradient calculated numerically using the finite difference method with a time step ∀ _t_ of 20 seconds, 10 seconds either side of 600s.
