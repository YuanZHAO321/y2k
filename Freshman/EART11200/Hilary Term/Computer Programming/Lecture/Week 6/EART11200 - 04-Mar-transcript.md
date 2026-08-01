---
title: "EART11200 - 04-Mar-transcript"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 6/EART11200 - 04-Mar-transcript.txt"
type: transcript
---

'EART11200 - 04-Mar', automated transcript
01/08/2026
---

Okay, good afternoon, everyone. I hope you're all well. So

What we're going to do this week is turn very much onto an area of work

Which I think will benefit most of you and we're going to look at working with

data

So previously collected previously generated data

Loading into a Python environment and then doing stuff with that data and as

ever

There was lots of modules that we can use depending on the use case. So we'll

see today that we'll plot some

Data that has

Geospatial nature to it. So it has coordinates. We'll talk about that in more

detail actually next week because

There are whole courses on GIS geographical information systems

But we were able to load that type of data in next week

But today's very much starting to understand the whole process of loading data

in into a Python environment

And we're going to use something called pandas pandas is the module is the data

equivalent module

To numpy for arrays. So everything you do with data in Python typically will

require us to have these panda pandas

Data frames they're called. I'll show you what data frame is shortly. We can

build on top of that

So we're here

So this week and next week we will focus on geospatial

Geospatial data is really important across the whole range of degree pathways

Whether it's subsurface top of the atmosphere or even when you breach out into

linking that data with health finance

Socio-economic data a lot of government policies is really built on top of being

able to do that

Understanding the links of social deprivation to health and environment huge

area of work at the moment

And what you'll see next week is we can start making maps to integrate all this

data until it tell a story with it

Which is really getting you to the point where you're moving beyond just working

with

Numerical models data for actually delivering that data to end users that are

connected to your domain

And that's really useful to be able to do and then we came will will do some

statistical analysis and then week nine

We'll do some a little bit of machine learning

But all of the next four weeks are built on top of pandas

So what we'll learn today is loading the data in and then being able to in

Access the functions associated with this data frame so everything we've done up

to this point. We've created numpy arrays numerical arrays

They've been one dimension two dimensions three dimension

There's an address system right so we can access the first second third or a

whole row and column

We've introduced some logic to search through those arrays do something with the

data that we find

We're going to do the same starting from today

You'll find the pandas does a lot of the the grunt work for us

We will ask it to load data in but we can still introduce logic so we can

actually select a subset of data

According to some criteria and the specific example. We'll see today is we'll

have a global data set

Volcanic eruptions, but we've just downloaded from the Smithsonian Institute

and we'll be able to produce a map where we can specify the latitude and

longitude bands or

Specify certain date ranges for that database

So we start to become much more useful from the programming perspective today as

I said last week

When it comes to the assessment eat there are options and one is associated with

content today one of the associated with the content

Next week so as you get toward Easter you'll probably have a feel for

Mainly which week you enjoyed the most or which week you think you might get the

most of in terms of turning into a jupiter notebook

That you will then submit

So just a bit of a recap. I think we're already finding that Python comes in

various flavors

You've been playing with the distribution on the cluster so far the anaconda

distribution that has modules associated with it

But we've had to bring in our own

Typically when you if you download anaconda on your own laptop, for example, it

will normally have pandas with it

It's considered one of the fundamental modules linked to whatever we need to do

in Python

And we've stored information as I said before in arrays

But what we'll see today is we can store information in these data frames that

we can actually interact with

So it's a much easier way of working with data

It'll look like an excel sheet

But it's much more powerful than that because we can store multiple types of

data

And we can ask the data frame to do functions on the data

For example standardizing it doing some stats on it and producing plots directly

for us

Data frames have a plotting function as well

So this whole pandas module has grown over a long period to be something that we

all use day-to-day

We still might want to create our own function

So what we'll see the typical workflow you'll come across from this week will

load

Data into a data frame maybe manipulate that and then pass that data out into

another workflow

That might include a numerical model. So going back to last week, for example

Imagine that you had a database on a whole range of parameters that dictated

predator frame

That might be thousands of columns

It might be hundreds of columns you could load that data in

Get that data out of the data frame once we've manipulated it and run the

workflow. It really depends on the problem. You're trying to solve

But as I've said lots of times data driven work really dominates most of what we

do with programming these days

Part of that's being driven by AI

Because of course with no AI, there's there's no data. There's no way I it's

literally the the food on which AI sits lives and breathes

and it's always interesting to see what might be changing in terms of

Acting as a researcher according to technologies that are coming down the

pipeline

So if you ever get interested in emerging technologies how they influence

scientific procedures

How they may influence societal societal changes every year. There's a

consortium called the Gartner consortium

I don't know if anyone's come across these before they're a global consortium

And they produce a map or a hype cycle of where technologies are where they're

going and every year

typically you see a range of emerging technologies and as a scientist or even

someone working in the public sector in a scientific role you

Can kind of get a feel for what's coming down the pipeline and what you might

need to be wary ready for if you like

So in this example

What a hype cycle what a hype cycle represents?

The hype cycle is where at the bottom left of the diagram you have an idea so

someone has come up with an idea

Brand new technology, maybe two or three people will create start working on

that technology

And the more and more that technology is developed our expectations rise

To the point where it reaches this peak of inflated expectations. We think it

can solve absolutely everything

so

That's an important point to get at but the most important point is after that

period when more and more people adopt that technology

We realize it can't solve everything. Well, this is a really useful stage to go

through

Because during this trough of delusion man, which for me represents a Monday

typically and it's reaching a stable state

Yeah, so it's reaching a state at which we can trust the technology

So scientists are starting to use it members of the public are starting to use

it

There's this hole for all that's decreased from the peak of inflated

expectations

So a lot of work I do at the moment and you'll actually find within the timeline

of your degree that we're starting to embed AI driven

Tools that influence what we do generate code write text and other things

Spending a lot of time with that at the moment. I'm still finding there's lots

of

inconsistencies generated from these tools

But the important thing is this was the hype cycle produced last summer and

generative AI

Which was in 2023 was at the peak of inflated expectations is already entering

this trough if delusion man

But that's a really important phase

Because really we wanted to get over here

So when we look at the machine learning notebook in the final week, we'll be

using machine learning. We call them stacks. I

Layers of different bits of code

That's pretty mature. We trust it. It's been used

For many many years hundreds of thousands of papers written based on these

technologies

Generative AI isn't quite there yet, but it does mean probably in two years

time. It will be

So I think in terms of data driven technologies if you're really interested in

exploring the wider implications of these

These kind of reports are really interesting to read and there are other there

are other things up here

AI augmented software engineering. That's what we're talking about here. I eat

please write that code for me

I want to solve this problem write the code. It's currently here

Still at the top of peak of inflated expectations, but there will be

Some demonstrated use cases in the media pretty soon

I imagine where that's created a big problem and there's been some errors

associated with that and obviously there's a huge

Media narrative around this at the moment exciting narrative. But nonetheless,

this is where technology comes down the line to us

So there'll be lots coming down the pipeline

But the important thing is an interestingly when we work with employers in this

space

You think that everyone's searching for someone who can work with models and

algorithms

Yes, there is an element of that

But I actually this data science process is much more than that. So we focus a

lot on models and algorithms at the moment

So we get a lot of people who want to dive in and start building their own deep

learning

Algorithms they want to play with large language models to generate things

But there are so many people doing that. Where's the niche and the niche tends

to be in all these elements here

This was published in 2013 and it's still true today

So we've talked about a lot. I've talked a lot about scientists working in

certain areas

You might become one of those you might come work in the public and private

sector

Whatever you do after your degree if you're involved with anything where data is

collected

There is a number of steps of which there's an expected

Recognition before you get to building models and algorithms

So what we're going to do today

We're assuming that someone's collected some raw data for us we're starting on

the far left

Then you have to process that data. You might have to clean it

You might have heard the phrase garbage in garbage out if you fit a machine

learning model to garbage data

It will produce garbage. So there's a lot of discussion around this at the

moment. What's the quality of the data?

What's the IP of the data as well?

I mean, there's a lot of legal cases at the moment if you publish a model and an

algorithm

But it's been fit to data where technically technically you shouldn't have

access to that data

It creates legal problems down the line

So universities are panicking about this at the moment, right?

Because if we're generating new frameworks on the right-hand side and we're

publishing those they're entering policy for the coming back to reality

There could be legal challenges down the pipeline. So there are so many things

trying to catch up with just the models and algorithms at the moment

But what we'll do today is we're going to work with a framework that allows us

to do

Data the data processing cleaning EDA

So EDA or exploratory data analysis is a term that you would start talking about

if you were moving into a

Sector where AI is being used predominantly. So EDA is critical to AI basically

means

Being able to understand the data before you do anything with it. Are there

errors in the data? Do you trust it?

Do you need to go out and collect more data? How do you present the data? What

are the statistics?

So from this week next week in the week after we'll do all those things before

we fit a machine learning model

So that's how the next four weeks connect to this particular workflow

Then of course, you can fit a model in an algorithm

whether or not that's a large language model whether it's something smaller and

then you try and communicate that and make decisions on the back of that or

Generate a data products which informs us how we operate in the real world and

that could be a policy change for example

So all of this is quite important and in terms of again employers looking for

people working in the digital space

If you can speak to that narrative more broadly, it's surprisingly a competitive

place to be

If anyone's ever interested in this wider ecosystem beyond this course happy to

talk talk with you about that

So pandas what is pandas? Well, I've said a number of times it loads data in it

allows us to work with data

But what do we mean by data because you'll you'll guess you'll predominantly be

used to working with Excel files comma separated value files

In earth and environmental science, there are so many different file formats and

you'll find that each particular domain might have their own preferred format

So when I'm working with people who run climate models, for example, they will

store their data in what's called net CDF file

It's a human readable file

What I mean by that is you can open the file and read some English narrative in

there

But some files you can't read at all. So people working in big data

Sectors, for example, they'll use something called the parquet format

She's really highly efficient format very quick to load very quick to save saves

energy and storage, but you can't read it

It's completely garbage. You couldn't determine what's in there. So you need

special tools to work with the data

Pandas can work with all of them. So this is why it's a mature tool. So if

someone gives you a data format

Whether it's net CDF, whether it's HTML CSV, whatever, it means that there's a

function in pandas

The reader function we can read a CSV file, read Excel, read parquet, whatever.

We can also write to different formats as well

So this is great. That means we can interchange different data products

So as you pick your pathways on your different degrees, you'll come across

different data formats, but you'll find that pandas is an all rounder

So you can load those data formats in. What we'll do next week when we look at

GIS, we'll work with things called vector files, shape files

They're a particular file format that will need a geo pandas to work with. But

again, it's pandas underneath

It's just a community developed certain functionalities to work in certain

areas. So it's a really good place to start today

We're gonna look at loading data in so we can interact with it in the sense that

it will look like an Excel sheet

But it'd be much more powerful than that. And the reason that's important

Imagine someone gave you a JSON file. So JSON files are very common in Internet

of Things networks

So this whole building's full of sensors. Outdoor there are network of sensors

that we manage. They're collecting data on the environment

They're throwing that data back into a server. They're collected in that format

The reason for that is not because we've said, well, we like that format.

Typically certain

Policies require standards are met. So data standards are, please use that file

format

So if you're working in environmental policy and you're working on collecting

data

You will have a whole set of regulations and standards to abide by

So the JSON file format is one if you're working in IoT

Now you can open the file and actually look at this stuff we can read here,

right?

But what I'm in solely interested in is this point here an ID and a name

So you can imagine that on a spreadsheet, one column with the ID, one column on

a name

Why on earth does it have all this extra information here? Well, we call that

metadata

So metadata is data about the data

Which sounds a little bit abstract, but it's really important because again

going back to the whole AI narrative

Understanding where data comes from, who collected the data, who owns it, when

it was collected

What was the instrument used, what were the conditions that were all of that

information can be held in metadata

So there's a provenance that you can go back to look at the state of things that

collected at the time

But we don't want we don't want to have to go through each of the this is a

single entry as well

If you had a JSON file with 200,000 of these

You're not going to have to cycle through each one and pull those out but pandas

will do that for us, which is great

So we don't have to worry about that

But we know it exists and if we want to pull that data out, we can

Another common file format you might come across is netcdf. So climate data is

stored in netcdf files

We won't work with netcdf data in this course

But if you're interested there are Python modules for loading netcdf files and

you can visualize them like this in the notebook

So imagine that you've got a climate model over the planet

You might have a cube of temperature data

And what I mean by that is each of these layers represents a vertical slice in

the atmosphere and each of the XY

Coordinates represents the grid over the over the planet. You might have

precipitation and matching latitude and longitude

So they're stored in a particular file format and if you were to open that and

preview it

It looks very similar to a JSON file, but it has very subtle nuances to it

And again, I don't want to write numpy code, for example, that's going to loop

through each of these entries and pull it out

So pandas can do that for us

So what we'll do is we're going to load pandas in as a module as we've done with

every other module

Like numpy, there's a particular format that people use import pandas as pd

It's just changing the name and then of course what we're going to do is access

many of the functions that pandas has

Using pd dot something. Yeah

It will look like a spreadsheet

But the difference really is we can include

multiple file for data formats in the different columns

We'll have certain ways of indexing them

So for the first two for this week and next week, we won't be concerned about

the index

But when we get to statistics, we can turn the index into a timestamp so that we

can tell pandas

Just give me the values at 9 a.m. From a million observations that would set

that saves you hours and hours of development

Okay

It's very efficient. It can be two-dimensional. It can be three-dimensional

It doesn't really matter but we'll work with it in the same way that you're used

to working with spreadsheets really

So in the notebook associated with today will load pandas in there's a data file

We've already provided though the eruption results was just a file I downloaded

from the Smithsonian Institute

And it has information on volcanic eruptions that have occurred throughout

history

And of course, you can imagine the further you go back

There's more and more uncertainty of how that information was captured, but

there's lots of data we can play within that file

The important point to start with is this line here. So data equals pd dot read

CSV

I pass that function the name the location of my CSV file and this line creates

this data

Well, what is data data is the data frame?

I could have called that anything but the data frame is what we then operate on

so we load data into this

This data frame and then we're going to actually

Use a lot of functions of properties that data frame has for example

This head brackets closed brackets function just gives us a preview gives us a

preview of the head of the file

And I can specify the number of lines

I want to preview but that's the first thing we do load the data in and just

check it and we can see what?

Information we're pulling in in this case the number of ID of a volcano its name

When it occurred when it stopped its locations evidence method, for example, and

we're gonna work

We could do a lot with this data, but we'll plot it onto a map and we'll start

pulling out subsets using

Some logic but notice again the dot operator again, that's a common way of

accessing

Functions and properties of anything in Python. So again, we're working with the

data frame. So we'll do the same

We can interrogate the properties of that data frame

So data dot size dot shape and in number of dimensions when we print those to

the screen

We can see that in the shape of the data frame that outputs

Number of rows number of columns so we have now

9891 observations and a fair few number of columns

So it gives us a feel for what the data is we're loading in

Because at this point on you really want to make sure that you're again

You're trusting the data that you're working with moving forward

If you don't preview the data and then you start getting a load of errors when

you're doing numerical operations

It might be just you're loading the wrong thing

Okay

On the right hand side

In this case, we've got many different volcanic eruptions in the database

I just want to see a unique list of the different names

What I don't want to do is have to count manually all the individual names and

then tally those up row after row after row

if we can specify a

Function to operate on a particular column. So the name of the data frame and

then square brackets and that this

string expression here is

Specifying the column name. So data volcano name is saying right Python

I want you to count the number of values of individual and unique entries on

this particular column

And this command alone will give us that list so we can see that our database is

dominated by Mount Etna

But we also have at the other end

individual eruptions that are actually collected in our data frame

That's just an example of how we can jump dive straight in start doing some EDA

exploratory data analysis to the data that we've got

We can apply the same functions. We did on the entire data frame to a particular

column

So I'm highlighting here. I'm

Singling out a particular column in my data frame then operate and end in the

size and shape and pulling those out

So we'll do this over and over again because what we want to do is solve

particular problems now

So we're getting away from very abstracts

Examples where in the first few weeks, we started just creating random loop

arrays random functions

We're gonna actually now contextualize this much better and actually plot plot

maps that make some sense. We can visualize what's going on

We can extract values from a column as well. So imagine I wanted to find the

minimum

So the earliest date in our in our record

I can't guarantee that the entries in my data frame are done by order

So someone has gone from the most recent down to the earliest

so this function here

name of a column dot values

Extracts a numpy array. So this is why the two were interchangeable

So we could actually extract data into a numpy array and then do anything we

want with that anything we've done in the last few weeks

So this line here is extracting the values from this column into an array called

years

Then the function min from numpy numpy dot min years just gives me the lowest

value

So this is just an example of how in two short bits of code. We've loaded this

database in

We want to we want to pull out the earliest eruption and this is the

Python code to do that

So there are many different examples of how we could do that

Imagine that we've got

Columns latitude and longitude and want to extract values from those and this is

exactly what we're going to do because we're going to produce a map

So we're going to bring in another module to take our coordinate data from the

data frame and produce a global map

With individual points of where our entries are now that module to plot will

require us to give it numpy array

So again, we're working with the two most common parts of Python

Pandas

So this line creates a numpy array of latitude values

So I have a column called latitude and I could have gone back to that the

initial code where I'll see all the

Column names are available

Data latitude values produce a numpy array latitude. I just called it latitude

It doesn't matter what the name is and the same with longitude

So what we'll start doing now is then throw in those arrays into a plotting

function and producing a map

We could be specific as well. So remember when we introduce logic into for loops

We could specify if something was true or not something was greater than less

than or equal to how do you do that within a data frame?

Well, you don't have to pull the data out first. We can actually ask the data

frame to just give me data that match a certain criteria

So let's go back to the original code example where I had data dot head brackets

closed open brackets closed brackets

That gave me a preview of the top five line now I say well, I'm only interested

in the eruptions that started in 2019

So we can specify anything in our data frame using this logic statement here

So again, I use the square brackets open and close but rather than specifying a

column name

I'm specifying when something needs to be true and we can chain these together

We could up so in this case, I'm saying please only do this when this is true

So when the data held in this column is equal to the 2019 only I could chain

that with other

Criteria I could say will only give me 2019 when these coordinates are matched

as well or when a name is matched

So this now is basically creating a new data frame this on the left-hand side

before the doc

We'll use that over and over again over the next few weeks next week. We'll

specify we'll cut out data from a certain

Political boundary on a map and the week after we'll pull out data from a

certain monitoring station in a different country

But all of these depend on telling a data frame

Please only give me this data that I'm interested in rather than the whole data

and then we can start narrowing down whatever we want to

Do afterwards and you can see that this is true on the column on the right-hand

side here. Oh

Sorry in the middle here. So it's only showing me data. That's from 2019. So

that's giving me a result

Typically if that wasn't working you get an error you wouldn't it wouldn't give

you the wrong answer

So again, we're trusting the technology to give us an answer that we're

specified

I can chain things together now this starts look a bit complicated quite

quickly, but it's getting used to the syntax

So remember that we have nested for loops. We have specific conditional

statements within those loops sometimes

I can also chain those together in a call to our data frame. So there's a lot

going on here

Basically going back to that original example of pulling out latitude and

longitude values

Rather than the whole globe now

I only want to bring out a band of data around them around the globe. So data

that sits within a certain

Latitude so upper limit and lower limit and then plot that in a map and we'll

see that this is true

But I'm saying that I only want data between 40 and minus 40. So it's the

central band around the world

So

I'm pulling out values from the column latitude

So just just focus on the right hand side here and I'm pulling out

Values from the column longitude and I'm passing those into I'm saving those as

an unpy array

But there's a lot going on in the middle here

So if we weren't interested in this specific subset, I just use data

Latitude dot values, but here in these curly brackets. I'm also saying only when

The information in the latitude column is greater than minus 40 and the

information in that same column is less than 40

Yeah, and same with the longitude values

So I'm being very specific here. I could chain that together with an and

Data start here is 2019 if I wanted to you can make it as long as you need it to

be

but that's saving a lot of effort on our part because we're not extracting the

data out into a numpy data frame searching for

Latitude longitude values creating another numpy frame. It would get messy quite

quickly. You probably create some errors

So what does this be in terms of geospatial data? Well, specifically the data

today will have coordinates associated with them

Next week also will but many different types of coordinates. So we'll have to

interchange the two

Pandas and geo pandas pandas today and geo pandas next week are the most common

modules in Python

Has anyone worked with Google Earth Engine?

Yeah

So Google Earth Engine anyone with a Google account

So if you've been working with Colab up to this point, obviously, that's a free

instance of a Jupiter

Notebook type environment, but you can also play with Google Earth Engine if you

want

So you can actually log into Earth Engine and start looking at satellite data

products, but that's based on Java JavaScript

But that gives you access to huge wealth of geospatial data

There are Python interfaces to Google Earth Engine as well called GEE maps

So you can pull data from Google Earth Engine into your Python environment and

plot it onto a map

Which could take a while to download but that's true. The point being if you're

interested in doing more on geospatial data

There's a whole ecosystem of tools out there. Google Earth Engine is really

popular because you deal with lots of big data sets in the cloud

So you don't have to download it onto your disk and then it would just be

impossible to work with

But we can pull the data from Google Earth Engine if we're interested in that

If anyone's interested in a demo of Google Earth Engine in the practical

sessions

Let me know and pass on some code so you can get a feel for it

But what we're going to do is work with another module called Car Toppy

Which basically takes what we extract from a data frame

Particularly coordinate systems and produces a global map

Car Toppy is quite old

It's still in use. It's still quite popular

The tool we'll use next week is a step up from that

But you'll get a much of a better feel for playing with pandas separately today

tomorrow

With Car Toppy and then use GeoPandas next week

It will look exactly the same but GeoPandas can deal with much more complex

shapes

And we'll talk about that next week

But Car Toppy allows us to produce this plot here and in fact the notebook

associated with today is the

Plot you'll produce and these are volcanic eruptions and you can start to see

some structure already

It makes sense because they follow plate boundaries

But we could select a subset according to our interests

But the workflow is still the same

We'll load a CSV file into a data frame. We'll extract the coordinates using

data frame

Conditional statements and then pulling out numpy arrays and we'll pass those

arrays to Car Toppy to plot

So the first example you'll come across looks like this

As with all the other figures that we've done in the notebooks, don't worry

about the syntax

We provide the template for plotting what just so you're interested Car Toppy is

imported here

Along with MapPlotlib and Car Toppy really is like a map canvas that MapPlotlib

recognizes

So it recognizes we're going to plot maps onto a map. It has certain projections

These lines here again, don't worry

There are certain projections, map projections if you come across this before

There are different ways of representing geospatial data and producing maps

Again, we'll specify all of that next week, but this line acts stock image

basically

produces this global stock image map

So it looks like Google Earth. It looks like Google Maps

It's not and again what we'll find next week because there's so much more to

GeoPandas

Is if we could actually change the style of these maps to look like OS maps,

Google Maps

So on and so forth. The key lines are here. So we've loaded the data frame in in

a previous line

I'm extracting latitude and longitude

coordinates

The MapPlotlib function plot scatter produces a scatter plot, but it plots it on

this canvas

This global canvas. So I'm passing it a latitude and longitude array and

specifying the color of the dots

Remember all functions have default values

So the scatter function within MapPlotlib, if you open up the documentation we

can change the shape of the dots that we're using

You'll see there are certain

Characters that we can change to change whether it's a point marker, a circle

marker, triangle

We can change the color. We can change the width so on and so forth

But the plot show line creates us that. So there isn't that much code there from

loading that database in

Into a data frame extracting the coordinates we can produce something that makes

sense

So if you're just staring at the data frame, it would be hard to understand what

the relevance of some of this is

Producing maps is a really powerful way of communicating your data

Really really important tool within the earth and environmental sciences of

course

I said previously I wanted to be specific

So the way that we change that code if I want to just produce data plot data

within certain latitude boundaries

I talked about that

The upper and lower limit going around the planet I've done that here, so I'm

using the

Conditional statement within the call to latitude and longitude values

And I'm simply plotting the same using the same code and now it's done what I've

asked it to do so it makes sense

You can change the color for example according to the year of the eruption or

the magnitude of the eruption

So you can make your map much more visually appealing depending on who you're

trying to present it to

So just have a quick look at that notebook

So usual format if you are working in colab there are a number of lines here,

but if you run it it will install

Car toppy and other modules that don't exist by default in a colab instance

So you just run that don't worry about it, but the first bit of text is talking

about the pandas package

What we mean by a data frame

But then we load data in directly so we're loading our

CSV file you can see up you can find all the data sets

We've got in the data folder with the repository do a preview

And if you see we can interact with the data in our notebook

Interrogate the size and shape of the data frame, but then start producing these

geospatial plots

So we'll use car topic to produce a figure we can actually change the figure

size so in this case

It's eight by eight. I can double that 16 by 16 so quite quickly you can start

modifying

What you're trying to produce for someone?

Then I extract latitude and longitude values produce our first plot quite

quickly

You can play around with some of the default options here as well if you looked

at the scatter

Documentation you'd be able to create green different size different size

markers whatever you want to do

But then we'll plot

The locations and change change the color of the markers as the first exercise,

but then we'll select a subset

Quantify the number of unique locations

Plot the location of eruptions in 2019 aren't that many so obviously we start

really reducing down the data

We're working with

But also plot the eruptions within a certain geospatial region

The other thing I haven't talked about is data frames have functions to actually

produce histograms

So as well as looking at unique entries in a column we can actually look at

statistical plots

So here we can actually see the distribution of entries in our data frame

according by year and of course you start to think well

How accurate are some of these?

Observations how baby we don't do that here

We're not I'm certainly not a volcanologist, but if you were if you were digging

deeper into the area

You can start producing many more plots when we get on to week eight we do

statistics with data frames

That's where we'll use another module that really really helps here

So we can produce statistical plots of the data in our columns really have a

feel for where data is skewed

Is there a bias in the data are we missing values are there values that just

just don't make sense

We need to cut those out. So that's why the next three weeks that really build

up that EDA

Approach to data before we fit a machine learning model and I as you go down the

exercises

We just get more specific. Okay, so hopefully this gives you a feel for what

pandas can do

And then we'll take it much more we'll take it a few steps forward in the

preceding weeks

And anyone's got any questions on anything to that point? Give me a shout, but

of course happy to go through things in the practical tomorrow

Cheers, you're free. Oh you are code

Maybe but my emails are so if you got any questions about practical

You
