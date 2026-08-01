---
title: "Practical_1"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Practical/Week 1/Practical_1.ipynb"
type: notebook
---

# Welcome!

# Practical 1 - An introduction to data types, operations and loops

Welcome to the first practical in our Python programming course. Over the course of this module we are going to take an applied approach to learning Python. We do this by working through examples of basic numerical computation to data input and analysis. We cannot teach you everything Python has to offer in this course, but we can give you a set of tools to begin your journey.

In this practical we are going to cover some core operations most Python programs will have. This gives you chance to learn the syntax that the Python interpreter expects. Remember, learning to program is similar to learning any other language, including a general appreciation of what the hardware underneath the software is doing. This course will provide you with a number of templates to keep and maybe modify and re-use as you build up your own expanding library of examples.

<div class="alert alert-block alert-success">
<b>Objectives:</b> The objectives of todays practical are:

 - 1) [Understand how data types are represented and how to use common arithmetic operators](#Part1)
      * [Exercise 1: Set the value of two new variables and print to screen](#Exercise1)
      * [Exercise 2: Implement equations as combinations of arithmetic operators](#Exercise2)
 - 2) [Arrays and lists](#Part2)
      * [Exercise 3: Add two more entries to a list and change an existing entry](#Exercise3)
 - 3) [Loops and conditional statements](#Part3)
      * [Exercise 4: Cycling through arrays and modifying values](#Exercise4)

Please note that you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the 'solutions' folder.
</div>

<div class="alert alert-block alert-warning">
<b>Please note:</b> After reading the instructions and aims of any exercise, search the code snippets for a note that reads ------'INSERT CODE HERE'------ to identify where you need to write your code
</div>

## 1) Understand how data types are represented in Python <a name="Part1">

In the following section we will see how both numeric and string variables are handled and manipulated. For this, we will first look at the type of variables we work with and then how they are stored and processed.

### Numbers (integers, floats and complex numbers):

As per the official Python documentation, there are three distinct numeric types:

 - integers
 - floating point numbers
 - complex numbers.

We talk briefly about this during the lectures, and will revisit this in more detail as we move into our course. Integers have unlimited precision in that you could use an integer with a growing number of digits that would be limited by the memory on your machine. Floating point numbers are usually implemented using double precision. Complex numbers have a real and imaginary part, which are each a floating point number. Let us see what this means using our first bit of code. In the following 'code box' I'm going to use three variables <code> x,y and z </code> and assign them either an integer, floating point or complex value.

| Type | Format | Description |
| --- | --- | --- |
| int [Integer] |  a = 10 | Signed Integer |
| float [Floating point] | a = 45.67 | Floating point real values |
| complex | a = 3.14J | (J) Contains integer in the range 0 to 255. |

```python
# Whenever you see a hash symbol [#] in Python code, this represents a comment which is ignored by the interpreter.
# This is where a code developer will add some personal comments or add key notes that enable others to understand
# and/or use the code she/he developed.

# So let's assign some values to some variables. By the way, the variable names are not important, but are more
# of an issue regarding style and documentation.
# Also note that I'm not defining what each variable is expecting in the first place.
# In other words, I don not have to tell the interpreter what data type to expect in, say, x:

x = 2.3 # float
y = 4 # integer
z = 5 + 6j # complex [we are not going to use complex numbers in our course so this is the first and last instance]
```

If you click anywhere in the above code box, and then proceed to click <code> 'Run' </code> from the menu bar, you should notice nothing happens. Not very interesting, but we have assigned values to three variables. Now we can print our variables to screen using the 'print' function as per below. Once again, select the cell below and click <code> 'Run' </code> from the top menu:

```python
# Just adding comment here for the sake of it...
print("x =", x)
print("y =", y)
print("z =", z)
```

    x = 2.3
    y = 4
    z = (5+6j)

Looks correct! We can also ask Python to check the numeric type using the <code> type </code> function. Thus:

```python
print("The data type of x is",type(x))
print("The data type of y is",type(y))
print("The data type of z is",type(z))
```

    The data type of x is <class 'float'>
    The data type of y is <class 'int'>
    The data type of z is <class 'complex'>

Let's look at some more specifics for type _float_ from the official Python documentation. We have a number of formatting permutations we could use:

| Property | Syntax |
|------|------|
| It can have a sign | "+ -" |
| We can express infinity as |  "Infinity" "inf" |
| If we dont have a number, referred to as 'Not a Number' [NaN] | "nan" |

For example, look at the following examples where Im using the command <code> float </code> to print out the floating point number of a string in the brackets ().

```python
>>> float('+1.23')
1.23
>>> float('   -12345')
-12345.0
>>> float('1e-003')
0.001
>>> float('+1E6')
1000000.0
>>> float('-Infinity')
-inf
>>> float('NaN')
nan
```

We can use a positive or negative assignment. Notice also the use of lower case 'e' and upper case 'E', indicating the power of 10 (2.5e2 = $2.5 x 10^{2} = 250$).

<div class="alert alert-block alert-success">
<b> Exercise 1. Set the value of two new variables and print to screen <a name="Exercise1"> </b>

Set the value of two new variables <code> temperature </code> and <code> mass </code> equal to 298 Kelvin [as an integer] and 3.78 Kilograms [as a float]. Then print their data type to the screen.

</div>

```python
#------'INSERT CODE HERE'------
temperature = 298 # Kelvin
mass = 3.78 # Kg
#------------------------------

print("The data type of temperature is",type(temperature), "and has a value of ",temperature)
print("The data type of mass is",type(mass), "and has a value of ",mass)
```

    The data type of temperature is <class 'int'> and has a value of  298
    The data type of mass is <class 'float'> and has a value of  3.78

### Arithmetic Operators (add, subtract, multiply, divide and raise to a power)

In most applications, and in any language, we are going to use basic mathematical operations such as addition, multiplication and division. In the following table you can see a column of operations using Python syntax and the equivalent result.

| Operation | Result |
| --- | --- |
| x + y |  sum of x and y |
| x - y |  difference of x and y |
| x * y |  product of x and y |
| x / y |  quotient of x and y |
| abs(x) |  absolute value or magnitude of x |
| int(x) |  x converted to integer |
| float(x) |  x converted to floating point |
| pow(x, y) | x to the power y |
| x ** y | x to the power y |

In the following code we demonstrate how to perform basic arithmetic on either defined variables or pure numbers using appropriate Python syntax, and add comments using the # symbol.

```python
# Addition examples [+]
# 1) Define variables and add
x = 2.4
y = 7.5
z = x + y
print("z = ", z)

# Subtraction examples [-]
var1 = -3.4
var2 = 4.7
var3 = var1 + var2
print("var3 = ", var3)

# Multiplication examples [*]
starting_temperature  = 273.14 # Kelvin
d_temp_d_time = 3.4 # Kelvin per second
duration = 12.5 # seconds
end_temperature = starting_temperature + d_temp_d_time*duration
print("end_temperature = ", end_temperature)

# Division examples
Price = 12 # £ sterling
weight = 2.3 # kg
price_per_kg = Price / weight # £ per kg
print("price_per_kg = ", price_per_kg)

# Exponetation examples
base = 2.3
power = 4.5
result = base ** power
print("result = ", result)
```

    z =  9.9
    var3 =  1.3000000000000003
    end_temperature =  315.64
    price_per_kg =  5.217391304347826
    result =  42.43998894277659

In the division example, did you notice we actually asked Python to divide an integer by a float? This is ok in the sense that Python will, by default, change the type of the variable with the lowest precision to the same as the highest.

<div class="alert alert-block alert-success">
<b> Exercise 2. Implement equations as combinations of arithmetic operators  <a name="Exercise2">  </b> Implement the following equations as combinations of arithmetic operators given above:

| Description | Form  |
| --- | --- |
| Einstein's relativistic mass-energy relation |  $E = mc^2$ |
| De Broglie Wavelength | $\lambda  = \frac{h}{{m\upsilon }}$ |
| Ideal gas equation | $PV = nRT$ |
| Temperature from Degrees Kelvin to Celsius | $^\circ C = K - 273$ |

Where we provide values for the following constants referred to in each:

 - Planck's constant, h = $6.62607004 x 10^{-34}$
 - Speed of light in a vaccuum, c = $3 x 10^{8} m s^{-1}$
 - Ideal Gas constant, R = 8.205736×$10^{-5}$ $\frac{m3⋅atm}{K⋅mol}$

You should see the following output:

    The relativistic energy of an electron =  8.199e-14
    The De Broglie wavelength of an eletron =  1.3697557246543088e-10
    The Pressure of our ideal gas =  0.05260061405059999
    The Temperature in Celsius =  25.149999999999977

</div>

```python
# Constants used in equations
c = 3.0e8 # Speed of light, [m/s]
h = 6.62607004e-34 # Plank's constant [J s]
m = 9.11e-31 # Mass of Electron in kg
T = 298.15 # Assume temperature is 298.15 K
R = 8.205736e-5 # Ideal Gas Constant [m3⋅atm/ K⋅mol]
V = 1.0 # Assumed volume in ideal gas law
n = 2.15 # Number of moles of gas used in the ideal gas law
vel = 5.31e6 # Assumed velocity of eletron in De Broglies rule [m/sec]

#------'INSERT CODE HERE'------
# Einsteins relativistic mass-energy relation
E = m*c**2.0   # Energy of electron [J]

# De Broglie's Wavelength
Lambda = h/(m*vel)  # Wavelength [m]

# Ideal gas equation
P = (n*R*T)/(V)   # Pressure [atm]

# Covert above equation to degrees Celsius
T_celsius = T-273.0

#------------------------------

print("The relativistic energy of an electron = ", E)
print("The De Broglie wavelength of an eletron = ", Lambda)
print("The Pressure of our ideal gas = ",P)
print("The Temperature in Celsius = ",T_celsius)
```

    The relativistic energy of an electron =  8.199e-14
    The De Broglie wavelength of an eletron =  1.3697557246543088e-10
    The Pressure of our ideal gas =  0.05260061405059999
    The Temperature in Celsius =  25.149999999999977

## 2) Arrays: Lists, tuples and dictionaries  <a name="Part2">

In most programming applications we want to store and update values in an array, be it 1D, 2D, 3D or even more. Python comes with 3 ways to store this information known as:

 - lists
 - tuples
 - dictionaries.

For applications focused on numerical computations, the module known as Numpy is used for manipulating and creating/modifying numerical values in arrays. We meet this module in Practical 3. The reason is that Numpy has been optimised for use in this way and can be significantly faster than 'non-Numpy' approaches we will use in this class. We will be using the Numpy package throughout this course, but we will also come across a 'list'.

So, why are there multiple methods?

Lists and tuples are perhaps the most common used data structures in Python. They have a number of similarities:

 - They both store a collection of items sequentially
 - They can store items of any data type. So this include numeric and non-numeric.
 - Any item is accessible via its index. We will see this below

<div class="alert alert-block alert-danger">
<b>Indexing </b> Please note, Python indexes start at 0
</div>

However they have a key difference which is:

>> Lists are mutable while tuples are immutable. This means we can change/modify the values of a list but we cannot change/modify the values of a tuple.

They also have a different syntax. Let's run through some examples below. Notice again Im using whatever variable name I want. To re-run the code in a box, such as that provided below, click anywhere in the box and then click on the 'Run' symbol in the notebook toolbar. For example, once you have read through the below, try accessing a different element from the list.

```python
# First let's create an identical list and tuple containing names of places
# Lists use square brackets, whereas tuples use parentheses

list_capitals = ['London','Paris','Rome','Ankara']
tuple_capitals = ('London','Paris','Rome','Ankara')

# If we want to access a particular element from a list of a tuple, we use the same bracket notation but also
# remember that python indexing starts at 0. Thus, for the first element in the list we would write:

list_capitals[0]

# Now click run on this portion of code and you should see the word 'London' below, if accessing element [0].
```

    'London'

```python
# Now lets access the 4th element of both the list and tuple. Note im using the print command here so we can see
# both printed to the screen:

print("4th entry in the list is ",list_capitals[3])
print("4th entry in the tuple is ",tuple_capitals[3])
```

    4th entry in the list is  Ankara
    4th entry in the tuple is  Ankara

The key different between lists and tuples are the ability to change values. This impacts on efficiency, which we wont cover in detail during this course; Lets try to change and then print the 2nd entry in both the list and tuple. Let's try to change this to <code> Beijing </code>. See the code below. When you click <code> Run </code>, does it produce an error?

```python
# Change the 2nd entry to 'Beijing'

list_capitals[1] = 'Beijing' # note the index value and the [] bracket notation
# print full array to the screen
print("full list array = ",list_capitals)

tuple_capitals[1] = 'Beijing' # note the index value and the [] bracket notation
# print full array to the screen
print("full list array = ",tuple_capitals)
```

    full list array =  ['London', 'Beijing', 'Rome', 'Ankara']

    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[9], line 7
          4 # print full array to the screen
          5 print("full list array = ",list_capitals)
    ----> 7 tuple_capitals[1] = 'Beijing' # note the index value and the [] bracket notation
          8 # print full array to the screen
          9 print("full list array = ",tuple_capitals)

    TypeError: 'tuple' object does not support item assignment

You will see an error as we cannot change the entry in the tuple. Following on from this, we can change the size of a list, but we cannot change the size of a tuple. Imagine we want to add a 5th entry to our list. To do this we can append to the list by using the

```python
>>[Name of list].append()
```

operation. Thus, look at the following code:

```python
# Append another city to our list as follows, and then print the new array
list_capitals.append('Moscow')
# print full array to the screen
print("full list array = ",list_capitals)
```

    full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Moscow']

<div class="alert alert-block alert-success">
<b> Exercise 3. Add two more entries to a list and change an existing entry  <a name="Exercise3"> </b>

Append to your existing list the following cities, in sequential order:
 - Manchester
 - Edinburgh

    Then change the existing value of the 5th element, which is currently <code> Moscow </code>, to <code> Hanoi </code>. When youy have finished this, and run the code, you should see an output resembling:

```python
full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Hanoi', 'Manchester', 'Edinburgh']
```
</div>

```python
#------'INSERT CODE HERE'------
list_capitals.append('Manchester')
list_capitals.append('Edinburgh')
list_capitals[4] = 'Hanoi' # note the index value and the [] bracket notation
#------------------------------

# print full array to screen
print("full list array = ",list_capitals)
```

    full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Hanoi', 'Manchester', 'Edinburgh']

## 3) Loops and conditional statements  <a name="Part3">

Once we have information stored in an array, or wish to generate information iteratively, we start to use a combination of **loops** and **conditional statements**. Let us focus on loops during this practical.

### Loops
Take the previous list, or array, of city names. We could, as we have done, print each entry individually like so:

```python
print("first entry is",list_capitals[0])
print("second entry is",list_capitals[1])
print("third entry is",list_capitals[2])

#...and so on

```

    first entry is London
    second entry is Beijing
    third entry is Rome

However we often work with very large arrays and this simply wouldnt be feasible or just too time consuming. We might want to generate values to be stored in a very large array, based on a specific algorithm, which would be better automated. Loops allow us to do this. Take our previously constructed list. The following code demonstrates using a loop to print each value in turn. Take note of the way the loop is contructed, the syntax and the need for introducing a space within the loop. We will discuss this shortly. In fact, obeying the white space rule is a fundamental requirement in Python

<div class="alert alert-block alert-danger">
<b>White space rule </b> Whenever a series of commands, or command, is terminated by a colon :, the following line should be indented. Examples typically include loops and function definitions.
</div>

```python
# Example loop to print entries in our list of capital cities
for step in range(7): # I have introduced a variable called 'step'. It dosnt matter what name we use
    # but see how the same variable, once defined by the loop, is used to access entries in our array
    print(list_capitals[step])

```

    London
    Beijing
    Rome
    Ankara
    Hanoi
    Manchester
    Edinburgh

Let us break this down a little. The loop counts through a fixed number of integer values using the <code> range </code> function. We will start looking at functions in our third practical. Briefly, this Python function creates a sequence of numbers that define each iteration of the loop. By default, this sequence is based on integer values but you can modify this by passing optional arguments which we will not cover in this practical. For now, this generates values from 0 to 6. Recall, Python indexing starts at 0. In fact, lets add another line within our loop such that we can access the value of our 'step' variable within each loop iteration as follows:

```python
# The following loop counts through a fixed number of integer values using the range function. We have defined the
# limit of values to be iterated through by knowledge of how big our array is. If you ask Python to print
# any entries beyond the boundaries of our array, you would get an error message. Try it!

for step in range(7): # I have introduced a variable called 'step'. It dosnt matter what name we use
    # but see how the same variable, once defined by the loop, is used to access entries in our array
    print(list_capitals[step])
    print("the value of step is ", step)
```

    London
    the value of step is  0
    Beijing
    the value of step is  1
    Rome
    the value of step is  2
    Ankara
    the value of step is  3
    Hanoi
    the value of step is  4
    Manchester
    the value of step is  5
    Edinburgh
    the value of step is  6

We have only looked at a list containing strings, or words. Let's try a numerical example. Assume we want to create two new lists, <code> x </code> and <code> y </code>. Both have 100 elements. The <code> x </code> array contains integer values from 1 to 100, and the <code> y </code> array is defined by the basic equation <code> y=x*3.4 </code>. Check out the code below. This uses a combination of creating a new list, defining a loop and applying a numerical operation:

```python
# Create two empty lists. We are going to fill these in the loop
x = []
y = []

# Create a loop that cycles through 100 values, then implement the equation defined above
for step in range(100):

    # First lets define a value in our x array. We know x goes from 1-100 so, knowing Python
    # indexing starts at 0, do you understand the following operation
    x.append(step+1)
    # So for our first iteration, step is 0 and thus we place the value '1' into x

    # We might aswell also define our y values.
    # Take your time to understand whats going on below.
    y.append(x[step]*3.4)
    # We can break it down into 3 phases
    # 1) We want to append a value to our y array using .append()
    # 2) We want to take the associated value from the x array using our index given by the 'step' variable
    # 3) We want to implement the function given by equation xx.

# Below the indented space above, the loop has finished. Lets print the first 4 values from both
# our x and y values

print("The 1st element of x is ",x[0])
print("The 1st element of y is ",y[0])

print("The 2nd element of x is ",x[1])
print("The 2nd element of y is ",y[1])

print("The 3rd element of x is ",x[2])
print("The 3rd element of y is ",y[2])

print("The 4th element of x is ",x[3])
print("The 4th element of y is ",y[3])

# What about the 81st element of x and y?
print("The 81st element of x is ",x[80])
print("The 81st element of y is ",y[80])

```

    The 1st element of x is  1
    The 1st element of y is  3.4
    The 2nd element of x is  2
    The 2nd element of y is  6.8
    The 3rd element of x is  3
    The 3rd element of y is  10.2
    The 4th element of x is  4
    The 4th element of y is  13.6
    The 81st element of x is  81
    The 81st element of y is  275.4

<div class="alert alert-block alert-success">
<b> Exercise 4. Cycling through arrays and modifying values <a name="Exercise4">  </b>  Create a loop that implements the function:

\begin{eqnarray}
Y = X^{2.8}
\end{eqnarray}

Where <code> x </code> is an array of 50 values from 1 to 50.
</div>

```python
# Initiliase an empty list for both 'x' and 'y'
x = []
y = []

# Now loop through 50 values and append each list accordingly.
# One list contained values for 'x', the other 'y'.
# Please note the operator ** is needed to raise one number to another [e.g 2**3]
#------'INSERT CODE HERE'------
for step in range(50):

    # Append a value to our x array
    x.append(step+1)

    # Append a value to our y array
    y.append(x[step]**2.8)

#------'INSERT CODE HERE'------

# Print the last four values from both our x and y arrays
print("The 47th element of x is ",x[46])
print("The 47th element of y is ",y[46])

print("The 48th element of x is ",x[47])
print("The 48th element of y is ",y[47])

print("The 49th element of x is ",x[48])
print("The 49th element of y is ",y[48])

print("The 50th element of x is ",x[49])
print("The 50th element of y is ",y[49])

```

    The 47th element of x is  47
    The 47th element of y is  48069.98672788238
    The 48th element of x is  48
    The 48th element of y is  50988.87907329358
    The 49th element of x is  49
    The 49th element of y is  54019.30894617742
    The 50th element of x is  50
    The 50th element of y is  57163.13149091575

## ⚙️ What We Did

> 🟦 **In this practical, we:**
>
> - Explored the idea that **all values in Python have a data type**
> - Looked at common basic types, including:
>   - Numbers (integers and decimals)
>   - Text (strings)
> - Used **comments (`#`)** to explain code and leave notes
> - Created **variables** to store values for later use
> - Practised assigning values to variables with clear, meaningful names
> - Used the `print()` function to **display output** and check our code
> - Ran and modified code cells to **observe how Python responds**
>
> 🧠 *The focus was on understanding how Python stores data and how we interact with it in simple programs.*

```python

```
