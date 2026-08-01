---
title: "EART11200 - 11-Mar-transcript"
source: "Freshman/EART11200/Hilary Term/Computer Programming/Lecture/Week 7/EART11200 - 11-Mar-transcript.txt"
type: transcript
---

'EART11200 - 11-Mar', automated transcript
01/08/2026
---

Okay, good afternoon everyone. Hope you're all okay. It's got a bit colder,

isn't it? So hopefully the

warm weather will return quickly

so

We're staying in pandas today, but we're going to look at specifically a

geospatial

Adaption of pandas which turns out to be really useful. So we're going to be

talking about GIS today. Has anyone

heard of GIS before

Has anyone used ArcGIS? Have you heard of these software platforms?

So if you go over to geography, for example, they do lots of their work around

ArcGIS

So that's a software product that's also installed across the campus and it's a

particular

environment for working with geospatial data

It's actually a pretty highly sought-after skill

in a whole range of companies

But again, it's just learning how to work with another software platform to deal

with GIS data

What you'll see today and tomorrow is we can actually do a lot of the

functionality in

Python and the great thing about this is because it connects with other

modules machine learning modules

Statistical modules we can just build and build and build our

Ecosystem if you like to make it much more powerful than it was when we first

started this course

So

We're pretty advanced now in terms of the course layout this screen is not

working

I don't know why sorry today, but hopefully you can see that so we're in week

seven

And I think it's it's worthwhile spending two weeks on geospatial analysis. I

think I've said a few times

I think this is definitely one of those areas that's of relevance to pretty much

any pathway you pick in your degree and even if you

were doing

Solar system work you can still wrap

Data in a GIS format from other planets, but it's a real. It's a real scratching

the surface

Part of the course today. You'll see the notebooks probably looks feels quite

large

It's because GIS GIS has a lot to it

And how we deal with geospatial data, but because we're going to be producing

maps

Hopefully you'll again see the direct potential use of what you can create from

today and also while we're here today

I'll point you to various sources where you can find a whole range of GIS data

across the UK and globally

So this is a big community that we're walking into today

The following week so next week

Looking at statistical analysis, so that's just doing stats on data in a pandas

data frame

And I think after today the probably most directly useful to all of you

You'll all use stats, but but in terms of data driven work the machine learning

component in the final week

It's probably the most useful and one that you can again take much further than

you'll see in this course

You could do a whole course on GIS there are courses on GIS at the university

but we're just going to show you what you can do in Python that will hopefully

be of relevance to

Whatever you do and as I said before in terms of the assessment so the notebook

today

Links to a an option for you to pick so you'll actually repeat what's done in

the notebook

Associated with this week, but turn that into a Jupiter notebook yourself, which

looks like a mini report

Okay

so

So we've started the data science process and that's key so data science isn't

just about machine learning model development and fitting

That's definitely the people the element people focus on the most

Certainly in the media and across the wider public narrative. So what I'm

talking about there, let's get a pointer out is

The models and algorithm component

But what we're doing is really building up the other parts of the data science

process

and we've been using pandas to do that and that really lifts the work that we

have to do in terms of

Directly dealing with certain different data formats different types and really

reducing the effort

We need to put into a particular workflow to get something out of our data

But

What we're talking about really today is geospatial data in a more formalized

way

So last week you worked with data that had a geospatial element to it

I had coordinates and each coordinate had the location of a volcano. For

example, we produced a map

So we use matplotlib and kartopi

But there are much more useful but much more complex data formats when we talk

about geospatial data and the overarching

Description of this is GIS so geographical information systems

So ArcGIS for example is a software product and QGIS

Which is the open source version of that to deal with GIS data

Esri are the big company global company that developed that software product and

Esri were the company that define a lot of the shape for

The data formats we use in this week's practical and more broadly globally

Okay, the university is actually working with them at the moment

So we've got a project to develop a brand new window to the entire

UK's environmental data holdings and then push that out into the NHS for example

So our patient records are held a tagged with GIS data

So it tags where we live where we work for example

So then we can start researching potential determinants of disease progression

and other things so GIS isn't just about geography

It straddles the whole range of scientific disciplines that have a particular

impact angle to them

So what we're really talking about is thinking about data in it in in form of

layers

And hopefully you'll see that in the notebook that will run this week

So we're going to load different data files in but then we're going to overlay

them on a map and we think about that

In terms of data layers and in terms of the real world there might be different

data layers

We're interested in but all these data

Products might be held in different repositories different locations. So for

example in my area of work at the moment

I'm interested in

Predicting how air quality might determine disease progression in sensitive

parts of the population

So I have to push my data into the NHS

They will then combine that with sensitive data

But it all has the geospatial element to it for me to get a feel for that

It's not just air quality data that I want to load into Python. I need

information on land use

Probably need information on transport and mobility

Socio-economic data so we can actually see where pollution might be having the

strongest impact

Typically you find in terms of pollution

It is the low-income neighborhoods that suffer the most and you can get a feel

for that once you produce a map

But producing that map requires us to bring all that data together in in form of

data layers

And that data as I said before is held in different locations. So you'll often

hear

Terms such as interchangeable formats

So normally a community will agree on the data format that they're holding their

information in

So that it can be combined with other data formats

so the great thing about GIS is the broader area of work and what's happened

over the last few decades is

a lot of these data products will be in file formats that we can combine and

The whole point of the geo pandas would look at today is that can do that for us

So in the same way that pandas could deal with CSV files net CDF JSON files

There are geospatial versions of those that this geo pandas can bring in and

produce this map and you'll produce a few maps in

the notebook this week

Once we think about data layers

Then we start to think about what the data actually looks like and what I mean

by that is

The resolution of the data and the shape the data has so this is best

illustrated on the right-hand side

Because I've said that we could bring in all this different information together

as data layers

But with the data that you use last week that had a clear

Coordinate to it right it had a location of a volcano so it had two bits of

information latitude and longitude

So we produce these dots on a global map. Yep

When I run an air quality model

Typically our a climate model what you do is you represent the planet as a grid

Yeah, and you want to make this grid as high resolution as possible. You could

have

Latitude and longitude on the different axes, but the point being the

information is stored in this grid

Okay

So these have very similar elements to them these represent certain points and

this represents a grid or a mesh

But you know in the real world certain natural systems don't really conform very

easily to the two things

So imagine that we have a river

And it might have certain features to it

It has a particular shape doesn't it?

Yeah

So we need a different way of representing

this kind of information as well because those data layers need to be able to

capture the different shapes and

The different shapes have different elements to them

So on this right-hand side here

The reality is really composed of different data formats and different types the

reality might be represented by this

Figure underneath, but that's composed of different layers

And it's the same way that images are put together right you can stack different

layers together to form an image

So we'll actually formalize what we mean by data. That's held in different

formats

Specifically we'll make reference to raster and vector data, and this is quite

important

now raster data given on the the schematic on the screen are

represented by

gridded data

And that's typically most of the data you'll come across if you weren't working

in GIS

If you're looking at climate model outputs if you were looking at latitude

longitude coordinates, they're represented on a grid

Vector data is much more complicated in

The sense that how do we represent a single entity such as a river?

When this is constructed of certain points and lines between the points

Yeah, so what we say is these these are vectors

They give us information about directions and connect points together

Vector data is much more accurate in the real world because what we could do

then imagine we have this volcano

But also we know that the volcano might have a certain

Might have a certain land footprint

So then we can represent that as better vector data

So you can get the best of both worlds really?

This obviously is much more efficient because they're single points, but now we

might want to represent

Characteristics in vector format to give you another example rather than a

volcano. Imagine. This is a factory

Chucking out lots of really harmful plumes

And this represents a neighborhood and there's a certain wind direction

Okay

Now the footprint of that factory might be much more complicated. It might be

represented by a given shape

Okay, I won't go near the whiteboard anymore

so

They have particular areas of use and particular

Use cases that will come across so if you can just see on the table here raster

data

Key characteristics of gridded format as I've said cellular values, but it's

resolution dependent and this is the key difference

When we're running a climate model, we really want to make these this grid as

fine as fine a resolution as possible

because if you think about it if this is predicting temperature or

precipitation or other climatic variables and

This is the UK terribly drawn UK

Okay, then really that's not giving us much information about certain political

boundaries here

We want to make that smaller and smaller and smaller as possible

Vector data on the other hand can actually capture the shape within a grid cell

So new climate models are being rewritten

So I have something called an adaptive mesh where you can go to real high

resolution over a country

But keep it course resolution over the planet. There are certain benefits to

doing that

But how is that held in terms of a file so

Common formats in terms of raster data include geo tiff

IMG images and examples include satellite imagery elevation data land cover maps

So a satellite that's providing a scan over the planet if it's not geo

stationary

We can convert that data into

gridded format

So there are certain file formats that adhere to whether it's vast rasta or

vector data

Vector data is more complicated because what vector data is doing is storing

this information so we can repeat the shape

So you'll often come across a shape file and that has the extension of dot shp

and within that shape file

It'll contain this information

So the data that we include in the notebook include

Geo JSON files shape files depending on where I've got the data from

If you remember last week, I said some data is human readable some isn't we

don't really care about that in this instance

Because we're loading data into pandas and in this case, we're producing a map.

What we'll do next week is do some statistics

Some data is human readable. So I gave an example of a JSON file last week

This is a geo JSON file and it's just pointing to a particular location

So it's a rasta data because it's a point on a map. Sorry, it's a vector data

because it's point on a map

It has coordinates for all this metadata as well

So vector data will work with geo JSON are also shape files. I couldn't read a

shape file

I can't read it using a text editor. It's not human readable

But there are benefits there are pros and cons for how these are stored

But we will load in geo JSON files and shape files

The geo JSON data will work with include political boundaries because what we're

going to do

Is show that when we can produce a map with all these layers we can cut out like

a cookie a cookie cutter

Data from the UK. So imagine I want to just extract

Data from Greater Manchester combined authority so that has a shape to it pretty

boring shape

But I can draw out for example geological information

Atmospheric information that are within those political boundaries that would be

really hard to do and very clunky

If I was working with a gridded data set because if imagine the political

boundary looks like this

Again, it's a complex shape

Yep, and my grid if my grid has a certain resolution that looks like this

Which grid cell do I pick? Well, I'll probably pick these ones

But I'm going to miss some information

Yeah, so it we can combine the best of both worlds and do that

so rasta and vector data

in terms of using

Python again what you'll see within the

Documentation is we're provided with a list of file formats that it can deal

with

pandas can read many but the key difference with

Geopandas is if you recall when we've loaded a data set into pandas and we've

previewed that it looks like

A spreadsheet right so we can see a table of our data

The key difference in Geopandas is we have a column now that is is called

geometry

And that includes information like this like that or like this

So what that means?

Previous last week we had a single entry for a volcano and that was that worked

Okay, because one column was latitude and longitude

Imagine that we want a single entry for the river bowling. How do we include

that in one entry into a database?

Using the approach last week, we'd actually have to have

Cut different collections of latitude and longitude coordinates all in different

rows, but what we can do with Geopandas

Is actually load a single entry for the river that includes its geometry

So you'll see it's a collection of these points that all join together

Which is great so now it becomes much more useful in terms of us looking at the

data

We can enter much more categorized data into this version of pandas. We can do

much more with it on

The face of it. It will look as pandas look last week, so you'll be able to

preview the data frame

You can look at the columns you can actually interrogate the data in there

extract a subset

We can do everything we do next last week, but we'll do that with geospatial

data as well

One of the examples you'll get to toward the end of the notebook this week is

producing this map

So you might recognize the location that is Greater Manchester combined

authority

So I had the different authorities all within that outer boundary

That is loaded as a GeoJSON file. You'll see that in the notebook. We're able to

produce this map

this

Blue blue shaded area a flood risk maps produced by the Environment Agency every

year

So we can now start to visualize

risk assessments

So if we know you know that last year there was particularly particular problems

with flooding

Particularly around South Manchester. We can see the risk maps here, so you can

see the spatial extent now for particular risk

So the Environment Agency have their own data repositories that you can access

for free. They're held in GIS formats

I've got the political boundaries from the council website and these red dots

are just substations

So power stations which again I've got from a particular website and I can start

to visualize

Potential risk and I've come up with a hypothetical scenario here of flooding

affecting power outages across

Greater Manchester

Whether or not that will happen

It doesn't matter the point being I've gone from loading data in with not that

much code to produce that map

And what what you'll see here is well, you'll be able to see it more easily in

the notebook

You see there's a shaded area around the dot

I've actually told GeoPandas give me a radius of a kilometer from around the

substation

So we can start to calculate distances as well

And you can start to think about where that might be useful

particular particularly useful around infrastructure risks population health

But also from an urban and rural planning perspective

We can start playing with all the data we want to tell a story with

We do have to do a little bit of work with the data we've loaded it loading in

so last week latitude and longitude made sense

But geospatial data also adheres to a particular standard. So you've probably

heard of different coordinate reference systems

So these are pretty much historical. So a coordinate reference system

Defines how your data is projected onto a particular style of map

So geological data will have its own

CRS atmospheric data has its own. These are all defined by particular

communities

We don't want to have to worry about that. We just want to bring the data

together and tell a story with it

So there are certain codes EPSG codes

They're actually

Historical from the petroleum survey group that represent a particular CRS

The only thing we need to worry about is making sure everything's on the same

CRS

Otherwise when we plot it on the map, you might get unrealistic

Geospatial patterns occurring what I mean by that is if you have

The data from the flood risk maps from the environment agency in one CRS and

then you might have data on

Public houses and another CRS if you plot them together and they're not on the

same standard

You might not get the right you might not get the realistic map once they're on

the same

Once on the same CRS system, you'll know that that's an accurate map

I they are the real locations for the metrics were interested in

The reason that these codes are different is because they depend on the system

or technology they feed into you

GPS for example uses this EPSG code for three to six

Doesn't really make a difference. You can have a whole list of different W EPSG

codes

But what we're going to do today is show that

We can actually can make sure they're all on the same code before we plot them

before we calculate distances and things like that

But pandas will do all that for us

so

What we what we'll do in the notebook is we'll load data into a data frame again

So we're still working with data frames the data frames still have functions and

properties

It just just that now we have this geometry column so we can still do everything

like subsets of data

But we'll produce much more

Useful maps in the sense of moving from car topic to geo pandas gives us much

more control

Over the type of map we can produce but also the calculations that we can do

So car topic was a good start, but typically anything you do with geospatial

data. You'll jump into geo pandas

So if we have a data frame, I don't know why that's not showing we can

interrogate the CRS

What what's hiding there is the name of the data frame dot CRS?

And when we print that to the screen it will tell us that the data has been

saved in British National Grid format

So we can actually load data from Office for National Statistics or ONS and that

abides by

Certain British standards if we pull in data from an American system for example

This is where we need to interchange the different file formats, but we can

check at every step

Are we doing the right thing typically if you get the CRS system wrong?

It will look ridiculous

So you'll show houses in the sea or your distances will be so large that doesn't

make sense

But it's good for us to test at least in advance

Because as we combine the different sources, we want to make sure that we're

actually

Merging them into the same data frame with the same CRS

Once we have the data in a data frame, we can go straight to a map. We can

actually use this code here

So what's hiding behind this display icon? Don't know why that is. It's the name

of the data frame dot plot

So the data frame now has a plotting function data frame last week did but a

plot would have given you a line plot a scatter

Histogram you've used those in the past

But now a geo pandas data frame has a plotting function and we specify the

column

We're interested in which which will plot the geometry of the information in the

data column in the data frame

But it will label the geometry according to this column this produces this map

of bedrock across the UK

So we're going to load a geological data setting into a geo pandas data frame

We'll check its coordinate reference system for each entry into the data frame

So if I can't really zoom in but look at this yellow patch here, that's a single

entry of a shape

so it represents a geospatial extent of a certain bedrock type and

The data frame will have all of these distinct areas of single entries

So it represents certain types of bedrock and that's given by the column RCS

Underscore D. That's not a column name that I've come up with. It's just a

column that's in the data frame

And there are certain

Functional options to the plotting function the figure size

The edge color ie the color between the different shapes the color map

So you can change the range of colors used for the different entries and I've

told it please give me a legend

There's another module we're going to use to make to plot the map that goes

underneath ie the base map

And you can change whether that looks like Google Maps ONS street maps and so on

and so forth

So this CX is a module I've imported somewhere else

But I'm going to add a base map to an axis and notice I'm specifying again a CRS

Number so everything has to match so we load we're going to load data into a geo

pandas data frame check the CRS system

Plot it onto a map and then to make that much more visual

Put a base map underneath which is a global map like we did with car toppy last

week

But context early is work is designed to work with geo pandas that will actually

pull a map from a server

You can store very very high resolution maps locally

So if you wanted to do a plot of a real high resolution system

Let's say a bend a bend in a river system a couple of meters

There are maps that are that high resolution, but they're very large

So the examples will work within this notebook are good for national and

regional examples

But you can find on that server and I'll give you points to all of these

Datasets very very very high resolution maps once you start getting to street to

a meter scale maps typically

You'll probably find you have to pay for them because there are companies that

actually produce really high resolution maps of cities

You can actually download data from Google Earth as well convert that into a

base map

So you can start playing around with lots and lots of different ways to

visualize the same bit of information

So we the universe is quite a wide campus, and we also have a humanities faculty

You'll find a lot of people in that faculty do the research around

human interaction with data

So we just want to produce maps that look good that tell a certain story that

make us understand

What's happening, and then we can write the science behind that but there are

experts who then can take that to another level

So you get to explore more of that the more you go through your light your later

stages of your degree

And there are many different masters options that you could actually take on

Geospatial analysis linking with humanities social sciences and so off so forth

It's amazing the power of a map what a power of a map can have in telling that

story

So we're going to load the geological data set as the first example, but I've

been talking about layers

so

As a particularly relevant relevant example, I'm clearly not a geologist. I

don't have any expertise in that area

But what I've done in this example is after we load the bedrock

shape file

We can also find data on historical collieries does anyone know what a colliery

is

It's a coal mine

So there were many across the UK so we can then get a historical database of

coal mines

We load that into a data frame

So see here. We have the name of a data frame. We read the file

Wherever the file is it has a shape file. It's a shape file dot shp if you can

see that

We can preview the data frame so ever but now

It's still vector data, but it's point data

So what we'll do is overlay on the original base map the location of the

different coal mine mines

And again that start to make sense because what you'll see is where those red

points are

Represent the appropriate bedrock that people would have mined through to

extract the coal

we then take that a little bit forward and

Then as I said really drill down in particular reason regions

So I've got political region information on the Greater Manchester boundary

so all I've done is take that entire national data frame that has the

Bedrock information the colliery information and then cut out the information

from Greater, Manchester

So think of it like a cookie cutter so you can clip the data frame and produce

that

So you can see the location of the coal mines across GM

Familiar with some of those growing up in Salford

Obviously a lot of them are close. Well all of them are closed now. I think well

they will be

But again you can tell a story with that and you can do it without much coal

without much code

So have a look at the code here. We'll look at it properly in the notebook

so

the

Greater Manchester authority boundary is held as a geo JSON file

So I'm loading that in into a data frame. I have an I convert that to the CRS

I'm working with so again

You'll get used to a workflow load the data in preview it

Make sure the CRS is right and then do whatever you ever you want to do in

merging the different data sets together

But there's a line here that has the name of a data frame and dot clip

What that means is with Geo pandas we can clip another data frame according to

the geometry

geometry boundary of another data frame, so

GM DF underscore WM is just a data frame of the political boundaries

I'm using that geometry to clip the other data frame and that produces a brand

new geospatial data frame that only has

Information within that space and that's what I'm plotting here. So I'm still

including information on the bedrock

I've still got the colliery data. It's just now a subset

Do you remember last week we did a subset according to conditional statements in

the data frame if we have a subset?

That's in a certain

Geospatial boundary we don't have to do that

We can just clip the data frame using that geospatial boundary because otherwise

we'd have to specify all the different shape

Features of this boundary. We don't want to do that

The example that we get to at the end as I said is producing a map of flood

risks

Produced by the environment agency. I've loaded a data frame in as well on

information on power substations

But I've wanted to specify to Geo pandas. Well, you've got the rest the vector

data

Sorry the point data on the substations. I'm interested in a risk zone

So this is just illustrating the many many different features that Geo pandas

has

The buffer function of a data frame allows you to create a distance around a

point

So if I want to create a one kilometer boundary around a point

I provide the buffer function with the value of a thousand because this CRS is

in meters

The coordinate reference systems in meters

so the buffer function

Recognizes the metric that the data is in and then creates a brand new data

entry that represents this boundary around my point

So you can you could do a boundary around the flood risk map. It doesn't have to

be a point data

I could actually do an a kilometer boundary away from the flood risk areas. Why

might you be interested in that? Well flooding produces a lot of

Problems in in housing it produces foot mold

Bacterial growth it impacts on human health. It's known to actually create

medical problems after the event

So if I want to look at distances away from the flood zone

I can use the buffer function to actually build that distance and visualize that

on a map

Does now that distance suddenly include social housing stuff like that

So that's why it's quite a powerful module for us to start working with but this

is the example you'll get to toward the end

Okay, and this is the plot you'll produce

if you wanted to we could focus in on stockpore or Wigan or

Trafford it doesn't matter we could extract the different parts of the Greater

Manchester boundaries

You could do whatever you want. You could look at a different part of the UK

You could load in the West Midlands Authority maps

You can do what the exact same thing the point again is this is an applied cause

and it's getting used to the workflow

And this is a common workflow in GIS. You could do the exact same thing in Arc

GIS

But it would look very different in much more interactive because Arc GIS is a

has an interactive window

If you like, we're actually developing code to do this

Right, so

I'll just close that and then I'll look at we'll have a quick look at the

notebook as I said before you'll notice

It's a particularly large notebook today

You'll find that some of the commands that you run will seem to take a while

Maybe a couple of minutes or so because what's happening there is it's pulling

that base map from servers and creating that canvas for you

Particularly if you're running on colab, it seems to take a bit of a while to

run

So the notebook will have

Information and everything I've talked about why GeoPandas is useful what a

coordinate reference system is

So do read through that you can follow the numbers that we use in the practical

content

But you can look up if you want

Different numbers and codes that you use in different domains. There are five

exercises

But there's an intro to GIS here

Reaffirming the concept of raster and vector data because if you were to search

for data as well

And I'll point you to a useful source

You might actually Google vector data if you're looking for shape files for

things like this

Or point sources, but also raster data if you search for gridded data and raster

data, you'll get that kind of information

Okay, what is GeoPandas what it what it holds will load it in again. So the

environment should have it

If you're on a machine that we set up properly the data frame will look as it's

looked the last couple of weeks

So this is the information on CRS systems and again when we load the data in

we'll check it

But then we'll convert it where we need to and this is the first map that you'll

produce so you can see it in a bit

more detail here

so it's information I've got from

British Geological Survey, I think so they have different resolution

Data sets different versions of these I downloaded a default one so you can see

the different types of bedrock here

so really getting a feel for

What's happening between loading the data in and producing the map and selecting

a subset of data?

One thing I didn't say in the lecture actually so look here

I've only plotted data on sandstone, but there are certain ways of

selecting a subset in a GeoPandas data frame

Remember in the previous notebook we call the data frame with a conditional

statement

Whether our coordinates were in certain boundaries

Well, we can also use functions such as the string contains this term

So this is the column that defines the category of bedrock and this function in

GeoPandas says will only give me

information when it contains sandstone

So the plot then really reduces the subset of data that is generated across the

national map

Okay, one of the exercises is just then produce information where there's

limestone in there as well

Point two is really key is this it's that concept of then adding the different

data layers

So we're going to load into the data file in and the data is on the collieries

the location of coal mines

Across the UK we can interrogate them there are columns that give us the name

latitude and longitude

Which nation it's in but ultimately we're going to then produce this map

Which makes if you had more knowledge than I have about this area

Maybe it makes sense that the bedrock is appropriate for people to have mined

through to extract the coal

But then clipping a data frame will merge two data frames together did that last

week and we'll do it again next week

Well, particularly do it next week, but then we'll use this clip function

To then extract data from certain areas, so there are many different ways we can

Work with GeoPandas. These are just common examples for these particular

exercises and then loading the data frame in from the environment agency as a

shape file

It produces a much more bigger extent than the figure I showed in the lecture,

but we'll narrow that down

Different flood risk types depending on the hydrological event that the

environment agency have modeled and

Then you'll load

You'll then generate distances. So you'll be able to load in data on substations

produce a distance around that point and

Then combine that all into a single map at the end. Okay, so there is a lot

there. It's quite an extensive notebook file

So don't worry if you don't go through it in the entire

Time that you've got in the practical tomorrow

But do give us a shout

There are so much more you can do with GIS. This is really just scratching the

surface

But this is the place to start and once you can combine the data in this way

You can do a hell of a lot depend really it doesn't really matter what your use

case is

So this is typically what you'd learn to do in ArcGIS as well, but use a that

particular software product

Okay, so yeah, so I'll leave it there if anyone's got any questions on anything

up to this week

Please let us know

Happy to sit down and go over things, but see you tomorrow. Oh, you need the

code don't you?

Second is that the right date? It's not the right date again, is it? I don't

know why it keeps doing one second. Sorry

They go that should be right now
