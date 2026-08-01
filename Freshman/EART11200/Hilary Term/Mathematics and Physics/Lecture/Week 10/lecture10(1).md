---
title: "lecture10(1)"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 10/lecture10(1).pdf"
type: pdf
---

# **EART11200 - The Natural Scientist’s Toolkit**

# **Mathematics and Physics**

_Week 10 Lecture - Vectors and Partial Differentiation_

1/ 23

## LAST WEEK...

- **Second-order ordinary differential equations** are ODEs that involve a **second-order**

   - **derivative** .

- We could devote an entire course looking at solving different types of second-order ODEs, but we will only concentrate on

where _a_ , _b_ and _c_ are constants.

- This is referred to as a **homogeneous, linear, second-order ODE** .

- Note that we can write the exact same expression using alternative notation as per the following equation:

2/ 23

## LAST WEEK...

- To solve these second-order ODEs we first write out the **auxiliary** equation:

- Find roots of the quadratic equations using:

- If _λ_ 1 and _λ_ 2 are real and not equal ( _λ_ 1 = _λ_ 2 then we can write a general solution as:

- If our two roots are real and equal (i.e. _λ_ 1 = _λ_ 2) then we use the formula:

3/ 23

LAST WEEK...

- To find the values of the constants _A_ and _B_ , we use information such as _y_ = 0 and _y_ = 1 when _x_ = 0.

- These are called **initial conditions** , and they tell us the value of the solution and/or its derivatives at a specific point, allowing for a unique solution to the differential equation.

- This will lead us to solving simultaneous equations.

### ▶ Once we

4/ 23

## LAST WEEK...

- Fick’s and Fourier’s Laws describe the transfer of mass and heat.

- If we assume steady state, we get second-order ODEs which we can simply integrate twice

- We can use boundary conditions to solve this and find an expression.

- **Boundary value problems** differ from **initial value problems** as we specify upper and lower boundary conditions are specified (i.e, when _x_ = _x_ 0 and _x_ = _x_ 1).

- This gives us more information this means that we have to make the solution meet at both points.

5/ 23

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

6/ 23

## INTENDED LEARNING OUTCOMES

- (1) Describe the properties of scalar and vector fields and their applications in mathematics and physics

- (2) Apply basic vector operations, such as addition, subtraction, scalar multiplication, and magnitude, in theoretical and real-world applications.

- (3) Compute partial derivatives to determine rates of change of scalar fields in theoretical and real-world applications.

7/ 23

## WORKING IN MORE THAN ONE DIMENSION

- The topics Differentiation (Weeks 1-5) and Integration (Weeks 6-9) were centred around a

   - function in one variable or dimension

_y_ = _f_ ( _x_ )

- We differentiated or integrated in terms of that one variable:

- In many cases, we may need to work in more than one dimension (e.g. in space)

- So, we conclude the course by looking at **scalar fields** , **vectors** and **partial differentiation** .

8/ 23

## SCALAR FIELDS

▶ A **scalar field** is a function of two or more variables

- Scalar fields represent a single value at different positions.

▶ They have **magnitude but no direction** and can be represented with a colour plot.

- For example, wind speed – but not direction.

- In essence, they are functions in higher dimensions than we have seen thus far.

9/ 23

## VECTOR FIELDS

- A **vector field** is a mathematical function that assigns a vector to each point in space.

- For example, wind speed – but not direction.

- They have **magnitude and direction** as we can determine a direction, or flow and the magnitude from the length of the arrow.

<!-- Start of picture text -->
10<br>10 10<br>5 5 5<br>0 0 0<br>−5 −5 −5<br>−10 −10<br>−10<br>−10 −5 0 5 10 −10 −5 0 5 10 −10 −5 0 5 10<br>x x x<br>y y y<br><!-- End of picture text -->

10/ 23

## VECTOR NOTATION

- Each line in this figure represents the same vector, but a different starting position.

- Wherever the starting position is, each vector moves 2

units to the left and 5 units up.

- If we write this procedure in vector form we write:

_v_ = _⟨−_ 2 _,_ 5 _⟩_

- Notice the distinction in style between the variable and

the brackets.

- Specifically, _⟨−_ 2 _,_ 5 _⟩_ is fundamentally different from

writing ( _−_ 2 _,_ 5).

11/ 23

## VECTOR NOTATION

- A vector can be written more generally as:

_v_ = _⟨a_ 1 _, a_ 2 _⟩_

where _a_ 1 and _a_ 2 describe shifts along the axes.

- Now, imagine this vector represents movement from point _A_ to _B_ . In this case, we write the vector as _AB_ .

▶ In 2D space, if point _A_ has coordinates _A_ = ( _x, y_ ) and point _B_ has coordinates _B_ = ( _x_ + _a_ 1 _, y_ + _a_ 2), the vector _AB_ describes the displacement.

- Note the difference in notation between vectors and

coordinates.

12/ 23

## VECTOR NOTATION

- The direction indicated by the arrow over the vector,

_AB_ , specifies movement from point _A_ to _B_ .

- If the coordinates of _A_ and _B_ are given as _A_ = ( _a_ 1 _, a_ 2) and _B_ = ( _b_ 1 _, b_ 2), the vector _v_ describing _AB_ is:

- If our vector now starts at _B_ and moves to _A_ , thus _BA_ , then we can write:

- Using a **start minus end** approach.

13/ 23

## UNIT VECTORS

- We consider vectors in Cartesian form, that is broken

   - down into components along _x_ and _y_ of a Cartesian domain.

- The component along _x_ is component<sup>ˆ</sup> _i_ and along _y_ is component<sup>ˆ</sup> _j_ .

- Here,<sup>ˆ</sup> _i_ and<sup>ˆ</sup> _j_ are all called unit vectors and have length

equal to 1.

14/ 23

## EXAMPLE: UNIT VECTORS

- For example, take a look at the following vector:

4<sup>ˆ</sup> _i_ + 3<sup>ˆ</sup> _j_

- For every movement 4 units along the x axis there is 3 units of movement along the y axis.

- Note that this is equivalent to writing

_v_ = _⟨_ 4 _,_ 3 _⟩_

15/ 23

## VECTOR CALCULATIONS

- The magnitude of a vector is calculated by taking the square root of all of the square its components

   - (i.e. Pythagoras’ theorem):

- Vectors can be added or subtracted (add or subtract by component) or multiplied by a scalar (constant).

- Given the vectors _a_ = _⟨a_ 1 _, a_ 2 _⟩_ and _b_ = _⟨b_ 1 _, b_ 2 _⟩_ :

16/ 23

## EXAMPLE: VECTOR CALCULATIONS

▶ For example, if ¯ _a_ = _⟨_ 4 _,_ 3 _⟩_ = 4<sup>ˆ</sup> _i_ + 3<sup>ˆ</sup> _j_ ,<sup>¯</sup> _b_ = _⟨_ 2 _,_ 1 _⟩_ = 4<sup>ˆ</sup> _i_ + 3<sup>ˆ</sup> _j_ and _c_ = 2 then:

_a_ + _b_ = _⟨_ 4 + 2 _,_ 3 + 1 _⟩⟨_ 6 _,_ 4 _⟩ a − b_ = _⟨_ 4 _−_ 2 _,_ 3 _−_ 1 _⟩_ = _⟨_ 2 _,_ 2 _⟩ ca_ = _⟨_ 2 _×_ 4 _,_ 2 _×_ 3 _⟩_ = _⟨_ 8 _,_ 6 _⟩ |_ ¯ _a|_ = ~~�~~ 4<sup>2</sup> + 3<sup>2</sup> = _~~√~~_ 25 = 5

17/ 23

## PARTIAL DIFFERENTIATION

- We now think about differentiation of functions of two (or more) variables (i.e. scalar field),

   - _z_ = _f_ ( _x, y_ ), which now depend on _x_ and _y_ .

- For a one dimensional curve the gradient<sup>_d_</sup> _dx_<sup>_<u>y</u>_is fairly straight forward.</sup>

- When using more than 1D, we have to use something else to denote the gradient.

- The standard that is used is called ‘grad’, which is defined for a scalar field and can be written

- Note that _∇f_ (where _f_ = _f_ ( _x, y, z_ ) is a scalar field) is actually a vector.

18/ 23

## PARTIAL DIFFERENTIATION

- The gradient has magnitude and direction!

- Notice the change in the derivative symbol:

_∂f_

_∂x_

- Up to this point in our course, we have been using the expression:

_df dx_

- The change is important as this is called a **partial derivative** .

- When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant.

19/ 23

## PARTIAL DIFFERENTIATION

- The gradient has magnitude and direction!

- Notice the change in the derivative symbol:

_∂f_

_∂x_

- Up to this point in our course, we have been using the expression:

_df dx_

- The change is important as this is called a **partial derivative** and we move into using **partial differential equations** .

- When you have a function expressed using more than one dimension, this means that when calculating a derivative in say _x_ , you assume other variables such as _y_ or _z_ remain constant.

20/ 23

## EXAMPLE: PARTIAL DIFFERENTIATION

- Let’s find the partial derivatives of the following function:

- If we take _y_ as constant then we calculate partial derivative of _f_ with respect to _x_ :

_∂f ∂x_<sup>= 2</sup><sup>_y_</sup>

- The second term disappears here as it has no _x_ within it.

- If we take _x_ as constant then we calculate partial derivative of _f_ with respect to _y_ :

_∂f ∂y_<sup>= 2</sup><sup>_x_+ 2</sup><sup>_y_</sup>

21/ 23

## EXAMPLE: PARTIAL DIFFERENTIATION

▶ Putting this into vector form gives us:

- We can use this to calculate the magnitude of the gradient at any given point.

22/ 23

## PARTIAL DIFFERENTIAL EQUATIONS

- We could go even further and take second partial derivatives of _f_ to obtain get _∇_<sup>2</sup> _f_ .

- This would mean partial differentiating with respect to _x_ and _y_ :

- As we are differentiating twice with respect to all combinations of the variables, _∇_<sup>2</sup> _f_ is a matrix which has amazing properties, but this is outside of this course!

- Integrating partial differential equations analytically can only be done for simple cases and requires knowledge of Fourier methods, which is also outside of this course.

- Nearly all modern weather forecast models use approximate methods to find solutions of

**partial differential equations** .

23/ 23
