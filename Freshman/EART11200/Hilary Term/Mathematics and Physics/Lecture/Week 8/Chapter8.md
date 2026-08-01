---
title: "Chapter8"
source: "Freshman/EART11200/Hilary Term/Mathematics and Physics/Lecture/Week 8/Chapter8.pdf"
type: pdf
---

# 8. Integration by Substitution

## 8.1 Overview

In Chapters 6 and 7, we introduced rules that allow us to directly integrate certain basic functions if we can recognize their forms. These can be found in this table:

|Differential equation <sup>_dy_</sup><br>_dx_|Integral,_y_|
|---|---|
|constant|_constant →x_+_d_<br>|
|_x_|_x_<sup>2</sup><br>2 <sup>+</sup><sup>_d_</sup>|
|3_x_<sup>2</sup>|_x_<sup>3 </sup>+_d_|
|_x_<sup>3</sup>|_x_<sup>4</sup><br>4 <sup>+</sup><sup>_d_</sup>|
|...|...|
|_x_<sup>_n_</sup><br>_ax_<sup>_n_</sup>|_x_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup><br>_ax_<sup>_n_+1</sup><br>_n_+1 <sup>+</sup><sup>_d_</sup>|
|_ke_<sup>_kx_</sup>|_e_<sup>_kx_ </sup>+_d_|
|1<br>_x_|_ln_(_x_)+_d_|
|_cos_(_x_)|_sin_(_x_)+_d_|
|_sin_(_x_)|_↑cos_(_x_)+_d_|

There may be a need to rearrange the equation, often by using techniques like separation of variables (e.g., rearranging _N_ and _t_ ) before we can use them, but they are there for us to use. Furthermore, like differentiation for a sum of functions, the **integral of a sum** is equal to the **sum of the integrals** of the individual functions.

120

Chapter 8. Integration by Substitution

In some cases, we cant directly integrate by using these rules, as we are faced with more complicated combinations of functions such as **functions of functions** . For example, what happens if we want to integrate

### This is where **integration by substitution** comes in.

## 8.2 Integration by substitution

**Integration by substitution** is essentially the reverse process of the **chain rule** in differentiation. Let’s return to the example where we want to evaluate

At first glance, it may appear that this resembles the derivative of some function, allowing us to integrate directly. What if we replace the expression in the brackets with another variable such that we can integrate using the rules we already know? Making a **substitution** can often simplify things and enables us to perform what seems to be an otherwise difficult integration.

Lets use _u_ = 3 _x_ + 2 so the integral becomes

Now, the integral is expressed in terms of _u_ , but we need to address the _dx_ . This is asking us to integrate _u_ with respect to _x_ . Since _dx_ relates to _x_ , we need to rewrite it in terms of _u_ . This step ensures that the integral is entirely in terms of the new variable. When the integral contains a factor like _ax_ + _b_ , substituting _u_ = _ax_ + _b_ often simplifies the problem. Along with the substitution, we must also determine _dx_ in terms of _u_ to complete the process.

Let’s show how **integration by substitution** works in full:

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

121

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Make the substitution in the original integral

7. Integrate as usual:

8.

Let’s see some more examples of this.

**Example 8.1** : Lets evaluate the integral

Let’s use _u_ = _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = _x_ + 4 back in gives us:

You can differentiate using the chain rule to verify that this works.

**Example 8.2** : Lets evaluate the integral

122

Chapter 8. Integration by Substitution

Let’s use _u_ = 3 _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:

and substituting _u_ = 3 _x_ + 4 back in gives us:

You can differentiate using the chain rule to verify that this works.

So we see that we can integrate more complicated functions using substitution. We want to use a substitution so that the integration becomes something we can use our table of standard integrals for. However, this is integration by substitution for **indefinite integrals** . In many cases, we want to find the **area under a curve** so the integral has limits. For example,

therefore we have to perform **integration** . This means that we calculate the integral (using integration by substitution) then evaluate the integral but for the new limits calculated under the substitution.

**integration by substitution** works in full:

1. Write out the integral in its simplest form:

2. Find a new variable ( _u_ ) as a function of the old variable ( _x_ ) as a substitution:

3. Rearrange to get an expression for the old variable ( _x_ ) in terms of the new variable ( _u_ ):

123

4. Differentiate with respect to the new variable _u_ :

5. Get an expression for _dx_ :

6. Find the new limits of the integral:

7. Make the substitution in the original integral

8. Integrate as usual:

Let’s see some more examples of this.

**Example 8.3** : Lets evaluate the integral

Let’s use _u_ = _x_ + 4 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits:

Use these to make the substitution:

124

Chapter 8. Integration by Substitution

Now we can evaluate using the basic laws of integration:

**Example 8.4** : Lets evaluate the integral

Let’s use _u_ = _x_ + 10 as a substitution. Lets rearrange for _x_ , differentiate in terms of _u_ and find an expression for _dx_ :

Find the new limits:

Use these to make the substitution:

Now we can evaluate using the basic laws of integration:
