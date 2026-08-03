---
title: "Ex3soln(1)"
source: "Sophomore/Hilary Term/EART28202/Practical/Week 5/Ex3soln(1).pdf"
type: pdf
---

# **Exercise 3 solution**

A state of stress (units MPa) is given in a Cartesian coordinate frame ( _x_ , _y_ ) by

<!-- Start of picture text -->
7 19<br>19 36<br><!-- End of picture text -->

## **Part (a)**

## **_Using a Mohr diagram, solve for the principal stresses,_** s **_1 and_** s **_2 , and the orientation,_** q **_, between_** s **_1 and the x- direction._**

The state of stress is presented in tensor sign convention, and so first task is to determine the sign of the shear stresses using the Mohr circle convention. We draw a square element and orient the stresses in an ( _x_ , _y_ ) coordinate frame, noting that since the shear stresses are positive, for any given shear couple, on the side that cuts the negative axis the shear stress should be going in a positive direction. We then determine the sign of the shear stresses in Mohr circle convention (for given shear couple, clockwise is negative and anticlockwise is positive).

<!-- Start of picture text -->
Tensor sign convention Mohr circle sign convention<br>36 s = 36<br>shear sense on -ve axis s = 19 yy<br>side in +ve direction compression +ve yx<br>19 anticlockwise<br>s = 7<br>xx<br>y 7 y<br>s = -19<br>19 xy<br>clockwise<br>shear sense on -ve axis<br>side in +ve direction<br>x x<br>We can now draw the Mohr circle and read off the answers.<br>t (36 , 19)<br>( s yy , s yx  )<br>20 y -direction s1<br>s<br>10 2<br>s yy<br>2q = 232.65° s yx<br>s2 = -2.4 MPa s1 = 45.4 MPa x -direction<br>10 30 40 50 s n s xy s xx<br>20<br>-10 s<br>2<br>q = 116.3°<br>-20 s<br>1<br>x -direction<br>( s xx , s xy  )<br>(7 , -19)<br><!-- End of picture text -->

**Part (b)**

## **_Check your answers to (a) using the formulae,_**

With

then

With the value of q , note that in the range 0-180° there are two values of q that satisfy the tan 2 q equation (one finds the angle to s 1 and the other to s 2). These differ by 90° (26.3 + 90 = 116.3°). The rules for selecting the correct one are listed in the notes supporting the stress lecture (see also Jaeger _et al._ , 2007, _Fundamentals of Rock Mechanics_ (4th edition), Blackwell, p.21). In this case s _xx_ < s _yy_ and s _xy_ < 0 (Mohr circle sign convention) and so the angle between the _x_ -direction and s 1 lies between 90° and 135°. Hence 116.3° is the correct solution.

## **Part (c)**

**_Using your Mohr diagram, determine the value of normal stress (_** s **_n ) and shear stress (_** t **_) on a plane oriented at 30° anticlockwise to the x direction._**

<!-- Start of picture text -->
t plane at 30°to x (36 , 19)<br>22.1 ( s yy , s yx  )<br>s1 20 y -direction<br>+ve: anticlockwise<br>s2 10<br>s yy 30°<br>s yx x -direction s2 12.3 2q = 112.65° s1<br>s xx s n<br>s xy 10 30 40 50<br>a = -60° 2a = 120°<br>s -10<br>2<br>q = 56.33°<br>s normal -20<br>1<br>to plane x -direction<br>( s xx , s xy  )<br>(7 , -19)<br><!-- End of picture text -->

## **Part (d)**

## **_Check your answers to (c) using the formulae,_**

With

then

## **Part (e)**

**_Solve for_** s **_1_** , s **_2, and_** q **_by finding the eigenvalues of the stress matrix given above and the eigenvector associated with_** s **_1 ._**

We seek to convert our original stress matrix into a diagonal equivalent:

In doing this we seek the eigenvalues and eigenvectors of the matrix so that

**_Av_** = l **_v_**

where **_A_** is a square matrix (here our stress matrix), and **_v_** is the eigenvector associated with eigenvalue l . We can rewrite this equation as

where **_I_** is the unit matrix. For non-zero eigenvector, this requires that the determinant, | **_A_** - l **_I_** | = 0.

• First we find the matrix, **_A_** - l **_I_**

- Then we find the determinant of this matrix and set it equal to zero

- Using the quadratic formula we then solve for the two values of l

• We now seek the eigenvector corresponding to the eigenvalue of 45.4:

<!-- Start of picture text -->
A v = l v<br>7 19 1 1<br>check: =    45.4<br>19 36 2.02 2.02<br>45.4 45.4<br>=<br>91.7 91.7<br><!-- End of picture text -->

- Now to convert this eigenvector into the angle between s 1 and the _x_ -direction:

<!-- Start of picture text -->
s tan q = 2.02 / 1<br>1<br>q = 63.7°<br>2.02<br>s yy q<br>s yx 1<br>x -direction<br>s xx<br>s xy<br>or from s1 clockwise to  x<br>q = 180 - 63.7  =  116.3°<br>s<br>1<br>-direction<br>y<br><!-- End of picture text -->

- The eigenvector corresponding to the eigenvalue of -2.4 is at 90° to this.
