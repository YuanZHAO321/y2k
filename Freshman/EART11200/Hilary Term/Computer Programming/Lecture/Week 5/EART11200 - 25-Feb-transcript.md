---
title: "EART11200 - 25-Feb-transcript"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 5/EART11200 - 25-Feb-transcript.txt"
type: transcript
---

'EART11200 - 25-Feb', automated transcript
01/08/2026
---

All right, good afternoon, everyone.

Hope you're all OK.

So we're nearly halfway through the content today.

So only five more sessions with new content

before you work on the assessment.

But what we're going to do today is look

at solving differential equations.

So it relates entirely to what you're

learning with maths at the moment,

but taking a programmatic approach.

So rather than, there are many situations

where you can't solve a differential equation

analytically.

So I'll go over some of the terms

that you'll be able to cross reference

with the maths and physics module.

We'll look at some examples and then take a look at the notebook.

So we're here.

We're on week five.

So it is focused around modules and functions today, again.

But what we'll do is we'll load some functions in

that can solve differential equations

that we have to define.

So you'll basically convert or translate

differential equations, popular ones, into Python code.

And then we'll pass that into a function.

And then our function will be solved as a function of time.

So we'll see some common examples today.

That then really wraps up everything

we need to know at this stage in terms of modules and functions.

We won't stop using those.

We'll always import modules that have functions in them.

But we'll take a data-driven approach from next week

onwards, where we'll look at geospatial data.

And there's a reason that there are two practicals there,

because it is quite a large area by itself.

But it's a particularly relevant area

to all of your pathways, whichever you may pick.

So if you do want to look at data in your third year

project, for example, these are the tools that you could use.

And you could even replicate the notebooks as well.

It's up to you.

Then we'll look at some statistics

and do a little bit of machine learning at the end.

OK.

As a recap, I think hopefully you're

getting familiar now with the syntax, so the style

that we have in Python and the fact

that we have syntax highlighting within the notebooks.

We've used functions others have written for us,

but we've also written our own.

And we use the def keyword there when

we do want to write our own function.

We'll do the same in the notebook associated

with this practical.

But our function will return differential equation values,

i.e., gradients.

And then another function will take those and then

integrate them over time.

We'll still use an array of modules

because we'll have to plot the results,

maybe do some manipulation of the data.

So it'll feel exactly what you've done up to this point,

but we have a very targeted problem today.

And we'll have to work with arrays.

And again, we're going to always work with numpy arrays

from this point onwards.

The function that we'll use to solve

the differential equations expects us

to provide numpy arrays.

So as I said prior to last week, it's

really important to start working in this way

because a lot of functions do expect us to.

So that allows us to interact with the whole range

of tools available.

Well, I mean, differential equations

are everywhere, unfortunately.

If you're trying to simulate, so develop

a numerical model of any process within the system,

typically at some point, that process

will change in space and time.

And what you'll be learning with Matt

is we can often represent processes

in differential equation forms.

And bare bones of those equations

give us rates of change.

And you'll be familiar with the terminology,

with the style of writing on that second component here.

But basically, what we always need to do,

let's say we go back to the example of a climate model,

we need to translate that theory into something

that a computer can solve.

And then we try and represent a digital version

of our planet based on what we understand,

what we think is happening within the planet.

So you'll typically see we try to come up

with a closest possible representation

of what we're trying to understand.

And of course, what that means is

if you have a differential equation that, for example,

looks at population change, we're

going to have to represent that in a computational language.

And then the solver will integrate that

to work out what might happen in 100, 200 years time.

It's not as simple as having single differential equations

which we'll solve today.

I think you've seen the radioactive decay equation.

So we'll solve that equation,

but use Python to solve that equation.

We won't have to integrate it ourselves.

Typically, you don't have to do that

because the equations we're interested in

are much more complex than allow us

to use rules of calculus to go from one to the other.

Of course, underneath the hood,

those rules are embedded somewhere.

There is a reality check.

But typically, if we're thinking about

that example of population growth,

it won't just be dp by dt, p is the population.

That p will also depend on, for example,

geopolitical factors in a model,

economic status, land use change and other things.

So quickly we get into a situation

where we have coupled differential equations.

And this is where we have to start using methods,

computational methods.

Because if we change one thing, we'll change the other.

And that also relates to rates of change.

So you'll see a lot of that in the notebook today.

What you'll basically see is we write a Python version

of these types of equations.

And in fact, we will look at those equations specifically.

So these are three coupled differential equations

and they represent a chaotic process.

What that means is you can start

from a very specific initial condition,

nudge it a little bit,

you get wildly different results at the end.

They're called the Lorentz equations.

They've been used in climate forecasting as well.

I don't know if you've ever heard the term

that a butterfly will flap its wings in the Pacific

and cause a tornado in the Atlantic.

No, it's basically related to chaotic systems.

We know that the weather is a chaotic system.

But we can solve it though.

We'd be very difficult for us to do that by hand.

So once we write these equations in Python,

wrap it in a function,

and then ask a solver to solve those,

we can set values for these parameters

and starting values for X, Y, and Z

and then plot it on a graph.

So then we can get into sensitivities.

And that's really important

because if this represents a weather system, for example,

and this parameter here, sigma,

represented a process that might change due to climate,

then we can see the impacts on weather.

So this is why numerical simulations really underpin

everything we want to know about our impacts

on the environment moving forward

because there are time and spatial dependencies.

It's quite a specialized area of research though in itself.

I still maintain that from the course material

you'll come across, the data-driven work

will be most widely applicable whatever you decide to do.

But if you do get into research

that looks at numerical simulations,

you're solving differential equations at some point.

But as I said, there are mature tools

so we don't have to do that ourselves,

but knowing how to do that is key.

So this course is very much applied.

So we'll use modules and we'll trust that they work.

You'll find that sometimes they don't work,

but you don't need to understand

how all these equations have been solved, which is great.

So it takes the burden off you as a scientist.

And I think what we're seeing now

with large language models

that are enabling much more rapid workflows,

that will get more and more abstract

in the sense that I'm pretty sure in the future

you'll be able to write these equations in latex or whatever

and you'll say, well, please solve these equations

with these conditions.

And behind the scenes, code will be written and generated

such that they are solved

in the manner we want them to be solved.

So, but it will always require scientists and engineers

to understand that process.

So there's a safety check there.

It's just the nature of how we do science will change.

Absolutely.

So I'm not gonna put too much calculus on the board.

You have more than enough of that with Matt,

but I presume you're familiar at least

with the right-hand side in terms of the form

of equations you'll see.

This style of equations here,

and they're called couple differential equations

because we have, let's say,

this represents a chemical system.

I don't know, ozone in the atmosphere,

a common example I work on a lot.

There are many things emitted by trees and cars

that dictate the lifetime of ozone.

They react with each other.

So you'll often find that we use equations

that look like this.

So as A, the rate of A changes, it depends on X.

So we have to account for the rate of change of X as well.

So that's why they're coupled.

We couldn't, in the example of the radioactive decay equation,

and you won't, have you started integration yet?

No, you got that coming.

So, but you understand that differential equation,

you solve to get an integral,

and you can get the derivative of an integral

to get a differential equation.

So there's a circular thing taking place.

On the left-hand side here,

these provide us with rates of change,

and most of our physical theories begin in that form.

Newton's laws of mass, of motion, heating,

many things that describe how things change

in space and time start as a differential equation.

What you've been looking at in your course so far

is you have a function,

and you want to calculate the gradient of that function,

and there are rules to do that.

You can do that with Python as well.

We won't do that, but the dominant use

is when you start with a differential equation,

let's say one that describes the rate of change

of A, X, Y, and B,

but you want to predict the actual values of those

in 10 minutes time.

That's where you integrate.

So this no longer becomes rate of change

with respect to time.

You're solving it to predict the actual value.

So you're reversing differentiation.

So the rules you use to differentiate,

you reverse effectively.

So that's what integration is.

For examples like the radioactive decay equation,

Matt will go through this with you.

We can go from the differential equation

to an expression that tells us what the value of N is,

but in coupled systems, we can't,

because as I said before,

if we change the value of X and A,

it impacts on both rates of change.

We can't integrate one and then integrate another.

So what happens is there are strategies

that are written into Python programs

that will nudge the values of each,

make sure things like mass constraints

are abided by, you don't get negative values,

and it'll keep doing that until it meets the requirements

set by these rules here.

So it's an iterative approach.

So when you've heard about numerical solutions

versus analytical,

so an analytical approach is going from here to here,

so we can actually get an expression,

which is by far the quickest if you were to run that.

A numerical approach is iterative.

We keep changing the numbers in the system

and make sure it abides by those rules.

To give you an example,

and again, so I'm trying to contextualize this,

so when you do run the Python examples,

you can start to see how it relates

to what you're learning with math.

So I'm sure you've seen this type of example

where you have, let's say, S as a function of T,

yeah, and so that's the actual value

of S as a function of time,

and the derivative at this point here

gives you the gradient at that point, yeah?

So it's almost like a trajectory.

So if we were given a value of the differential here,

we might naively assume that this solution

will stay on this trajectory and go here.

So if we do that, we'll be wrong.

Yeah, so what integration allows you to account

for the rate of change over time,

so we actually follow that curve.

So what people then do in terms of solving this numerically

is when you have a differential equation,

and you want to solve with Python,

as we'll do in the notebook,

what it's doing is you might specify

the differential equation,

you might specify a starting point and an end point,

and say, give me the values every 10 seconds,

and then just let it solve.

But what it's doing, it's working out the gradient.

Let's say this is the beginning value here.

Let me just put the pointer.

Yeah, you can see that now.

It's working out the initial value here,

and it's using something called a time step.

So it's calculating the gradient

and then taking the solution along the gradient

by a given time step.

So in this case here,

the time step is given by, let's say, one second.

So it calculates the derivative at every second

and then forms this trajectory.

But our error is getting worse and worse and worse.

So you'll see here,

the actual solution is given by the dash line.

A numerical solution could be given by the solid blue line.

Because the time steps are really quite far apart,

the trajectories are getting worse and worse and worse.

So behind the scenes, the solver is working out

what the time step needs to be

to get the accuracy within a tolerance you define.

So this means the functions we call

will have a range of options.

They'll want us to define the differential equations

we want to solve,

starting conditions, frequency of outputs,

but also accuracy and tolerance.

So you'll see in some of the examples today,

I have to define a tolerance.

You don't have to.

We've given you some default values.

But if you start thinking about,

well, what do these represent?

That's it.

Because numerical solutions are not perfect.

They're never perfect.

You would struggle to get 100% accurate solutions,

but there are errors that we're happy with.

Another example could be,

because of that coupled system,

imagine that we have a differential equation

that we'll write today that represent X, Y, and Z.

And I know, so let's say that this is a concentration

and this is time,

but I know the real solution looks something like this.

So they're reacting with each other.

I know if this is X and Y,

this can't be less than zero

because it represents a chemical component.

It can go close to zero or zero,

but it can't go underneath.

So the numerical solver starts nudging

and working out the gradients

to actually predict these values.

There's a chance that if our time step is too big,

this trajectory might take a solution negative.

So you also might see options to say,

please don't let this happen.

Don't let things go to zero.

So there are many options numerical solvers have,

and they're all built around different strategies.

So imagine that we're solving a scenario

of subsurface evolution, I'm not a geologist,

but obviously that takes place over a long time period.

On the other hand, if we're solving something

that has really short time scales

like atmospheric chemistry, pollution,

some of those components can last seconds or less.

So the strategies are very different

according to the problem you're solving.

So you'll find that each domain has its own preferred solver.

So they're built for certain types of numerical systems.

This is why we need all of this in functions.

If we try and write these solvers

over and over again ourselves,

it becomes completely unsustainable.

But what you'll find is the community of developed tools

that are good for certain demonstrations,

and this gets better over time.

So this links back to all that modules,

all that thing I said about modules and functions, right?

If you've got mature packages you can bring in

to solve your problem,

it's likely that they're really stable

and they'd be tested for things that you're interested in.

If it's a new language,

you'll find that the number examples are quite low

because people are still developing them.

That's why Python's a good place to start.

When it comes to numerical simulation,

there are actually better languages

because Python was never developed to be

solely focused on numerical computation.

It was developed to be an all-rounder.

So I've talked a lot about speed of Python.

When it comes to solving things like a climate model,

speed's really important

because if you're solving something

100 years on a 100 year time scale,

and this thing requires huge amounts of energy,

so you have big high performance computers,

you want to look at the impacts pretty quickly.

We can't leave something running for a year.

Governments change, don't they, as we see, quite quickly.

So people will be furiously now looking at potential scenarios

as emissions might change by certain global players.

And you need to try and do that as quickly as possible

to actually push back against global pressures

against those things.

There is quite a strong link between what we can do

with our digital tools to how the world works,

certainly at the climate scale.

But all of this is more or less to show you

that there are many options out there

that typically maps to the certain problem

that you're solving.

We don't have to understand how they're solving them,

but at least we can start playing with

some of the parameters, such as accuracy,

setting constraints on values.

We'll give you all of those in the notebook.

And one of the examples you'll see today

is the Predator-Prey equations.

So these are two couple differential equations.

They're used as a toy model, if you like,

for describing one species interacting with another.

Again, we couldn't solve this by hand.

Even though they're only two couple differential equations,

it becomes quite tricky.

So we're going to let a numerical solver

that accounts for all these issues deal with that.

Predator-Prey equations are named

because it represents a hypothetical scenario

where you might have foxes eating rabbits, for example.

And in one example here,

let's say you've got the population of rabbits

on the red line, and you've got a birth and death rate.

So you have a positive and negative.

So if these represent the amount of foxes and rabbits,

let's say, you should start,

we can now recognize that if you have a negative differential,

it leads to a decrease in something.

If you have a positive, it leads to an increase.

So the numbers associated

with the positive and negative components

represent natural birth and death,

but also the impact of that other species on another.

In the rabbit's case, obviously, foxes start eating them.

But if the number of rabbits go down,

foxes get more hungry and start to die off.

So there's interdependencies between the two.

That's why you get this behavior in this system.

So you get one rising, the other rising,

and then down, so on and so forth.

Of course, reality is much more complex than that,

but it's an application of how we can set,

we can define these in Python, which we will,

in the notebook, we can change these values,

and then start looking at how the system changes

very quickly, so we don't have to spend hours

deriving integrals by hand.

You might wanna check them, and that's absolutely fine,

but we can get to this level of visualization,

which is quite powerful.

This is obviously a toy example,

but imagine a scenario, again,

where you're looking at an environmental system

which links to a particular policy change.

That's the kind of visualization you want to get to,

because you can start understanding that.

You can tell a story with it.

And this is why that whole Python ecosystem is brilliant.

I'm not gonna dwell on the type

of differential equations at all.

You'll see non-coupled and coupled in the notebook.

The non-coupled one does relate to the example

you've worked through with Matt,

and you will integrate by hand,

but you'll see the solution through Python.

You'll see the Lorentz equations.

You'll see the Predator-Tray equations,

but I did mention before that there are certain solvers

that work quite well, or badly,

according to the problem you're solving.

This is a really quite a,

there's a lot of information on this diagram,

but just to kind of reflect on this,

because we're using SciPy, if you remember,

the Python module for solving our differential equations.

These are different programming language options

for solving differential equations.

So imagine if I'm working in C, or Julia.

If you basically squint and see a green box,

it means it's fantastic at a certain problem.

So we're introducing you to Python,

because it has a very accessible set of functions,

but when it comes to numerical simulation,

it's not that good.

Now for your examples, it's fine,

because they'll run really quickly.

You'll get outputs.

You can interface with other systems through Python.

But just to give you an example here,

boundary value problems.

So what that means is,

you'll look at boundary value problems

throughout the first year courses.

What that means is, we're setting maybe a start

or an end value that we're interested in.

So when you integrate the radioactive decay equation,

you might have a starting number of unstable nuclei,

a time period you then want to work out a final value.

They're boundaries.

Yeah, so a boundary value problem

is very, very common, differential equations.

Starting state of the climate, you have a time period

you want to predict 100 years.

That's a boundary value problem.

Some are different from that.

There are many different types of differential equation.

But if you see here,

SciPy is noted as being fair,

because there aren't that many solvers.

So the range of problems we can look at,

fine for the notebook,

but once we start getting into complex scientific problems,

it's not that good.

Julia, on the other hand,

I think I've mentioned Julia at the beginning of the course,

which is emerging as a real juggernaut

when it comes to numerical simulations,

is excellent across the board.

But Julia has been developed

to target this particular area and AI.

So I think Python has around 10 or 20 different solvers.

I think Julia has around 300 now.

So the community is developing these solvers really rapidly

and it's gonna replace a lot of,

I think a lot of the climate models.

But it's just to illustrate,

depending on what numerical tool you want to jump into,

there are better options available.

You can call all the languages from Python.

So again, it's a great glue language.

It can bring things together

and bring in the benefits of the different languages.

But out of the box,

it's not great for numerical simulations.

Nonetheless, we'll use a module.

We'll use SciPy.

I always call them two different names,

any given sentence.

And we're gonna use a function called ODEINT,

ODE Integrator.

So if you were going online

and you looked through the documentation of SciPy,

you would come across this type of level of information.

You could click on each module

and it will give you examples.

It will show you how to run it.

So the documentation is great.

In fact, you can take examples if you wanted

from that into your notebook and run them.

But you'll notice every function we use

has some function arguments.

And this is why we're still looking

at functions and modules now.

So within the SciPy module,

there'll be many, many, many functions.

Some of these are listed here.

We will import one and use that to integrate.

So IE, turn the differential equation

into a form of absolute values in a future point in time

or in space, which you'll see on the Lorentz equations.

So documentation is always worthwhile

checking out whatever you're using

because it will give you more of an idea

as to whether or not you can improve what you're doing.

So this example where I talked about

non-negative constraints, some solvers can't do that.

So if you were looking at certain examples,

they wouldn't let you do that.

So if you weren't worried about non-negative constraints,

that's fine.

Many real world systems we are.

Same with the tolerance.

So setting the accuracy of the simulation.

We're gonna specify that in the notebook.

They are a little bit random,

but if you're pressed for time,

or let's say you're measuring something

in the real world system and that has a level of accuracy.

You don't want your numerical solver

to be worse than that, right?

Because you don't know if you can measure the truth

based on the accuracy of your simulation

and the accuracy of your instrument.

So you need to start matching the two.

The more accurate a solver becomes,

the longer it takes to run

because what it's doing behind the scenes

is it's making this time step smaller and smaller

to reduce the error projection from each gradient, okay?

There's a whole group in maths

that do research around differential equation solvers.

We're not here to do that.

You'll be glad to know.

Some examples.

So we're gonna define our own function

and there's a typical workflow

that is common throughout all of these examples.

Some of it's similar to what you've seen so far.

So we're gonna import modules always,

but the first thing we need to do

is define a function to solve

and we call this the right-hand side.

So if you hear the right-hand side,

what that means is if we have any differential equation,

dx by dt or dN by dx, whatever,

equals, equals, it's this bit.

It's literally the right-hand side of the equation.

So if you come up, if you find some documentation

or notes surrounding solving differential equations,

rhs is right-hand side.

That's the left-hand side, okay?

But it's common terminology.

So this function here,

I've defined using the def keyword.

I'm calling it dy by dt, not very imaginative,

and I'm gonna pass it some input and return these values.

So that's the function we need to define.

Obviously, we want to solve for values of these

in given point in space and time,

but our solver wants us to define them.

It will only solve what we've defined, which makes sense.

So we'll convert those differential equations into Python.

We'll use arrays, we'll use indexing.

So you see again, we're gonna be based

on that fundamental knowledge you've now got

of how Python works to define this right-hand side.

And it'll return this dy by dt array.

Again, I've defined that.

It doesn't have to be that name,

but it has to return something.

Because what the integrator's going to do

is once we've set some starting values behind the scenes,

it's gonna keep changing the values of x and y

and see how good the solution is

and keep nudging that toward the final solution,

and then give us the output.

It's a boundary value problem.

So we're going to define an array that represents time.

So we need to give the solver an array

of periods we want the output.

Typically, they're evenly spaced, yeah?

We define that using a numpy function.

Linspace is just a function

that defines linearly separated values.

You could use range, it's fine.

But linspace allows us to have a start and an endpoint

with that many entries.

So it'll work out the gap between t.

So once we've defined a function to integrate,

the time period to get the answers,

now I can call this ODEINT function.

So ODEINT has a certain strategy

to solve certain types of equations.

It won't work for some,

or it will not give you an answer.

It will struggle to get an answer.

It works for our examples.

Pass it the name of the function

so it knows to call the right-hand side function.

Now array is gonna be an array of starting values.

It's a boundary value problem,

so we're going to give it starting values,

period to get the answers out of.

And here you have this rtol and atol.

Not to be worried about,

but again, these are tolerance values.

So how accurate do I want the solution to be?

Relative tolerance and accuracy tolerance.

What that means is it will keep solving it

until it gets to that level of accuracy.

So the bigger you make this value,

the quicker the solution,

but it might be too erroneous.

It might not be good enough.

We set all of those,

but you can change them

and you can see whether or not

you start getting negative values,

whether the solution's good enough.

If you're an experimental scientist

working with someone working in the field or the lab,

typically you would spend a lot of time

talking about what accuracy is good enough.

And this is why normally as a scientist,

you're either a numerical modeler

or you're someone who's working in the lab.

You rarely get someone who does the two

because there are big areas of work,

but that's where the interface lies.

Okay, what can we actually measure

and how is it important?

But this workflow is what you'll see over and over again.

Actually very common in any other language.

We will always need to define the right-hand side function

and then call a solver.

The solution is going to output

the values for X and Y in a two-dimensional array.

We've said our time period is this,

so it will literally have values for X, Y

over that time period as a numpy array.

So that's when we can produce these plots.

We could change when we want the values to be output.

It's entirely fine, you can do that.

So I referenced that you'll be looking at

the radioactive decay equation

that you've looked at with Matt.

So see here, in the differential function I want to solve,

I've given it a different name.

I've defined the time period

over which I want the solution to be given to me.

I pass values for N and T

because I know that that differential equation,

dN by dt is equal to minus gamma N, yeah?

So I'm writing the right-hand side

in a very simple way.

I'm just returning minus one gamma times N.

That's the right-hand side, yeah?

Differential equation.

And then over a for loop,

I'm modifying this value over and over again.

And I'm getting results so I can plot them to the screen.

So you can see the bigger the value of gamma,

the quicker the decay.

That makes sense.

You could check the output of this

by actually knowing that there is an integral function

given here.

And you'll get, within that set tolerance

we've given the solver, the same value.

So in this case, we can check the output

from our integral solver

because we know what the answer should be.

We don't need to solve this with Python,

but it's just illustrating that you can.

And it'll do it really quickly as well.

Now for the more complex systems,

we do actually put in the Lorentz system.

And that represents this chaotic behavior.

So it's a certain set of differential equations

where, imagine in this example,

let's say X is,

it's becoming worse.

X is one and Y is 0.5.

You might have an example looking like this

after say 10 seconds.

If that's 1.01 and that's 0.5,

it could be wildly different.

It becomes chaotic.

So we can solve it.

It's called deterministic,

but it has chaotic behavior.

It becomes, it looks like it's uncontrolled.

How do we solve this for the exact same workflow?

This is the output we're gonna get.

So you'll see this common pattern

oscillating X, Y, and Z values.

And that will change,

very sensitive to the initial conditions.

So we can change those.

Have a look here.

So we're integrating the module.

We're importing the modules, sorry.

We're setting some parameters

that the differential equations rely on.

But let's look at how I've defined it here.

So now we have not just one variable.

We have three, X, Y, and Z.

So in the differential function, the right-hand side,

I'm going to pass an array.

So what the numerical solver is doing,

it's passing an array of three elements

with different values.

It's testing how it can take the gradient

and then get to the next value of each of those

within its own strategy.

Also, always passing the current time T.

I know that according to the address in that array,

the first, second, and third element represent X, Y, and Z.

That's just something I've defined.

It's not something the computer's defining.

It's just the way I've defined my system.

I know that I'm gonna represent the X by the T,

the Y by the T, and the Z by the T

by writing the Python version of these equations here.

So again, we're using same equals sign.

We're using brackets.

But I've defined what X and Y are

from that array that's been passed.

I then return an array of DX, DY, and DZ by DT.

So X and Y and Z always match in terms of their positions.

This array represents the actual values.

We return the derivative values.

So we're doing the exact same thing as before,

but now we've gone from one variable to three.

It could be tens of thousands.

It doesn't matter.

But this function has to return the differential values

for our integrator to then turn that

into estimating what the actual values are over time.

I define a time at which I want the solutions again.

In this case, very high resolution.

I'm going between zero and 100,

but I want them 10,000 outputs,

so very high resolution in terms of time.

That's why I get this very smooth graph here.

And I'm calling ODE int again.

It's a little bit different here

because remember, functions that are in Python modules

often have default values.

You don't have to change them.

We always have to pass the name

of the function we want to integrate.

The starting values, so it's a boundary value problem,

and the time at which to extract solutions.

But I haven't set the tolerance here

because there are already default values,

and I'm saying, well, I'm happy with that.

You just solve it.

And typically, they're always very, very small.

So if you looked at the documentation,

you'll see what the default values are.

And then the solution is, rather than a two-D array

or a one-D, a three-dimensional array now, sorry,

two-dimensional but has three components,

the value of X, Y, and Z over time.

So it all matches in terms of size and output.

But what you'll find is this runs quite quickly,

and there's no way that we could generate manually

10,000 outputs for a set of three-coupled

differential equations.

And the code isn't that big, is it?

It's quite a small amount of code, yeah?

And the other example we'll ask you to translate

into that function format is the predator-prey equations.

So you'll see that we have a two-component system,

U and V.

Yeah, U is number of preys, V is number of predators,

so that could be rabbits, foxes, for example.

There are values associated with A, B, C, D, and V.

They're coefficients.

They represent natural birth and death,

but also the dependency on the two.

When one's eating the other one

and then the food supply diminishes

and you get that non-linear dependency.

When we solve them, we get that behavior.

So they're the three examples

you'll get in the notebook today, tomorrow even.

Oh, let's turn this off.

I'll just quickly look at that.

It's quite, it looks like quite a small notebook,

but I think really the most important thing

is to make sure you understand the link

between indexing, arrays, functions,

using pre-made functions and so on, plotting them.

If I go to practical five, practical five, isn't it?

Yeah.

There we go.

So the first example we jump into

is the radioactive decay equation.

That should be relatable quite quickly.

We solve that for different values of gamma,

but then we go into the Lorentz system.

Yeah, so have a look.

Make sure that you see how I've structured

the definition of the right-hand side,

so the differential equations in this functional form.

You can change the name,

but make sure the name is consistent

between your function name and what the solver sees.

You can change values, you can add some uncertainty,

see how the results change,

but the point being that whole workflow

will give you this result here, a chaotic system.

And then it's implementing the predator-prey equations,

which will give you that output there.

So you see, you have to define the differential equation

there and extract the solution,

but you can use the exact same workflow

as the previous example.

All right.

If you've come across other differential equations

in your course so far,

and you want to implement it in this way,

happy to do that as well.

All right.

But this is the point at which we move on from next week,

is to start looking at loading data in.

So maybe use it as a checkpoint

to make sure that you understand functions,

conditionals, arrays, and talk to us during the practical,

and we can sit down and go through those.

Are there any questions at this stage?

Well, I'll put the signing code.

Okay, and I'll see you tomorrow morning.

Enjoy the rest of your day.

Oh.

Oh, hang on.

It keeps defaulting to the one the week before.

One second.

Yeah, there it is.

I don't know why it does that.

That should work now, I think.

So basically, I've missed quite a lot of this semester so far.

I've been in contact with like DATs and everything,

so I can't say anything,

but yesterday, I tried to download

this Anaconda thing to my Mac,

and then so I downloaded it,

but then I only have like two gigabytes of storage,

so I had to delete some like same stuff,

and then I had the right amount of storage,

and I keep trying to re-download it.

We said it already exists on my Macintosh HD.

Are you doing it through getting it,

how you download it?

Just the Anaconda website.

It was just download from that.

Okay.

Even if it has control on it,

I'll come and show you.

Okay, because yesterday, in the engineering building,

I logged in, and I've managed to go up to the point

where it said, do you know when you're in the coding thing,

and you make an environment, and you click on it,

and it says open with Jupyter Notebooks?

That's what I can't get past.

It won't let me open it with Jupyter.

That can solve that problem.

Just one more thing.

Okay.

If you do want to have a look over the next 24 hours,

whatever, the Google Colab link,

if you've got a Google account,

should give you the exact same experience.

Oh, okay, okay.

But through your Google account,

so maybe click on that button on my GitHub page.

Yeah, okay, that sounds good.

Click yes to everything,

and then just see if that runs,

but we'll look at it tomorrow.

I'll send you an email tonight if I can get anywhere.

All right.

Yeah.

Yeah.

The kind of problem that you're solving.

Is it going to be,

I haven't seen you,

but is it going to be along the theoretical lines

that we've sort of done up until now,

or is it going to be more so like real world problems

like the credit rating framework?

Yeah, so the only non-real world option

will be the context-gaping plan.

Okay.

So there'll be a single notebook to select

that relates to a given week.

The workflow will be pretty much exactly the same.

So I don't know,

but that's the only non-real world one.

There'll be a credit frame one.

There'll be some statistics on meteorological data.

There'll be a geospatial one on there.

Is there like additional reading to do

in like the real world one?

Did you have an overview about that?

Yeah, so there's a rubric that I'll send you,

but more or less, you know,

the minimum will be to at least allow that year.

But if you want to have slower stuff to read around.

Like to be able to apply the code on.

No, not at all.

Do you mean just to like give background to...

That's exactly it.

Imagine if you were given it to someone

who wants to understand what the hell is the code doing

and why.

It's literally a basic introduction to, you know,

like earthquakes are important because of this.

Here's a database we're loading in a pot in the map,

and here's how the earthquakes have changed up.

So normally what I recommend

is get the code working first,

and then if you were coming with it...

Which sort of...

Yeah, so you can actually directly translate it

from the work to the practical level

into the best known one,

but you'll have to change some of the options.

Expand what it does a little bit.

So again, just to get the code working in general now.

So there's always headroom to do a bit more of all.

The good result is delivering exactly what's been given,

briefly describing what happens.

So everyone's on a really good head of position.

You see what I mean?

It's very hard to not do well in this course

in the sense that the people who don't

just don't do it, you know what I mean?

So I'm not, it's not a course to actually examine

what you can do.
