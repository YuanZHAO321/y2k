---
title: "EART29102 - 02-Mar-transcript"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 5/EART29102 - 02-Mar-transcript.txt"
type: transcript
---

'EART29102 - 02-Mar', automated transcript
03/08/2026
---

Hello. Good morning everyone. Thanks for coming. I've got a couple of

announcements just before

we start the lecture. Firstly, I understand there's a problem with some of the

podcasts

for this course. I thought it was just me, but it turns out some of you can't

get access

to the first few weeks of the podcasts. I am trying to sort this out. It's more

complicated

than I thought it would be. If I don't get any sort of resolution this week,

I'll re-record

them for you and put the links up in the Canvas site for the course. So

apologies for that.

I didn't realize that it was affecting everyone. Secondly, I've put the

assessment exercise

up for you. Hopefully you can get access to it. If you can't, let me know. It

involves

choosing one of four case studies, depending on your preference. Obviously you

can make

a start on some of those if you want, depending on which one you choose. But

obviously there

will be more information as you go through the practical exercises that will

help you.

So don't submit anything too soon. Certainly not before the Easter break, in

case you were

going to do that. So the information is there. Take a look and if you've got any

questions,

just fire them at me. And then the other thing is next week, Pete Grinrod from

the Natural

History Museum will be giving the lecture today, next week on Monday. It's on

remote

sensing and that's his area of specialization. And Pete's got an honorary

position at the

University of Manchester, so he's got some kind of interest in our students. So

anyway,

I'll probably come along at the start of the lecture just to make sure he's set

up correctly,

but just to let you know if you see a strange face next week. Okay, so this week

we're going

to be focusing on spatial statistics. The contents there, I'm going to say a

little

bit about how we take our samples, consider some descriptive statistics like the

average

standard deviation and this thing called spatial direction. Then we'll move on

to more hypothesis

testing with inferential statistics and how this relates to this concept of

spatial randomness,

which we mentioned last week. You remember I introduced spatial autocorrelation,

so we'll

talk about that again just to remind ourselves. And then we'll look at various

statistics

that you can use for spatial cluster analysis, so nearest neighbor, Moran's eye,

Gettyshawd

and kernel density estimation methods. Now I don't expect you to remember any

statistical

formulae or know how to perform any of the calculations for these. What I'm sort

of aiming

for is that you know how to use them and then you know what they tell you, what

information

they can give you, so that if you have a particular application, you know which

of those statistics

to apply. Obviously there's a lot more spatial statistics than the ones listed

there, but

some of the common ones that you'll come across. Alright so spatial statistics

then, what's

special about it? Well nothing really, it's just applying statistical methods to

spatial

data. So you're used to applying statistics to data, but this is kind of a

special area

looking at spatial analysis. Why do we do it? Well we want to minimize any

subjectivity

or bias that we might have when we're looking at maps and spatial data. We might

want to

find out if there are some trends or patterns in our data that are not obvious

just by looking

at it. And basically we want to question our data set and we want to have some

idea of

how confident we can be in the answers. So we need some kind of probability

measure to

give us confidence in our analysis. And just an example on the right there, this

shows

what's called a hotspot analysis using one of the methods we'll look at today,

the Gettys

Award, GI star. So here this is a compilation of data, I think from 2000 to

2018. So this

is 2008 to 2018, looking at surface water contamination of different metals and

showing,

in the Appalachian region in the US this is, and showing where the hotspots or

high values

cluster together for those different metals and other contaminants. And you can

see there

that the scaling gives you what's called a hotspot with a certain level of

confidence

and these are shown by these different sort of colors of green on the map here.

So what

that means is in one of those areas you've got high values associated with other

high

values and you have a level of confidence that it's not just happening by

chance. So

you've got a 90% level of confidence or a 95% level of confidence that this is

not just

a chance relationship. So you can't always be certain of course in statistics

but you

can apply a certain level of probability to your data. Anyway, more of that a

bit later

on. Let's first of all consider some sampling methods because any kind of data

that you

use, any statistical method that we want to apply needs a sample that's

representative

of the population as a whole and that's critical. Because if it's not

representative and we're

trying to infer something about the overall population of a measurement

quantity, then

our answer is going to be systematically wrong. So very often to try and find

out what the

data is and meet that criteria of having a representative sample, it really

matters

how we go out and collect the data. And there are a number of sampling methods

shown here.

So the one on the top left there, random, just means that every location in our

area

has an equal chance of being selected. So they're all independent, all those

dots are

dependent of each other and we just take a random distribution across that area

and

collect our measurement there. It doesn't matter what the measurement is, it's

the

actual location where we do the measurement that's important. The ones along the

bottom

there are more structured. So we've got a grid of sample points there shown as a

systematic

sampling. We may choose small areas at random and then select sample points

around those

areas in the clustered sampling method. Or we might take samples along a line in

the

form of a transect. Depending on what we want to find out, what our question is

really matters.

And then the other thing that's shown in the top right there called stratified,

this one

here, is about dividing your area into different strata depending on their

characteristic.

They share a common characteristic. So the example that's shown on the map here

subdivides

the area into topographic height. So it may be important for our particular

application,

our interest, to sample things that are at high elevation and low elevation. And

because

those areas are not equal, then we need to proportionally sample from both. So

if one

of those areas represented 40% of the total area, then we'd need to collect 40%

of our

samples within that strata. And the other 60% in the other strata. So we need to

sample

proportionally, but again we can apply any of these types of sampling to that

stratified

situation. And another example could be that the orange area here represents a

different

kind of habitat from the white area. Maybe you've got woodland here and maybe

you've

got grassland there, and you want to collect samples from each, but you want to

keep them

kind of proportional, representative of those two areas as a whole. And you'll

find within

a GIS, you'll find various tools that will help you to identify sample locations

depending

on your needs. So in ArcGIS Pro for example, there's a tool that allows you to

choose points

at random if you want to, or do some kind of transect or whatever you want to

do. It

will show you where to make your sample measurements. So this idea that we have

to have a sample

that's representative of course is very important and has an influence on how we

collect the

data or where we collect it. So let's turn our attention now to some descriptive

statistics.

These are ones which just summarise the data, and commonly our common sort of

descriptive

statistics that we use every day are things like the mean, so some idea of the

central

tendency of our data, how our data are dispersed, so that would be like a

standard deviation,

and importantly for spatial data, direction. So that's kind of different from

other types

of data you might normally use, because it's spatial, we have this sort of

direction that

we can also interrogate. And that might be important for looking at how

pollutants move

through a landscape for example, if we're sampling at different places, we might

be

able to track that with our directional trends. Now in spatial data we can show

that using

this little image here, so the central tendency of our data we obtain from the

mean centre

shown by this yellow circle with a black dot in the middle, and that's simply

the average

of our X and Y coordinate values, so that could be temperature that we've

measured

at X and Y, and we're just averaging all of the values in our data set. The

standard

distance is like standard deviation, it's just a measure of the variance between

the

average distance of the features to the mean centre, so it's given by this large

circle

here which represents the distance scale over our measurements from the central

value here.

And then the extra thing that we have is this standard deviational ellipse. So

here we're

calculating separate standard distances for each of the X and Y values. In the

standard

distance itself these two are combined, but here they're kept separate. And this

forms

an ellipse, so in other words if we've got a lot more variation in our Y value

compared

to X, then it's going to elongate the ellipse in a vertical sense, a lot more

variation

in Y than X can give you, and vice versa. So let me try and illustrate that with

a real

world example. Again, you don't need to remember any of these statistical

formulae, so you

can just ignore those if you like. Okay, this was from a paper that was

published a few

years ago. Here's Washington state in the US, sorry, shown by this black shaded

area

here within the US, and this is just a blow up of this black shaded area here.

And the

wildfires that occurred between 1970 and 2020 that are greater than 100 acres in

size.

So they're all the recorded wildfire burns. And then these on the right hand

side shows

the directional ellipses for each decade going from the 1970s up to the 2020s.

And these

are the 2020 shown in progressively darker colours. And you can see how the area

of burns

has changed with each decade. Generally it's got smaller and more concentrated

here in

the north east of the state. So you can see how useful that is in giving you,

showing

how things are changing over time. The areas of burns are becoming more intense

in the

north east part of Washington state. Okay, well descriptive statistics are

reasonably

easy to understand. Let's move on to what we spend probably more interest is

inferential

statistics. Now I'm sure you've done this in your first year on your statistics

course,

so hopefully this is something of a refresher. So inferential statistics means

that you're

trying to infer something from a population based on the values you have in your

sample.

Okay, so we can't go out and measure everything, so we collect a sample, we hope

that it's

representative of the population, and then based on the characteristics of that

sample

we try and infer something about the overall population. And usually we want

some degree

of significance, and that's usually measured in terms of probability. So we need

some level

of confidence, significance, that the observed spatial pattern that we have is

not likely

due to chance alone, so it's not produced by some random effects. There are some

underlying

reasons why our data are distributed in the way they are. And that takes us into

the realm

of significance or hypothesis testing. So we need some kind of statistical test

or measure

that helps us to determine whether this is a random pattern or whether it's a

random

pattern that has some significance. So let's look at our baseline, if you like,

our randomness

to see what that looks like. So say we were interested in looking at the spatial

pattern

of the population density in the US. Now okay, I can go out and I can do that in

every county

of the US, which is shown by those black lines there, each one marking a

separate county,

can get some idea of the population and see how many people there are per square

kilometer.

And I can color code that where the darker colors are where you have a higher

population

density. And I can think, well, is that a random thing or not? But we can make a

random

population map, so the one on the right there, that's what it would look like if

the population

density in the US was entirely random. So where somebody lived was totally

independent

of everything else. And you can do the same with other features, so physical

features.

So there's an elevation map of the US shown on the left, where the various

colors represent

different elevations. And then if we randomize that, then that's what it would

look like

on the right hand side. So what we're doing here is we're setting up a baseline

or a null

hypothesis of randomness. This is what a random distribution would look like is

my observed

distribution of density or elevation. How well does that match randomness? So

it's not

realistic, it's a concept that we tend to test against. So in hypothesis testing

then

we set up a null hypothesis, sometimes called H0 or H0. And this is always

stated as being

that there is no spatial pattern or relationship present in our observations.

And that's the

same as you set up any kind of null hypothesis that you've ever encountered

before. It's

always that there's no effect, there's no correlation, there's no pattern, etc.

And

then we counter that, against that we counter it with an alternative hypothesis

HA, which

is the opposite to the null hypothesis. So there is a pattern present. And then

we have

to decide which one of those hypotheses we accept or reject based on some kind

of significance

level. So what's my probability cut off? Where I think if I'm more of a higher

probability

then I'll accept my null hypothesis. It's below that. I'll have to accept my

other

hypothesis. So we can think of that as a distribution, so a Gaussian

distribution. Hopefully you're

familiar with this sort of bell-shaped curve here of my random sample. And what

we're saying

is by chance how likely is it for me to obtain some value which is down in the

tails of this

distribution. And you can see that there are various things which are shown on

this.

We have z-scores along here. So z-scores just means that the distribution has

been standardized

and that's to remove units. Because if you take the average of something, it's

whatever

the units that you're working in. But you can standardize that to make it have

an average

of zero and a standard deviation of one. And that means you can apply any scaled

variable

onto your standard curve. Are these things sounding vaguely familiar to you from

last

year? And then down in the tails you have the probability values. So once you go

beyond

those, so here we've got our 90%. Once you exceed that 90% level it means that

you can

be 90% confident that your sample distribution is not part of this parent random

distribution.

So we're always testing against randomness. I've mentioned the z-scores. This is

just

basically showing the same thing again. So here's our distribution for our

random variable.

These are the z-scores here, 0, 1, 2, 0, minus 1, minus 2. So these are like

standard deviations.

These are our critical values. So if our test statistic is over in this area,

then we reject

H0, the null hypothesis. Similarly, if it's over in this tail here, we do the

same. And

you can turn this around. So if you calculate your test statistic and you obtain

your z

value here, then you can convert that into a probability. So you can either set

boundaries

for your probability or you can determine the actual probability based on the z

-score

that you calculate. I'll try and make that a bit more understandable by using an

example.

So let's look at the first one of our statistical tests that you're going to

use. So we're going

to use something called nearest neighbor analysis, sometimes called average

nearest neighbor analysis.

This map here shows California. So the outline here is California in the U.S.

You've got San

Francisco over here. And then Los Angeles is down here. You've got Sierra and

the Avada

Mountains running through along in that direction there, if you know that part

of the world.

And then we've got a number of sample points which are shown as the red dots.

And each

of those represents a location where an ozone level has been measured. This is

about measuring

the air quality. And the first question we might ask ourselves is, are these

sample locations

randomly located from each other? Okay, now you can look at that map and I think

you could

probably say, well, they're probably not random. They're in some way, they're

clustered. So

what the nearest neighbor analysis does, it measures the distance of each sample

location

to its nearest neighbor and then compares the observed distances with that

expected

from a random spatial pattern. This particular statistic doesn't use any

attribute value.

So it doesn't use the concentration of the ozone or any other measured variable

at those

sample locations. It simply works on their spatial distribution of the sampling

points.

So you get a ratio of mean observed distances divided by mean random distances.

And then

you can interpret that value, that ratio. If it's less than one, then it shows

that

the data are clustered. If it equals one, then they tend to be random. And then

if it's

greater than one, that means they're highly dispersed. Okay? So just bear that

in mind.

If you run this analysis on ArcGIS Pro, which is something you'll be doing in

the practical,

this is what you get. You get a summary statistic. You don't get a map. You

don't get a visual

output. You get a statistic. So what we get is our nearest neighbor ratio is 0

.866. So

that's less than one. So we would immediately think our data must be clustered.

From that,

it can calculate a Z score, which is minus 3.3. And it has this blue color next

to it

here. And then we get probability value. So here's our histogram for a random

distribution

of distances between neighbors. And we can see that it's color coded with

significance

level or probability value and our critical Z score. Okay? So it's all nice and

clear.

So blue here, which corresponds to our Z value, if we look at that on our graph,

we're down

in this part of the tail of the distribution here at quite an extreme point. And

we can

see how this is constructed. So here we've got clustered on this side, random in

the

middle, and dispersed on the right-hand side. So depending upon our statistic,

if it was

less than one, greater than one, or around equal to one, it would correspond to

one of

those spatial distributions. And then we get a little summary here. It just says

that given

the Z score of minus 3.3, there's less than a 1% chance that the clustered

pattern could

result by random. So in other words, our data are clustered, but we can be 99%

sure that

they are. So we looked at it, we said, yeah, they're clustered. We carried out

the statistic,

and now we've got a kind of confidence that we can associate with that. Now what

you can

use it for, some common applications that might be of interest. Nearest

neighbors being

used a lot in woodland management, looking at wildlife damage of areas, either

by animals

or wildfires, looking at regrowth patterns. You can look at it, if you remember

you did

a tree survey back in the first year, where you measured the distance between

trees, where

you can use nearest neighbor to tell you whether you're dealing with a random or

a

clustered or dispersed pattern, which you might expect if these trees were

intentionally

planted. They wouldn't necessarily have a random pattern. You can use it for

looking

at ancient animal communities. So in paleoecology, you can see if organisms tend

to cluster together,

so if they show a sort of gregarious behavior where they all want to be located

together

in their environment, or whether they're dispersed. So if they're dispersed,

that might indicate

that there's a shortage of resources, that there's competition between

organisms, and

they're spreading out from each other as far as they can. People have used it in

petrology,

looking at mineral textures, they're looking at the spatial relationship between

the mineral

grains, and that can help give you insights into the way that these minerals

form, the

chemistry and the physics of crystallization. And you can use it for

earthquakes, so clusters

of earthquakes are something you expect to see after a main shock event, so you

can analyze

your earthquake locations to try and have a pinpoint where a main shock

occurred, or

to verify that those shocks are indeed associated with that main shock. So

there's lots of examples

that you can use for a nearest neighbor. Okay, we need to go back and have a

look at spatial

autocorrelation again, because we've already started talking about dispersed and

clustered.

So this is a variation of the slide I showed you last week. So spatial

autocorrelation

relates to Tobler's first law of geography, which if you remember, things which

are closely

spaced together are more similar than things which are further apart. So things

which are

close together are more similar. So really, we're looking at whether things are

dispersed,

random or clustered. If they're dispersed, we say it has negative spatial

autocorrelation.

If they're clustered together, it's positive. One way that people like to try

and remember

this, which never works for me, I always get confused, but you think of

clustered, it's like

with like, things which are similar, like with like. If you think of dispersed,

things that

it's like with unlike, things are located with things that are different from

each other,

like with unlike. So that's one way of thinking about it.

Okay, let's have a look at another statistic then. Now, nearest neighbor

analysis just gave you

information about location. It didn't, you couldn't use the ozone levels

themselves. You could just

look at where the sampling points were on a map and see if they were clustered.

Of course, what

you might be interested in is knowing where are the clusters? Are there clusters

of high ozone

concentration, for example? So are my data clustered? So the question then is do

similar

values cluster together across the whole study area? So there's two types of

Moran's eye statistic.

There's one that's called global and there's one that's called local. We'll look

at both of them.

The global one, again, doesn't give you any kind of visual output, but it gives

you a statistic

and it gives you a probability. So this is the analysis here shows you the

Moran's eye or the

Moran's index value, which we won't consider the actual formula for calculating

that. But based on

that, you can calculate a Z score of 15 with this probability. Now, 15 plus 15

takes us over into

this tail of the distribution and that's indicates that our samples values, our

ozone concentrations

are clustered. So that means we have high values associated with high values and

low values

associated with low values. And again, it gives us a summary here. Z score of

this 15

means there is less than a one percent likelihood that the clustered pattern

could result from

random chance. So our values, our ozone concentrations are clustered together,

but we can't really see where they are clustered. So we need to try another

statistic

and there's a few of these, a couple of these, that will show us where the

clusters are.

Now, local Moran's shows where the clusters occur and identifies any local

outliers.

So it produces a visual output. So here's our data, which have been

changed slightly. So we're still in the same sample locations, but they've been

color-coded

according to this legend here. Okay, so you've got high-high clusters, high-low

outliers,

low-high outliers, and low-low clusters, right? That's quite complicated. So

what does it mean?

Well, a high-high cluster just means that their high values are associated

spatially with other

high values, so they're grouped together. A high-low outlier means that we've

got a high value

amongst a lot of low values. All right, so let's have a look at the blown-up

area of the map here.

So this square here basically just shows the area in the middle here,

at slightly higher scale. And what I've done is I've put on the values of ozone,

which are in parts per million, associated with each one of those sample

locations.

And you can see that we've got generally an area of blue points, which means

that we have a low-low

cluster. So all these values here are all low, and they're all sort of in the

same space.

But in amongst them, we've got this high-low outlier. So we've got a high value,

0.062,

sitting inside our cluster of low values. So it's identified an outlier. And

that, you know,

that's kind of interesting, because there might be a reason why that

concentration is very high.

We would need, you know, further investigation. And then on the other side here

in blue, in dark

blue, we've got a low-high outlier. So what that means, we've got low values,

which are associated with a cluster of high values. So all the ones in red here

are relatively high.

But in amongst them, we've got some particularly low values, which is

highlighted here.

All right, so we can see that there are clusters. There are some other values

around which don't

seem to be associated with those clusters. Okay, so not all of them are part of

the

low or high cluster areas. We've now got a map, then, that's showing us where

the high values

are concentrated, where the low values are, but it's not giving us any kind of

probability

associated with that. And it's using some kind of arbitrary cutoff to define

what is high and what

is low. So to try and get a better or more confident measure of those hot spots,

we use

another statistic, which is called GetisOrgGI star. So this is a form of hotspot

analysis.

So the question we might ask is, where are the unusually high or unusually low

values

located? So where are my highs? Where are my lows in my data set on the map?

And if you run this analysis, you get this output here shown on the right,

where the hotspots shown in red indicate statistically significant clustering of

high

values, and the cold spots in blue are clusters with low values. And it works

with attribute

values, so it works with ozone concentrations. And you get a scaling here, a

color-coded scaling,

with various levels of confidence. So the dark blue points that you can see

indicates a cold spot

with a 99 percent level of confidence. So you can be 99 percent confident that

that little cluster

was not caused by just a random chance alone. Now the last analysis I want to

look at is

with you is kernel density estimation, or KDE, which is slightly more

complicated to think about

because in this analysis, you produce a surface, a density surface. So density

as in, say,

ozone concentration per square kilometer, that kind of density, so population

type density.

And in this analysis, you produce a raster as an output. So it's a surface, it's

a raster.

So you start off with some vector data, which are points on your map, and what

the analysis does,

it converts that into a grid of cells and then associates each cell with some

ozone concentration of a certain probability. And it does that by doing this

thing or

adding what's called kernels at each of the measured point locations. And a

kernel is

is just a circle that's centered on the location. And then it applies some kind

of function

to that kernel. So most commonly it fits a Gaussian distribution at that point,

but there are other types of functions that you can use depending on what kind

of data you have.

So you can think of your original map here, and each one of the points on this

is a sample

location. And then on each one of those points, it puts a kernel, which has a

density function

on it, or probability function, and some limit. So some what we call bandwidth

is the size of the

circle around each point, but you can see you end up with a lot of large

circles, or much larger

than the original data points, and you're producing a surface, a probability

surface at the end of it.

So you can think of it as being lots of Gaussian distribution functions, each

one of these at a

location where you've made a measurement x, all overlapping with each other, and

then you're adding

these together to give you an overall shape to your surface. You don't really

need to know that

detail, but you do need to have an understanding of what it tells you. So let's

look at our ozone

data again. So here's our starting position, here's our sample locations where

each one of

our kernels will be placed, they'll be given some kind of Gaussian distribution

around them,

there will be a new grid set up over this whole surface, and each one of those

cells will be given

some kind of ozone concentration with a known probability based on where the

sample points are.

And what you end up with is what's called a heat map.

So this heat map just is scaled according to, in this case, sample points per

square kilometre.

Okay, so it just shows you that the sample points are kind of grouped in

clusters here, here, and

here. So in some ways it's quite similar to the Gettys Ord, however, this time

you're not given

a probability, it's just a surface that you're creating. So you can do it for

sample points,

so that's just looking at the distribution of sample points themselves, or you

could do it for

ozone concentration or any other attribute that you want to use. So here's the

same analysis,

but this time using ozone concentrations. So our heat map that we produced

that's scaled

in the legend there is in parts per million of ozone per square kilometre.

So you can see that it's giving you a surface over which you can, in areas where

you haven't

got any data, where you can kind of perhaps come up with some estimate of what

the ozone

concentration would be. So it's a little bit like an interpolation surface, like

we were talking

about last week when we were considering crigging. Now one of the things that

matters when it comes to

kernel density estimation is the radius that you choose for your kernels. So

remember the kernels

are placed over each of the sample points and then there's some kind of radius

around them that's used

to obtain the density function. So in this example here, I've chosen 1500

kilometres, which is

huge. So each one of these points has a very large kernel on top of it, and what

that tends to do is

produce a very smoothed out density surface. So you can lose some of the detail.

In this area here, for example, you don't see any evidence of higher values

particularly.

If you choose a kernel radius that's too small, so here I've selected 15

kilometres,

you get this what's known as a salt and pepper effect. You're not seeing much

detail. It's not

very realistic. You're not seeing really much evidence of any concentration of

ozone. But

luckily most GIS systems have what's called an optimised routine or an

optimisation routine that

try and produce the best kernel radius for you to show the right level of

detail,

to make it more realistic. So in this case it's chosen 99 kilometres and you can

see that it's

picking out these hot spots here, here and even a hot spots developing in this

area here. Okay,

right, well there'll be some practice at doing this and you'll be using the data

set from

what we've been talking about today. So you'll be going through some of the

exercises again

and hopefully that will help to reinforce some of the things I've been talking

about.

I'll just finish off then. Homework and resources, well there's a chapter in the

textbook. Have a

look at that. It's probably got more information than you need, so you don't

need to worry about

the formula etc. but have a read through. There's a quiz on the canvas site and

then also have a

look at the, if you're interested or you're still confused, have a look at the

ESRI training on this

topic. It's about 50 minutes it takes to go through it. Okay, yeah, that's

everything then. So

put that back up. Just to remind you again then, I've put the assessment up on

the

canvas site and next week Pete Grinrod will be giving you the lecture. Okay,

thank you very much.
