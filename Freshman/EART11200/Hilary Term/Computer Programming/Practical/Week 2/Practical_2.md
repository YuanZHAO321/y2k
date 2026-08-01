---
title: "Practical_2"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 2/Practical_2.ipynb"
type: notebook
---

# Practical 2 - Loops and conditional statements

In today's practical we are going to continue practicing working with loops whilst also moving on to the use of conditional statements.

<div class="alert alert-block alert-success">
<b>Objectives:</b> The objectives of todays practical are:

 - 1) [Loops: FOR loops continued](#Part1)
      * [Exercise 1: Cycling through arrays and modifying values](#Exercise1)
 - 2) [Conditional statements: IF, ELSE and ELIF](#Part2)
      * [Exercise 2: Modify a loop to implement one of two equations according to a condition being met](#Exercise2)
 - 3) [Nested loops: Working with more than 1 dimension](#Part3)
      * [Exercise 3: Print out the result from a nested loop according to a condition being met](#Exercise3)
      * [Exercise 4: Print out which variables match a condition](#Exercise4)
      * [Exercise 5: Repeat Bob Newby's code breaking nested loops to crack the code in the Hawkins lab](#Exercise5)

Please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the 'Solutions' folder.
</div>

<div class="alert alert-block alert-warning">
<b>Please note:</b> After reading the instructions and aims of any exercise, search the code snippets for a note that reads ------'INSERT CODE HERE'------ to identify where you need to write your code
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

## 1) Loops: FOR loops continued <a name="Part1">

Let us jump straight into our first exercise, following on from the previous practical.

<div class="alert alert-block alert-success">
<b> Exercise 1: Cycling through arrays and modifying values. <a name="Exercise1">  </b> Create a loop that implements the function:

\begin{eqnarray}
Y = X^{2.8/X}
\end{eqnarray}

Where <code> x </code> is an array of 75 values from 11 to 85. Print the final 4 values of the <code> x </code> and <code> Y </code> array one-by-one. Your output should be:

```python
The 72nd element of x is  82
The 72nd element of y is  1.1623843156991178
The 73rd element of x is  83
The 73rd element of y is  1.1607534518329277
The 74th element of x is  84
The 74th element of y is  1.1591580160090038
The 75th element of x is  85
The 75th element of y is  1.157596831308393
```
</div>

```python
# Initiliase an empty list for both 'x' and 'y'
x = []
y = []

# Now loop through 75 values and append each list accordingly.
# One list contained values for 'x', the other 'y'.
# Please note the operator ** is needed to raise one number to another [e.g 2**3]
#------'INSERT CODE HERE'------
for step in range(75):

    # Append a value to our x array
    x.append(10+(step+1))

    # Append a value to our y array
    y.append(x[step]**(2.8/x[step]))
#------------------------------

# Print the last four values from both our x and y arrays
print("The 72nd element of x is ",x[71])
print("The 72nd element of y is ",y[71])

print("The 73rd element of x is ",x[72])
print("The 73rd element of y is ",y[72])

print("The 74th element of x is ",x[73])
print("The 74th element of y is ",y[73])

print("The 75th element of x is ",x[74])
print("The 75th element of y is ",y[74])

```

    The 72nd element of x is  82
    The 72nd element of y is  1.1623843156991178
    The 73rd element of x is  83
    The 73rd element of y is  1.1607534518329277
    The 74th element of x is  84
    The 74th element of y is  1.1591580160090038
    The 75th element of x is  85
    The 75th element of y is  1.157596831308393

## 2) Conditional statements: The IF, ELIF and ELSE statements  <a name="Part2">

Once we have information stored in an array, or wish to generate information iteratively, we start to use a combination of **loops** and **conditional statements**. Conditional statements allow us to develop software that can be responsive to certain conditions. For example, in the following control flow diagram we define a set of instructions that initiate a variable and start a loop that adds 3 to this variable at each iteration. However, at each iteration we also check the value of said variable and if it becomes equals or greater than 30, we stop the program.

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/If_example.png?raw=true)

The following table lists the Python equivalent of common mathematical symbols to check numerical values.

| Meaning | Math Symbol | Python Symbols |
| --- | --- | --- |
| Less than	 | < | < |
| Greater than	 | > | > |
| Less than or equal | ≤ | <= |
| Greater than or equal | ≥ | >= |
| Equals | = | == |
| Not equal | ≠ | != |

<div class="alert alert-block alert-danger">
<b> Warning </b> The obvious choice for equals, a single equal sign, is not used to check for equality. It is a common error to use only one equal sign when you mean to test for equality, and not make an assignment!
</div>

How do we implement checks using these symbols? This is where we use the <code> IF </code>, <code> ELIF </code> and <code> ELSE </code> statements. Let us start with an example.

```python
# Initialise two variables with integer values
x=3
y=5
# Now use an IF statement to check the relative values of x and y, then act accordingly
if x > y:
    print("X is greater than Y")
...
if x < y:
    print("X is less than Y")
..."X is less than Y"
```

Once again, notice how we have introduced a statement that ends with a colon : and thus requires the next line to be indented. We also use specific symbols to check whether one value is greater than [>] or less than [<] another. Within each condition check, depending on which is true, we print a message to the screen.

Rather than use two <code> IF </code> statements, we could combine these checks using an <code> ELSE </code> statement as follows:

```python
# Initialise two variables with integer values
x=3
y=5
# Now use an IF statement to check the relative values of x and y, then act accordingly
if x > y:
    print("X is greater than Y")
else x < y:
    print("X is less than Y")
"X is less than Y"
```

There are a huge number of examples we could work on here, but to begin let us build on the first exercise. In the following code we again have two variables <code> x </code> and <code> y </code>. Each has 50 elements. Let us assume that we want to implement two functions: one that is used if our <code> x </code> value is *less than or equal* to 20, the other if <code> x </code> is *greater than* 20. We can use a combination of the <code> IF </code> and <code> ELSE </code> statements.

 - If $X$ is *less than or equal* to 20, $ Y = \frac{X}{12.5} $
 - Otherwise [else], $Y = X^{12.5} $

Let us see this implemented as code below. Read through the syntax and if you do not understand, please ask.

<div class="alert alert-block alert-danger">
<b>Indexing </b> Once again, notice how we have introduced a statement that ends with a colon : and thus requires the next line to be indented.
</div>

```python
# Initiliase an empty list for both 'x' and 'y'
x = []
y = []

for step in range(50):

    # Append a value to our x array
    x.append(step+1)

    # Now add a conditional statement to check the value of x
    # Notice our additional indentation
    if x[step] <= 20:
        # Append a value to our y array
        y.append(x[step]/12.5)
    else:
        # Append a value to our y array
        y.append(x[step]**12.5)

# Print the first and last four values from both our x and y arrays

# First four
print("The 1st element of x is ",x[0])
print("The 1st element of y is ",y[0])

print("The 2nd element of x is ",x[1])
print("The 2nd element of y is ",y[1])

print("The 3rd element of x is ",x[2])
print("The 3rd element of y is ",y[2])

print("The 4th element of x is ",x[3])
print("The 4th element of y is ",y[3])

# Last four
print("The 47th element of x is ",x[46])
print("The 47th element of y is ",y[46])

print("The 48th element of x is ",x[47])
print("The 48th element of y is ",y[47])

print("The 49th element of x is ",x[48])
print("The 49th element of y is ",y[48])

print("The 50th element of x is ",x[49])
print("The 50th element of y is ",y[49])

```

    The 1st element of x is  1
    The 1st element of y is  0.08
    The 2nd element of x is  2
    The 2nd element of y is  0.16
    The 3rd element of x is  3
    The 3rd element of y is  0.24
    The 4th element of x is  4
    The 4th element of y is  0.32
    The 47th element of x is  47
    The 47th element of y is  7.965686757032835e+20
    The 48th element of x is  48
    The 48th element of y is  1.0363715136605023e+21
    The 49th element of x is  49
    The 49th element of y is  1.341068619663965e+21
    The 50th element of x is  50
    The 50th element of y is  1.7263349150062194e+21

### The AND statment

Once we move beyond two mutually exclusive conditions, we can also use the <code> ELIF </code> statements. However we need to be careful that we are assigning correct boundaries on our conditions. For example, let us assume we have been tasked with creating an array <code> X </code> that contains values from 1 to 200 and we want to implement 3 equations according to the following rules:

 - If X is less than 20, use: $ Y = \frac{X}{1.56} $
 - If X is greater than or equal to 20, but less than 60 use: $ Y = X^{0.35} $
 - If X is greater than or equal to 60 use: $ Y = 4.5*X $

Below we implement two different versions of a loop using the conditional statements introduced earlier:

```python
# Version 1
if x[step] < 20:
    <<action>>
elif x[step] >= 20:
    <<action>>
elif x[step] >= 60
    <<action>>
```
```python
# Version 2
if x[step] < 20:
    <<action>>
elif x[step] >= 20 and x[step] < 60:
    <<action>>
elif x[step] >= 60
    <<action>>
```

The first version will work, but produce incorrect results. Why is that? If you follow the code instructions, as the Python interpreter would, once <code> x[step] </code> is greater than 20 the second conditional statement will always be true. As a result, it will never have to move to the third. In the second version however, the second conditional will no longer be true once <code> x[step] </code> is greater than or equal to 60.

Let us run both versions and plot the results so you can see the difference. In the following code I will create two <code> Y </code> arrays, one for each loop variant. A line plot will be produced where you should see a step change in values according to these rules. Do not worry about the syntax or module used to create the plot, we will visit this throughout the course.

```python
# Initiliase an empty list for both 'x' and 'y'
x = []
y_version1 = []
y_version2 = []

for step in range(200):

    # Append a value to our x array
    x.append(step+1)

    # Version 1
    if x[step] < 20:
        # Append a value to our y array
        y_version1.append(x[step]/1.56)
    elif x[step] >= 20:
        # Append a value to our y array
        y_version1.append(x[step]**0.35)
    elif x[step] >= 60:
        y_version1.append(4.5*x[step])

    # Version 2
    if x[step] < 20:
        # Append a value to our y array
        y_version2.append(x[step]/1.56)
    elif x[step] >= 20 and x[step] < 60:
        # Append a value to our y array
        y_version2.append(x[step]**0.35)
    elif x[step] >= 60:
        y_version2.append(4.5*x[step])

# Plot results
import matplotlib.pyplot as plt # Import Matplotlib so we can plot results
import numpy as np # The Numpy package - more soon!!
fig = plt.figure(figsize=(8,8))
ax = plt.axes()
ax.plot(np.array(x),np.log(y_version1),label='Version 1')
ax.plot(np.array(x),np.log(y_version2),label='Version 2')
ax.set_title('Y as a function of X')
ax.legend(loc='upper left')
ax.set_ylabel('Y')
ax.set_xlabel('X')
plt.show()

```

![png](output_9_0.png)

<div class="alert alert-block alert-success">
<b> Exercise 2: Modify a loop to implement one of three equations according to a condition being met  <a name="Exercise2"> </b> In this case, let us assume an array X contains values from 1 to 1000 and we want to implement 3 equations according to the following rules:

 - If X is less than or equal to 250, $ Y = X^{1.03} $
 - If X is greater than 250, but less than 690 $ Y = X^{1.2} $
 - If X is greater than or equal to 690, $ Y = X^{2.5} $

This is the first graph we have created. Dont worry about the syntax for now, we will produce graphs in every practical following this.

Your output should look like the following:

![](https://github.com/loftytopping/DEES_programming_course/blob/master/images/Practical2_example.png?raw=true)

</div>

```python
# Initiliase an empty list for both 'x' and 'y'
x = []
y = []

for step in range(1000):

    # Append a value to our x array
    x.append(step+1)

    #------'INSERT CODE HERE'------
    # Now add a conditional statement to check the value of x
    # Notice our additional indentation
    if x[step] <= 250:
        # Append a value to our y array
        y.append(x[step]**1.03)
    elif x[step] > 250 and x[step] < 690:
        y.append(x[step]**1.2)
    elif x[step] >= 690:
        # Append a value to our y array
        y.append(x[step]**2.5)
    #------------------------------

# Print the first and last four values from both our x and y arrays

#Import plotting package
import matplotlib.pyplot as plt # Import Matplotlib so we can plot results
import numpy as np # The Numpy package - more soon!!
fig = plt.figure(figsize=(8,8))
ax = plt.axes()
ax.plot(np.array(x),np.log(y))
ax.set_title('Y as a function of X')
ax.set_ylabel('Y')
ax.set_xlabel('X')
plt.show()
```

    Text(0.5, 0, 'X')

![png](output_11_1.png)

## 3) Nested loops: Working with more than 1 dimension <a name="Part3">

In many applications we want to work with more than one variable at a time, often in a two [or more] dimensional setting. We can combine <code> FOR </code> loops on any number of levels. For example, take the following hypothetical example:

```python
for [first iterating variable] in [outer loop]: # Outer loop
    [do something]  # Optional
    for [second iterating variable] in [nested loop]:   # Nested loop
        [do something]
```

Notice how we have our first, or 'outer' loop cycling through our first iterating variable. As we cycle through this variable, we then 'do something' as a direct consequence. However, directly following this action, we cycle through a second iterating variable as part of our 'nested loop'. In other words, we have a loop that is nested within our first, or outer.

<div class="alert alert-block alert-danger">
<b>Indexing </b> Once again, notice how we have introduced a statement that ends with a colon : and thus requires the next line to be indented.
</div>

Let us run an example of cycling through a list of words. In this case we are not using the
```python
range()
```
function as we are not dealing with numeric examples or cycling through integers.

```python
# Create two lists of words
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:
    for word2 in list2:
        print(word1)
        print(word2)

```

    Hello
    George
    Hello
    Frank
    Hello
    Susan
    Hello
    Sarah
    Goodbye
    George
    Goodbye
    Frank
    Goodbye
    Susan
    Goodbye
    Sarah

Turns out we can make the output easier to read by adding each word together, with a space ' ' in between as:

```python
# Create two lists of words
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:
    for word2 in list2:
        print(word1+' '+word2)
```

    Hello George
    Hello Frank
    Hello Susan
    Hello Sarah
    Goodbye George
    Goodbye Frank
    Goodbye Susan
    Goodbye Sarah

We will not be exploring the rich text processing power of Python in this course, but if you are interested there are some great examples to follow on the [internet](https://towardsdatascience.com/gentle-start-to-natural-language-processing-using-python-6e46c07addf3). The important lesson here is noticing how we deal with a nested loop. Please also note that we can use a <code> FOR </code> loop to iterate on members of any list, whether they are numeric or string values.

Again we can use conditional statements to modify our output. What if we only wanted to output entries involving Susan? We can add a conditional statement as follows:

```python
# Create two lists of words
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:
    for word2 in list2:
        if word2 == "Susan":
            print(word1+' '+word2)
```

    Hello Susan
    Goodbye Susan

<div class="alert alert-block alert-success">
<b> Exercise 3: Print out the result from a nested loop according to a condition being met  <a name="Exercise3"> </b>

In this exercise we have three lists with the following entries:

```python
 list1 = ['Maths','Physics','Programming','Chemistry']
 list2 = ['is','can be','is not']
 list3 = ['enjoyable','awful!','ok, I guess','....']
```

Your task is to create a triple nested loop and only print out when the word in list1 is 'Physics' and the entry in list2 is 'can be'.
There are multiple ways to achieve this.

Your results should look like the following:

```python
Physics can be enjoyable
Physics can be awful!
Physics can be ok, I guess
Physics can be ....
```

</div>

```python
# Create three lists of words

#------'INSERT CODE HERE'------
list1 = ['Maths','Physics','Programming','Chemistry']
list2 = ['is','can be','is not']
list3 = ['enjoyable','awful!','ok, I guess','....']

for word1 in list1:
    for word2 in list2:
        for word3 in list3:
            if word1 == "Physics" and word2 == "can be":
                print(word1+' '+word2+' '+word3)
#------------------------------
```

    Physics can be enjoyable
    Physics can be awful!
    Physics can be ok, I guess
    Physics can be ....

<div class="alert alert-block alert-success">
<b> Exercise 4: Print out which variables match a condition  <a name="Exercise4"> </b>

In this exercise we have two variables, <code> x </code> and <code> y </code> taking on a value from two loops that cycle through 80 values.

```python
for x in range(80):
    for y in range(80):
        [do something]
```

Your task is to identify which combinations of <code> x </code> and <code> y </code> through the function:

\begin{eqnarray}
Z = Y+X^{2}
\end{eqnarray}

produce a value of <code> Z </code> = 80

</div>

```python
#------'INSERT CODE HERE'------
for x in range(80):
    for y in range(80):
        z = y + x**2.0
        if z == 80:
            print('x = ', x)
            print('y = ', y)
#------------------------------
```

    x =  1
    y =  79
    x =  2
    y =  76
    x =  3
    y =  71
    x =  4
    y =  64
    x =  5
    y =  55
    x =  6
    y =  44
    x =  7
    y =  31
    x =  8
    y =  16

<div class="alert alert-block alert-success">
<b> Exercise 5: Repeat Bob Newby's code breaking nested loops to crack the code in the Hawkins lab <a name="Exercise5"> </b>

In this exercise we imagine that we are tasked with finding the value of a password that is different everytime the program is executed. This will be generated by an internal Python function and used to create a string which has 5 numbers in it. We then have to create a 5 level nested loop to combine 5 different numbers into one word and when this matches the one generated by the internal Python function the attempted, thus correct, password is printed to the screen.

The code box below provides you with indentend lines in which to enter the rest of the code required. The first loop is provided. As part of the 5th loop you will need to combine all of thje individual numbers, as strings, into one word and then check if this is the same as the internally generated password. You can use the following commands for this, assuming that you call each letter as letter1, letter2 etc.

```python
password_attempt = letter1+letter2+letter3+letter4+letter5
if password_attempt == password_string:
    print("Passwords match!, attempted password = ",password_attempt)
```

Once you have finished, why not see how many steps have been taken to arrive at the correct password?

</div>

```python
# The following imports a module [see Practical 3] and then creates a string of a random number of 5 digits
from random import randint
n=5
password_string = ''.join(["{}".format(randint(0, 9)) for num in range(0, 5)])
print("password = ", password_string)

# Now create a 5 level nested loop which prints when the successful password has been met

#------'INSERT CODE HERE'------

# First loop
for step1 in range(10):
    letter1 = str(step1) # Convert number to a string
    # Second loop
    for step2 in range(10):
        letter2 = str(step2)
        # Third loop
        for step3 in range(10):
            letter3 = str(step3)
            # Fourth loop
            for step4 in range(10):
                letter4 = str(step4)
                # Fifth loop
                for step5 in range(10):
                    letter5 = str(step5)
                    password_attempt = letter1+letter2+letter3+letter4+letter5

                    if password_attempt == password_string:
                        print("Passwords match!, attempted password = ",password_attempt)

#------------------------------
```

    password =  35988
    Passwords match!, attempted password =  35988

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Continued working with **`for` loops** to repeat actions efficiently
> - Used loops to **cycle through arrays** one element at a time
> - Modified values inside a loop to see how data changes step by step
> - Introduced **conditional statements**:
>   - `if` to test a condition
>   - `else` and `elif` to choose between different outcomes
> - Combined **loops and conditionals** to apply different equations depending on a condition
> - Worked with **nested loops** to handle data with more than one dimension
> - Used conditions inside nested loops to:
>   - Control what gets printed
>   - Identify values that meet specific criteria
> - Practised reading instructions carefully and matching code output to expected results
>
> 🧠 *The focus was on learning how programs make decisions and repeat tasks automatically, which are core ideas in almost all real-world code.*

```python

```
