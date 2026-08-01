---
title: "Practical_3"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 3/Practical_3.ipynb"
type: notebook
---

# Practical 3: Modules and Functions - Introducing Numpy!

<div class="alert alert-block alert-success">
<b>Objectives:</b> In this practical the overarching objective is for you to practice using modules and functions. Following on from a discussion in class, this will be done through 4 sections in this notebook, each with its own exercise for you to practice:

 - 1) [Part 1: Learning how to use the Numpy module](#Part1)
      * [Exercise 1: Create a 2D array and populate with specific values](#Exercise1)
 - 2) [Part 2: Using conditional statements to modify values in an array using Numpy](#Part2)
      * [Exercise 2: Create a 2D array and populate with values according to an equation and condition](#Exercise2)
 - 3) [Part 3: Creating your own function](#Part3)
      * [Exercise 3: Create a spooky type-writer](#Exercise3)
      * [Exercise 4: Build a function that creates a 2D surface plot of a scalar function](#Exercise4)
 - 4) [Part 4: Numpy operations on entire arrays](#Part4)
      * [Exercise 5: Re-create a function that creates a 2D surface plot of a scalar function](#Exercise5)

As with our other notebooks, we will provide you with a template for plotting the results. Also please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Do try to finish as much as you can whilst we are here to help. Proposed solutions to all exercises can be found in the 'solutions' folder.
</div>

<div class="alert alert-block alert-danger">
<b> Using Google Colabs </b> Please note that the first code block ensures that we can install the module Cartopy IF we are running this example on Google Colab. Please run this code block and, if you are not on Google Colab, you will recieve a message that confirms this. If you are on Colabs, you will see messages regarding the status of the installation.
</div>

```python
if 'google.colab' in str(get_ipython()):
    from google.colab import drive
    mount='/content/gdrive'
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # Change to the directories to get data files
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root
else:
    print('Not running on CoLab')
```

    Not running on CoLab

## First, why modules and functions?

As we saw in the lecture for today, a typical computer program is contructed in a modular way. This is beneficial as your program gets bigger. It also allows you to develop and test routines seperately, making improvements or upgrades in a clear and transparent way.

A module is a file containing Python definitions and statements. The file name is the module name with the suffix <code> .py </code> appended. It will also likely contain functions we wish to use. For example, if we want to use a module we would use the following command:

```python
import *module name*
 ```
Where the module name is the same as the file

> *module name.py*

and, if not in the same directory, can be found by the Python interpreter. We will not cover this here, but you can also specify the location of modules you write yourself by changing what is called the Python path or by importing another module that adds the location in the code directly.

From this point on in our course, will be using the [Numpy](https://numpy.org) module. We can import it by including the following statement in our program or by writing this into the command line Python shell:

```python
import numpy
```

If you position your mouse in the above box and then click the <code> Run </code> button from the notebook menu, nothing appears to have happened. But it has! We now have access to all of Numpy's functionality. We can also import any module and change its name. This is useful if we constantly want to write and refer to a module. If you search for Python examples online, you will invariably see the following:

```python
import numpy as np
```

This is just common practice and proves to be much easier when using lots of functions held within Numpy, which we will get to shortly. We will also be using a number of other widely used modules in our course, including:

 - [Pandas](https://pandas.pydata.org): A module dedicated to data structures and data analysis tools.
 - [Scikit-learn](https://scikit-learn.org/stable/): A module dedicate to developing and deploying machine learning functions
 - [Scipy](https://www.scipy.org): (pronounced “Sigh Pie”) is a Python-based ecosystem of open-source software for mathematics, science, and engineering [including Numpy]
 - [Matplotlib](https://matplotlib.org): A module used for plotting, which we will use throughout the course.

On the plotting module, we will not provide specific training on this but provide you with templates that cover most basic examples from line, scatter to 3D plots. You can take these templates and modify them for your own benefit. You can also search for help online or via the official Matplotlib webpage: https://matplotlib.org

We normally import all of the modules we need at the start of any program. For example, if we want to import all of the above I would write:

```python
import numpy as np
import pandas as pd
import sklearn #the name of the module is different from the official title, but the .py will have this name
import matplotlib
```

Sometimes we do not want to import an entire module if we are only using one function out of many. As an example, in the Scikit-learn package I might only want to import a function that allows me to perform a technique known as K-means clustering. By checking the online documentation, I find that I should import this as:

```python
from sklearn.cluster import KMeans
```

Does the syntax make sense? The use of '.' is important. This is allowing me to access functions within the entire package. We will use this today as we explore the functionality of the Numpy package.

# Part 1:  Learning how to use the Numpy module  <a name="Part1"></a>

Numpy is a package used for numerical computations. It is used inplace of the vanilla Python approaches, as we used in the first lecture, on account of its speed and flexible functionality. For the remaining part of the course we will use Numpy to create and manipulate arrays. Let us go through some example and practice assigments on creating and manipulating 1D and 2D arrays

### 1.1) Creating 1D arrays

In the following code we import Numpy and use it to intialise two 1D arrays. One will contain integers, the other floating points. Please note that, unlike lists and tuples in Python, we **cannot** blend data types in one array via Numpy. This is ok for our course, however, and related to the efficiency of Numpy arrays. Please see the code snippet below and notice where we use the **'.'** extension to the imported packaged to access a function. We will write our own functions later on in this practical:

```python
# Lets import the numpy package and call it np
import numpy as np

# We can use an internal Numpy function to create a 1D array of fixed length. Lets say we want to create arrays
# with 15 elements. For this Im going to use the function numpy.zeros() to create an array filled with 0's.
# The official documentation for this function can be found here: https://docs.scipy.org/doc/numpy/reference/generated/numpy.zeros.html
# Lets look at our example for now

# Im going to use my own variable names for each array. This dosnt matter:
Integer_array = np.zeros((15,), dtype=int)
Float_array = np.zeros((15,), dtype=float)
```

Before we print these arrays to the screen, let us see what has happened here. The function **numpy.zeros()** is expecting at least two bits of information

> numpy.zeros((rows,columns), type of data)

Where, in our case, we have specified we want 15 entries but only in one dimension as we have ignored the 'columns' variable. If we wanted to specify a 2D array, or matrix, as we will do later with 15 rows and 4 columns, we would write:

> Integer_array = np.zeros((15,4), dtype=int)

Notice we also specified our data type in each case. The first uses **'dtype=int'** and the second **'dtype=float'**. The function **expects** this syntax, as you might see in the official documentation. Let us now print our arrays to the screen to see what we have created. The notebook will automatically run code in each block when we first load it. However if you change anything, click inside the box and then click the 'Run' button above:

```python
# Simply print the arrays to screen

print("The integer array looks like > ",Integer_array)
print("The floating point array looks like > ",Float_array)

# You should be able to see a difference in format, thus precision.
```

    The integer array looks like >  [0 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
    The floating point array looks like >  [0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]

### 1.2) 2D Numpy arrays and accessing/changing values

Now we can practice creating 2D arrays but also accessing and modifying/creating values. Let us create a 2D matrix that has 3 rows and 3 columns and then put a floating point number in every cell. Note the use of the **':'** operator that allows us to straddle the start and end indices of either a set of rows of columns.

Now let us read through the code in the box below.

```python
# Create an empty matrix, of 3 rows and 3 columns, using the numpy.zeros() function
matrix = np.zeros((3,3), dtype=float)

# Now lets put the value 298.15 in each cell. There are multiple ways we could do this. I demonstrate 4
# below, where one method is significantly quicker than the other from a data entry perspective

# 1) Enter all values manually. 1st row and 1st column, 1st row and 2nd column etc etc
matrix[0,0] = 298.15; matrix[0,1] = 298.15; matrix[0,2] = 298.15
matrix[1,0] = 298.15; matrix[1,1] = 298.15; matrix[1,2] = 298.15
matrix[2,0] = 298.15; matrix[2,1] = 298.15; matrix[2,2] = 298.15
# Lets print the matrix to the screen
print(" first entry method result = ", matrix)

# 2) Assign the value to every column as a function of each row using the ':' operator
matrix = np.zeros((3,3), dtype=float)
matrix[0,0:3] = 298.15
matrix[1,0:3] = 298.15
matrix[2,0:3] = 298.15
# Lets print the matrix to the screen
print(" second entry method result = ", matrix)

# 3) Assign the value to every row as a function of each column using the ':' operator
matrix = np.zeros((3,3), dtype=float)
matrix[0:3,0] = 298.15
matrix[0:3,1] = 298.15
matrix[0:3,2] = 298.15
# Lets print the matrix to the screen
print(" third entry method result = ", matrix)

# 4) Assign every cell using the ':' operator in 2 dimensions
matrix = np.zeros((3,3), dtype=float)
matrix[0:3,0:3] = 298.15
# Lets print the matrix to the screen
print(" fourth entry method result = ", matrix)

```

     first entry method result =  [[298.15 298.15 298.15]
     [298.15 298.15 298.15]
     [298.15 298.15 298.15]]
     second entry method result =  [[298.15 298.15 298.15]
     [298.15 298.15 298.15]
     [298.15 298.15 298.15]]
     third entry method result =  [[298.15 298.15 298.15]
     [298.15 298.15 298.15]
     [298.15 298.15 298.15]]
     fourth entry method result =  [[298.15 298.15 298.15]
     [298.15 298.15 298.15]
     [298.15 298.15 298.15]]

Remember that, in Python, indexing starts at 0. For a 2D Numpy array, a nice schematic is provided by [O'Reilly](https://www.oreilly.com/library/view/python-for-data/9781449323592/ch04.html) below.

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Nump_array_indexing.png?raw=true)

<div class="alert alert-block alert-success">
<b> Exercise 1: Create a 2D array and add specific values.  <a name="Exercise1"></a> </b> Now it is your turn to practice these operations. In the box below, you are tasked with the following:

 - Create an empty 2D array with 5 rows and 6 columns, containing floating point values.
 - For the first two rows the array will contain a value of 2.5
 - For the remaining rows to contain a value of 5.5.
 - Print the array to the screen so you can check your answer.

Your answer should look like this:

```python
matrix result =  [[2.5 2.5 2.5 2.5 2.5 2.5]
 [2.5 2.5 2.5 2.5 2.5 2.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]]
```
</div>

<div class="alert alert-block alert-warning">
    <b>HINT</b>: Rather than writing an entry for each cell, why not try using the technique demonstrated in example 2 and 3 above. </div>

```python
#------'INSERT CODE HERE'------

# Initialise an empty 2D array using the np.zeros function
practice_matrix = np.zeros((5,6), dtype=float)

# Populate the array with appropriate values
practice_matrix[0:2,0:7]=2.5
practice_matrix[2:6,0:7]=5.5

#------------------------------

# Lets print the matrix to the screen
print(" matrix result = ", practice_matrix)

```

     matrix result =  [[2.5 2.5 2.5 2.5 2.5 2.5]
     [2.5 2.5 2.5 2.5 2.5 2.5]
     [5.5 5.5 5.5 5.5 5.5 5.5]
     [5.5 5.5 5.5 5.5 5.5 5.5]
     [5.5 5.5 5.5 5.5 5.5 5.5]]

# Part 2: Using conditional statements to modify values in an array using Numpy  <a name="Part2"></a>

In the first two practicals we came across **for loops** and conditional statements. We can combine these with Numpy arrays to start building a basis for numerical models. We can then turn a given combination of the above into a function that we can call over and over again. Let us start with an example. In the code snippet below, you can see a loop that populates a 1D Numpy array <code> Y </code> with 100 cells, according to the function:

\begin{eqnarray}
Y = X^{2.0}
\end{eqnarray}

Where <code> X </code> is an array that contains values from 1 to 100. This example combines a number of operations we have covered so far, including:

 - Initialising a 1D Numpy array of specific size, designed for floating point values
 - Creating a 'for' loop that cycles through integer values
 - Accessing a specific entry in a 1D array through an index value, remembering that Python indexing starts at 0.
 - Raising a number to a power
 - Print values to the screen

When you run the code below you will see the output:

```python
the value of the 98th component of x is  98.0
the value of the 98th component of y is  9604.0
the value of the 99th component of x is  99.0
the value of the 99th component of y is  9801.0
the value of the 100th component of x is  100.0
the value of the 100th component of y is  10000.0
```

```python
# First create an empty array for both x and y
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)

# Now implement a *for* loop that cycles through 100 values and creates the X and thus Y values
for step in range(100):
    x[step] = step+1 # We need to create the x array starting from 1
    y[step] = x[step]**2.0

# print the final 3 values for both x and y
print("the value of the 98th component of x is ", x[97])
print("the value of the 98th component of y is ", y[97])

print("the value of the 99th component of x is ", x[98])
print("the value of the 99th component of y is ", y[98])

print("the value of the 100th component of x is ", x[99])
print("the value of the 100th component of y is ", y[99])
```

    the value of the 98th component of x is  98.0
    the value of the 98th component of y is  9604.0
    the value of the 99th component of x is  99.0
    the value of the 99th component of y is  9801.0
    the value of the 100th component of x is  100.0
    the value of the 100th component of y is  10000.0

What about accessing and modifying values in a 2D array? We can 'nest' multiple *for* loops to deal with each dimension. Below is an example where we populate values in a 2D array, of 100 rows and 100 columns, according to the following function:

\begin{align*}
z = x+y
\end{align*}

Where variable <code> X </code> represents a row index and <code> Y </code> represents the column index. <code> Z </code> is a 2D array which is then plotted using the matplotlib package, assuming you use a 2D Numpy array for <code> Z </code>. Read through the comments associated with each step, can you recognise the stages of constructing this set of operations?

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the Numpy arrays
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)
z = np.zeros((100,100), dtype=float)

# Lets populate our x and y arrays with values from 1 to 100
for step in range(100):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

# Now create a nested loop that cycles through each dimension to produce our z array
# Thus the first loop cycles through each row
for row in range(100):
    # The second loop cycles through each column.
    for column in range(100):
        z[row,column]=x[row]+y[column]

# Plot the results. Dont worry about the Matplotlib template for now.
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

![png](output_24_0.png)

Before we move on to the second exercise, let us look at what is happening in our 'nested' loop. In English, the operation is designed to populate values in our 2D array, or matrix, as follows:

1) Specify a for loop for the row index. Lets call this variable 'row'. This cycles through values from 1 to 100. The index is our row number.

2) For each row number, lets cycle through each column index. Lets call this variable 'col'. This is equivalent to scanning across a matrix left-right.

3) Now we have a value for a row and column index. Use these indices to extract values from our X and Y arrays, as X[row] and Y[col].

4) Use these values to create an entry into our 2D array 'Z' as Z[row,col] = X[row]+Y[col].

<div class="alert alert-block alert-success">
<b> Exercise 2: Create a 2D array and populate with values according to an equation  <a name="Exercise2"></a> </b>

In this practice exercise, your goal is to use a *for* loop to populate a 2D Numpy array with 200 rows and 300 columns based on the following equation:

\begin{align*}
z = x+y*x
\end{align*}

Where variable <code> X </code> is an array that holds the row index and <code> Y </code> is an array that holds the column index. <code> Z </code> is a 2D array which is then plotted using the matplotlib package. If successful, your simulation should generate a plot given by the figure below.

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical3_example.png?raw=true)

</div>

<div class="alert alert-block alert-warning">
    <b>HINT</b> You will need to use a nested 'for' loop to cycle through the rows and columns. Check out our previous example above. Remember that Python expects indentation after the ':' operator.</div>

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the arrays
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)
z = np.zeros((100,100), dtype=float)

#  ------- 'INSERT CODE HERE' ---------
# Lets populate our x and y arrays with values from 1 to 100
for step in range(100):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

#  ------- 'INSERT CODE HERE' ---------
# Now create a nested loop that cycles through each dimension to produce our z array
# Thus the first loop cycles through each row
for row in range(100):
    # The second loop cycles through each column.
    for column in range(100):
        z[row,column]=x[row]+y[column]*x[row]

# Plot the results. Dont worry about the Matplotlib template for now.
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

![png](output_27_0.png)

## Part 3: Creating your own function <a name="Part3"></a>

In the same way we have started to use functions included within the Numpy package, we can write our own functions to perform specific tasks. This might be a numerical operation, or string manipulation task. This brings us closer to modular software development. In the example below we define a function with the keyword **'def'** and then call the function to receive its output. For example:

```python
# Lets define a function called 'test'. This function will simply write a message to the screen.

def test():
    print("All work and no play makes Jack a dull boy")
    return

# Call the function
test()
```

    All work and no play makes Jack a dull boy

Let us understand a few important features used in defining the function:

 - The 'def' keyword defined a function by its name.
 - The parenthesis () can take a list of inputs that the function needs.
 - The function name and input list is terminated with a colon ':'.
 - The next line, thus internal workings of the function, is *idented* by 4 spaces.
 - A 'return' statement closes the function definition.

<div class="alert alert-block alert-success">
<b> Exercise 3: Re-create the repeated output from the typerwriter in the Shining...  <a name="Exercise3"></a> </b>

    Using the example function above, combine this function call with a <code> FOR </code> loop to print 30 instances of the sentence to the screen.

</div>

<div class="alert alert-block alert-warning">
    <b>HINT</b>: Remember that a <code> FOR </code> loop takes the format: 'for "variable" in range(number):' </div>

```python
# Lets define a function called 'test'. This function will simply write a message to the screen.

def test():
    print("All work and no play makes Jack a dull boy")
    return

# Call the function in a 'for' loop, 30 times
for step in range(30):
    test()
```

    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy
    All work and no play makes Jack a dull boy

Before we move on to the final exercise, let's look at another example on populating a 2D array with the function:

\begin{align*}
z = x+y
\end{align*}

Where we are going to implement this equation as a function, which is passed arrays <code> X </code> and <code> Y </code> and returns <code> Z </code>. Read through the code below and see if this makes sense. Can you notice where we have now put the nested loops inside a new function?

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the arrays
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)

# Lets populate our x and y arrays with values from 1 to 100
for step in range(100):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

# Implement the equation z=x+y as a function
def create_z_array(x,y):
    # Initialise the z array
    z = np.zeros((100,100), dtype=float)
    # Now create a nested loop that cycles through each dimension to produce our z array
    # Thus the first loop cycles through each row
    for row in range(100):
        # The second loop cycles through each column.
        for column in range(100):
            z[row,column]=x[row]+y[column]

    # return the z array
    return z

# Call the function that generates our z array
z=create_z_array(x,y)

# Plot the results. Dont worry about the Matplotlib template for now.
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

![png](output_33_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 4: Build a function that creates a 2D surface plot of a scalar function <a name="Exercise4"></a> </b>

In this practice assignment, you are tasked with inserting all of the code [except the plotting function] to replicate the function used in Practice '2':

\begin{align*}
z = x+y*x
\end{align*}

Where variable <code> X </code> represents the row number and <code> Y </code> represented the column number. In this instance we have 200 rows and 200 columns and the procedure to populate our <code> Z </code> array should be included as a function.

</div>

<div class="alert alert-block alert-warning">
    <b>HINT</b>: The majority of this code has already been written earlier in this practical, but you need to reformat this to be called as a function. Also note the change in number of rows and columns. </div>

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the arrays
x = np.zeros((300,), dtype=float)
y = np.zeros((300,), dtype=float)
z = np.zeros((300,300), dtype=float)

#  ------- 'INSERT CODE HERE' ---------
# Lets populate our x and y arrays with values from 1 to 100
for step in range(300):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

#  ------- 'INSERT CODE HERE' ---------
# Now create a nested loop that cycles through each dimension to produce our z array
# Thus the first loop cycles through each row
def create_z(x,y,z):
    for row in range(300):
        # The second loop cycles through each column.
        for column in range(300):
            z[row,column]=x[row]+y[column]*x[row]

    return z

z=create_z(x,y,z)

# Plot the results. Dont worry about the Matplotlib template for now.
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

![png](output_35_0.png)

# Part 4:  Numpy operations on entire arrays  <a name="Part4"></a>

Once we start writing *large* modules we need to start thinking about how efficient our procedures are. In many areas of research, time of computation is a fundamental hurdle to increasing complexity. We will not cover optimisation in this course, but it is useful to start considering where we might use more efficient options in numerical computation. The standard Numpy library offers us multiple options which also helps to reduce the size of our code and, potentially, make it more readable!

### 4.1) Operations on a 1D Array

A [nice example](https://www.pluralsight.com/guides/overview-basic-numpy-operations) is provided by using arithmetic operators with Numpy. If we have 2 arrays, array1 and array2, created through:

```python
array1 = np.array([10,20,30,40,50], dtype=int)
array2 = np.array([0,1,2,3,4], dtype=int)
array3 = array1+array2
```
what might our answer look like? Lets run this code below and print to the screen

```python
import numpy as np

array1 = np.array([10,20,30,40,50], dtype=int)
array2 = np.array([0,1,2,3,4], dtype=int)
array3 = array1+array2

print("array3 = ", array3)
```

    array3 =  [10 21 32 43 54]

Rather than cycling through each element using a loop, this was much easier to write. What exactly is going on? The [visualisation](https://www.pluralsight.com/guides/overview-basic-numpy-operations) below should help:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/adding_arrays.png?raw=true)

### 4.2) Operations on a 2D Array

Unsurprisingly, we can also perform common arithmetic operations on 2D arrays. For example, let us add two 2D arrays [matrices] tother as per the following example:

```python
# Initiliase two empty matrices, A and B
A = np.zeros((3,3), dtype=float)
B = np.zeros((3,3), dtype=float)

# Set all cells in A to 2.4 and all cells in B to 1.6.
A[:,:]=2.4
B[:,:]=1.6

# Lets print the result of adding both together
print(A+B)
```

    [[4. 4. 4.]
     [4. 4. 4.]
     [4. 4. 4.]]

All the arithmetic operations work in a similar way. We can also multiply or divide the arrays. In the example below, see how we multiply matrix <code> A </code> by matrix <code> B </code>.

```python
print(A*B)
```

    [[3.84 3.84 3.84]
     [3.84 3.84 3.84]
     [3.84 3.84 3.84]]

We can demonstrate how each cell is multiplied together with another example:

```python
# Create two new matrices by manually writing out a Numpy array
C = np.array([[3,2],[0,1]])
D = np.array([[3,1],[2,1]])
# Multiply them both together. Can you confirm each cell has been acted on independently?
print(C*D)
```

    [[9 2]
     [0 1]]

<div class="alert alert-block alert-success">
<b> Exercise 5: Re-create a function that creates a 2D surface plot of a scalar function <a name="Exercise5"></a> </b>

In this practice assignment, you are tasked with inserting all of the code [except the plotting function] to replicate the function used in Exercise '4':

\begin{align*}
z = x+y*x
\end{align*}

Where variable <code> X </code> represents the row number and <code> Y </code> represented the column number. In this instance we have 200 rows and 200 columns and the procedure to populate our <code> Z </code> array should be included as a function. To start you off, I have initialised both <code> X </code> and <code> Y </code> as 2D arrays for you to use

</div>

<div class="alert alert-block alert-warning">
    <b>HINT</b>: The majority of this code has already been written earlier in this practical, but you need to reformat this to be called as a function. Also note the change in number of rows and columns. </div>

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the arrays
x = np.zeros((300,300), dtype=float)
y = np.zeros((300,300), dtype=float)
z = np.zeros((300,300), dtype=float)

# Lets populate our x and y arrays with values from 1 to 100
for step in range(300):
    x[step,:]=step+1 # why do we add 1?
    y[:,step]=step+1 # why do we add 1?

#  ------- 'INSERT CODE HERE' ---------
# Now create a nested loop that cycles through each dimension to produce our z array
# Thus the first loop cycles through each row
def create_z(x,y,z):
    z=x+y*x
    return z
#  ------------------------------------

z=create_z(x,y,z)

# Plot the results. Dont worry about the Matplotlib template for now.
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

![png](output_46_0.png)

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Introduced the idea of **modules** and why we use them to extend Python’s capabilities
> - Learned how to **import modules**, focusing on the `numpy` module
> - Created and worked with **NumPy arrays**, including:
>   - 1D and 2D arrays
>   - Populating arrays with specific values
> - Used **conditional statements** to modify values inside NumPy arrays
> - Applied equations to arrays to generate values automatically
> - Wrote our own **functions** to:
>   - Package code into reusable blocks
>   - Take inputs and return outputs
> - Practised building functions that:
>   - Manipulate arrays
>   - Produce visual outputs such as 2D surface plots
> - Learned how NumPy can perform **operations on entire arrays at once**, without explicit loops
>
> 🧠 *The focus was on writing cleaner, more powerful code by using modules, functions, and NumPy’s ability to work with whole datasets efficiently.*

```python

```
