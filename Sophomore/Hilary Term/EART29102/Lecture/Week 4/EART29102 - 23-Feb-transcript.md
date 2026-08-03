---
title: "EART29102 - 23-Feb-transcript"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 4/EART29102 - 23-Feb-transcript.txt"
type: transcript
---

'EART29102 - 23-Feb', automated transcript
03/08/2026
---

OK, good morning, everyone.

I'll put this up again at the end, assuming there's time.

So we're in week four now, then.

So we're moving on from talking about how we put data in,

how we process it in coordinate systems, and so forth,

and now getting into sort of the meat of the subject,

where we're talking about spatial analysis itself.

So once we've got all the data into our GIS,

what can we do with it to solve particular problems that we have?

So I've listed the content of the lecture there.

We're going to start off with a few introductory things.

And then essentially, I'm going to sort of cover spatial query,

spatial operations, and then a couple of spatial interpolation

methods and some errors associated with those.

So there's a fair amount to cover,

so I won't dwell on anything too long.

So there's a few statements here.

Basically, what we're doing with spatial analysis

is to apply some methods to ask questions

about the different features that are stored in our data

based on their attributes or their geographic locations,

and then look at how those layers interact

with each other spatially.

So we've already sort of kind of introduced

this idea of overlaying data layers,

one on top of another, and how that's a useful approach.

What do we use it for?

Well, we use it for identifying patterns, associations,

evidence of change through time and space.

And essentially, I'm going to sort of break it down

into three, spatial query, spatial operations,

and spatial interpolation.

So I'll talk about these now.

But the graphic on this next slide

kind of encapsulates some of the common types

of spatial analysis that we use.

So you can see along the top there,

we've got network overlay and proximity.

Well, we've already talked about overlay a little bit,

but we'll cover that in a bit more detail.

Proximity, well, we've already done buffers

in one of your practical exercises,

so that's all about proximity.

Network is about finding the least cost path

or least cost surface of an area.

So it's about finding the shortest route,

finding the best way to lay a pipeline

across the landscape, looking at wildlife corridors,

and so forth.

Then the ones at the bottom there,

statistics we're going to talk about mainly next week,

and then 3D we'll come into a later lecture.

So we'll consider that in a few weeks' time.

And then, of course, the temporal change

is something that we're all also interested

along with the spatial connections.

So let's start off with spatial query then.

So spatial query is about selecting

and extracting data or attributes

based on some kind of interactive query.

And then we subdivide this into two types,

query by attribute or query by location.

And really, this only really applies to vector data.

Raster data has a way of doing spatial query,

but that's based on something called map algebra,

which we'll talk about in a few slides' time.

So attribute is about retrieving all the features

with a particular attribute value

from a data layer or a feature class.

Now, feature class in a GIS, if you remember,

is something which has a common geometry.

So it's a sort of layer with either made up of lines,

points, or polygons that share attribute features

and also location.

They're all on the same coordinate system.

Or we could just find them by location.

So in GIS, they tend to use something called

a structured query language, SQL,

which is quite simple in the way that it's written.

It's common amongst lots of databases,

not just geo databases.

I'm not going to talk about spatial join query.

You can probably find that information

about that in the book.

But I am going to talk about attributes and locations.

So best way of showing this is an example.

So let's say we have a question where we would like

to retrieve all the water mains installed before 2010

with a diameter less than 30 centimeters.

So that means our feature layer would be made up

of point data with a geographical location.

It would tell us the diameter of the main, the pipe,

and also when it was installed.

So we can write a SQL statement like the one there,

which I think is fairly intuitive when you read it.

So we've got some layer called W mains,

and we're selecting data from that layer

where we're interested in a date before 2010

and a diameter of less than 30 centimeters.

And then there's another one there

which is slightly more complicated based on location.

So here we're trying to select all the buildings

that intersect within a given park name.

And this is about how the geometries

of the layers intersect with each other.

And ST in that context, that statement there

where it says ST intersects, ST just means spatial type.

And there's lots of spatial type statements

that you can use in SQL language.

Now, if you can't be bothered to learn SQL,

most GISs now allow you to build up clauses yourself

so you don't need to type them in in SQL.

So here's an example, if you look at the top map,

top left there, there's a map of the US

showing major cities in those point data.

And I've just constructed two clauses here.

So for cities where the population is greater than 10,000

and females outnumber males,

extract that data from the attribute table

and display it on the map.

So that's what it's done here by showing these blue points.

So I didn't actually have to write anything.

I could just put the statements in by adding clauses

and it allows you to do a number of different clause types.

If I wanted to write it in SQL

or I wanted to convert my clauses into SQL,

there's an option for doing this here.

So this would be the statement.

Okay, so it's quick and easy.

You can extract the data you're interested in

by combining different attributes or their location.

Okay, other types of spatial query are more complex.

So we've got ones here called dissolve, merge and reclassify.

So dissolve just combines polygons together.

So if they've all got the same attribute,

so they're all colored the same here,

we don't need these different polygon shapes.

We can just merge them all together

to give us a much simpler output.

That's dissolve.

Merge is where you're combining different spatial data sets.

So here we've got data which are overlapping,

but they're stored in different data layers

and they can be merged together.

And then we can do fancy,

other fancy things like reclassify.

So if you look at this map at the top left here,

you can see that it's made up of two different types

of woodland, coniferous and deciduous.

Well, say you wanted to combine those two together

to just call them forest.

And it also has two types of agricultural land,

corn and soybean.

So say you just wanted to merge those two together

or combine them into something called agriculture.

Agriculture.

Well, you can do this by reclassifying

using a reclassified tool within your GIS.

So if you run that tool,

it recodes all the attributes of the polygons

that make up this map

and produces a much simpler version of the map.

However, you can still see that in this version,

you can still see the individual polygon shapes

of the different types of forest,

particularly down in the bottom right-hand corner here,

where you can then use the dissolve tool

to get rid of those boundaries

so that you just have a much simpler map.

And this is the kind of thing you might do, for example,

if you're changing the scale of your map.

So you've got to make it much simpler to look at

if you're going to change the scale by a large amount.

Or if you just simply want to reclassify

some of your polygons.

Okay, another kind of spatial query,

if you like, is overlay analysis,

where we have covered this.

It's the process of stacking multiple data layers

with a common georeferencing system.

So they're all on the same projection,

the same coordinate system.

Stack them on top of each other

so that you can look at the relationships

between the features.

And you did an example of this

when you worked out in your second practical

the number of properties that were at risk of flooding

around the rivers in Carlisle, if you remember that.

And you can use overlay analysis

in either vector or raster data.

So let's just see what options there are.

So this is vector overlay.

So basically you're combining the layers together

to produce some kind of new geometry.

So here we've got point in polygon.

So here we've got a number of point data in this layer

and we've got two polygons marked in this layer.

What we're doing by combining them

is we're counting the number of points

in each of the polygons, okay?

We can do the same things with lines.

So here we've got a river in this layer.

We've got two polygons.

And then in the combined layer,

we've got the two polygons,

each with their own segment of the river inside.

Polygon on polygon can also be done,

but this is more complex, okay?

So here we've got two polygons

and we're kind of bringing them together

to show, to make four new polygons, okay?

Now there's a number of spatial operations

that you can do with polygons

to produce new geometries.

And usually they are sort of classified

into union, intersection, and difference.

So here's an example of each.

So this is intersection.

So we've got two polygon shapes.

We've got a circle and a square.

And the green represents the output layer,

depending on what we're doing.

So here we're looking at the intersection area

of those two shapes.

So the output layer would be this green shaded shape here.

Union is a way of just combining the two shapes together.

So the output would just be a combination of the two shapes.

A symmetrical difference excludes the overlap part.

So the output wouldn't have this part within it.

And then difference is just excluding the whole

of the overlap of the circle on the square here.

So you get the idea.

So you can look at these layers visually,

but you can also create new layers

based on how you combine them together.

And there are tools in a GIS

to allow you to do all of these things.

For raster data, we have a slightly different approach.

So as you remember, rasters are made up of grids

and a number of cells within that grid pattern.

To be able to combine rasters or use overlay,

the grids need to have the same number of cells

and cover the same spatial area.

And there are tools within a GIS

to allow you to reprocess rasters

so that they are, so that they meet those criteria.

Okay, so if your current rasters have different cell sizes,

you can reprocess that data

to get it into another cell size

that allows you to do the map algebra.

It's fairly simple to think about.

So here we've got two layers, two raster layers,

and they're coded with these numbers.

Doesn't really matter what they represent,

but these are the values of each cell.

And we can do a certain number of operations on these.

So we could simply combine them by adding them.

So here, all we're doing is adding

the corresponding cell values together.

So two plus two is five, two plus three is five,

zero plus five is five, and so on.

You get the idea?

Or you can do subtraction.

So you can subtract layer one from, sorry,

layer two from layer one.

So three minus two is one,

two minus three is minus one, and so forth.

And then you can do things like the maximum value

from each of the layers or the minimum,

or you can calculate an average.

You can do conditional operations as well.

So there's a couple of examples here.

So this says if layer one is greater than two

and layer two is greater than one,

then either put a one or a zero, a yes or a no,

true or false, in the cell.

So for the first one, for example,

layer one is greater than two.

Well, if we look at this cell here, the value is three.

Layer two is greater than one, and that's true

because the value here is two.

So that would be a one, because it's true.

And for the next cell, layer one is greater than two.

Well, that's false, and layer two is greater than one.

That's true, but we have to meet both of those conditions.

So that means we put a zero in there.

And generally, raster data are much easier

to combine in this way.

It's much more efficient to do that

than it is to sort of do some of the overlay operations

that we just described for vector data.

And there's a large number

of different relationships that you can use.

I don't expect you to remember these,

but just really an awareness that when you're combining

raster layers using map algebra,

you can use lots of different ways of doing that,

different mathematical functions.

Okay, let's move on a little bit then

to some spatial operations.

Geometric and distant measurement is something

I did mention in passing in the first lecture.

So we can do, we can compute things

like the lengths of lines, areas of polygons,

perimeters and shapes, which of course

is all very useful for landscape metrics.

But these geometric properties are not encoded

into the spatial data input.

They're actually calculated for you.

You have to ask it to calculate these numbers for you.

They're not stored anywhere.

And usually you can do this from the attribute table.

So here's an attribute table and you'll see

there's an option here called calculate geometry,

which allows you to do those things.

For rasters, it's much the same thing.

So you're just counting the number of cells

for a line here, vertical or horizontal line,

and then just multiplying that by the cell side length.

Slightly more complicated for a diagonal,

but you just have to find that diagonal distance

of the cell here and allows you to work out the length.

And the area of a polygon where you just count

the number of cells inside the polygon,

you can work out the area.

The perimeter, one would naturally count

the number of cells on the perimeter,

but there is another way of doing it,

which is the way that's shown here,

and which is the way that a GIS would do it.

Basically just counting the number of internal edges

within the polygon.

So you'd start off by a row, you'd say,

well, there's one edge here, and then the next row,

well, that's two, that's three, that's four,

five, six, seven, eight, and you just count them

all the way down, and then you do the columns,

and then you go, well, there's one there,

there's another one there, that's two, three, four,

five, six, seven, eight.

If you do that, I think you end up

with a number that's 30, and because each cell

is adding one of its edges, so there's contribution

of one edge from this cell and one edge from that cell,

you have to multiply it by two.

Doesn't really matter, you don't need to,

you wouldn't be asked to do that kind of thing,

so don't worry about learning it too much,

just trying to explain it.

Okay, we're gonna talk a little bit about networks

and neighborhoods now.

Buffers is already something you know about

because you used a buffer previously in your practical.

You can make a buffer around a point, a line,

or a polygon of any distance you like.

Usually, we tend to dissolve the boundaries

between the different buffers to make them continuous.

Okay, so it's shown here.

And this is just an example, so this is just showing

a 500-meter buffer around some roads.

Okay, you get the general idea,

you've used that tool in your practical.

Now, cost-distance surfaces or network analysis

is something that GIS is used for quite a lot.

And basically, what it's saying is it's measuring

how costly or expensive it is to travel over a surface.

So it kind of thinks about how you would move

or how something would move across the landscape.

So we tend to think of, well, yeah, if I go from A to B,

I can draw a straight line and I'll get there.

And that's what we call the Euclidean distance.

But obviously, that might involve a lot of cost.

So if you imagine there's a big mountain in the way,

then I have to go up and down the mountain.

There's a huge cost there in time, energy, et cetera,

risk, perhaps.

So it might be easier if I go around the mountain

at the bottom and I don't try and go over the top of it.

Okay, and that's kind of logical

and we're used to thinking about that.

But it turns out you can measure costs

in lots of different ways.

So you can think of it in terms of the topography.

It could also be how much time it takes,

how much it costs, how much energy you use.

But there's lots of other things

that you could bring into it as well.

That's what makes it so useful.

So what do you get if you run this cost-distance surface analysis?

Well, you get a cost surface which is shown here.

So here we've got some kind of landscape.

And it's color-coded as to high-cost and low-cost areas.

And mapped through this is a least-cost path.

So it's the most efficient way that you can travel

through the landscape based on the criteria that you've set.

It's useful for lots of reasons.

So people use it for wildlife corridors in areas

where they've got fragmented habitat and you've got things

that want to go to a neighboring habitat.

They have to find their way through the landscape.

As I say, it's useful for sort of planning out where you're going

to put a pipeline, where you're going to build a road.

It's used in rescue operations.

So people use this tool to find the best place,

the best route to recover people and so forth.

I thought it would be useful just to show one example.

So this is a study that was done in 2019

about hedgehog movements in urban landscapes.

So the study area was in Rennes, which is in northern France.

So that's shown on this little insect map here.

And what the people did was they worked out a least-cost surface,

which they called resistance,

which is shown in the gray scale here,

where the darker gray areas are high-cost or high-resistance

and the lighter gray areas are lower.

And then they also mapped out some least-cost paths shown

by this network of green lines here.

And they braced the criteria on things that would either attract

or act as a barrier for hedgehogs in a city.

So, you know, things like roads would be a problem for hedgehogs,

buildings, railway lines, waterways, things like that.

Hedgehogs wouldn't really want to go anywhere near those

if they could find another way.

And so then what they did was that after they mapped out,

they took 30 hedgehogs and released them at different points

based on their modeling.

So they put them into highly connecting networks,

which is shown by the white dots,

and something which they called unconnected context,

which was shown by the black dots there.

So really, the green, the white dots here represent places

where you get lots of connections between these least-cost pathways.

And they're much more sort of favorable for hedgehogs in those areas.

So they released them, radio-tracked them, and see what happens.

And they found the ones which were in the highly connected areas

traveled further, faster than the ones which were in the least connected areas.

So you can think, well, that's interesting, but, you know, okay,

so the hedgehogs are basically following what I'm modeling.

But if you were a sort of, you know, town planner

and you were worried about hedgehogs getting run over and so forth,

you would, that kind of information would be useful for you

because you might not want to interrupt some of those pathways

which the hedgehogs were following.

So that's a kind of real-world example.

So let's move on now to spatial interpolation.

So interpolation is about finding a value in a place

where you have some surrounding information,

but you don't know what the value is, okay?

So let's look at this little pattern here.

Let's imagine each one of these dots is a meteorological station

that's recording precipitation, which is scaled on this color band here.

And let's say I want to go to this point here, which is a known location,

but I don't have any precipitation data for that actual point.

So what we're trying to do is interpolate what the precipitation should be

at that point by looking at the precipitation values

in the neighboring meteorological stations, okay?

So that's what we mean by interpolation.

And it's spatial because obviously there's a spatial dimension to it.

So we start off an interpolation having a set of points with known values.

And what we do is we create a continuous surface, such as the one shown here,

okay?

So we're not interested necessarily in a single point,

but we want to see how the precipitation varies across that surface based

on the data that we have from each of those meteorological stations.

So the data we collect are often made at discrete observational points, okay?

So we go somewhere, we measure something at a specific location,

and then we want to try and interpolate beyond that single location.

There are lots of ways of doing this.

If you read the chapter in the book, it covers some of them.

The two that I'm going to focus on is called inverse distance weights,

or IDW, and krigging.

And they're different in that IDW is what we call deterministic.

So it just estimates a value, okay?

Just estimates a single value.

Whereas krigging is something we call stochastic or geostatistical,

which means it estimates a value and an error.

So it's got some element of randomness built into the method

that allows us to work out the error.

So that makes it very useful, makes it particularly useful.

But you can see that the two methods I used here, IDW and krigging,

if you compare them, they look fairly similar.

So you sometimes, depending on your application,

it doesn't really matter which one you use.

So let's look at inverse distance weights first.

And I don't want to get too technical,

but essentially what you're doing with inverse distance weights,

you're saying, well, I want to know the value

of some environmental variable here at this point.

And I've got information from these points here,

which have values of 10 and 12, which are located some distance,

different distances from my point of interest.

And all it does, it simply uses that distance

as a way of obtaining the average.

So it weights the average, or the interpolated value, by the distance.

So the idea behind it is that it makes an assumption

that things that are closer together will be more similar.

Things that are further apart are likely to be more different.

And it uses that distance as a way of weighting the data.

So in the equation here, and you don't need to remember any

of these equations, but you can see

that there's a distance term, di, here, which is the distance

of the points from where you're interested.

And it's inverse, it's got an inverse relationship,

both in the numerator and in the denominator.

And then there's another control on the distance,

which is this thing, a power term, P. Okay?

So that also affects the influence of more distant points.

Okay, so let's just recap.

So it explicitly assumes that things close to one another are more

alike than those further apart.

And this is known as Tobler's first law of geography.

And it's an important assumption.

And the other thing is that as the value of P,

this power term here, increases, the importance or the weights

for distance points decrease rapidly.

So if the P value is high, so it has a value of, say, five,

then only the immediate surrounding points will

influence the prediction.

I mentioned that Tobler's first law is really critical in a lot

of interpolation methods.

So it's worth just expanding on that slightly.

We have this thing called spatial autocorrelation.

It's a very fancy sounding term.

But it's just a way of measuring this Tobler's first law

of geography.

So Tobler's first law, everything is related

to everything else.

But near things are more related than distant things.

So if me and you are standing 10 meters apart,

we experience very similar weather to each other.

It could be raining.

It could be sunny.

If I'm one kilometer away from somebody else,

we could have quite different meteorological conditions

or weather conditions.

That's the general idea.

How we think about it, well, there's a little diagram here.

So spatial autocorrelation can either be positive or negative.

If it's positive, it means that similar values

are clustered together.

So here, all our similar values are closely related spatially

to each other.

And that's positive.

On the other end, dissimilar values cluster together.

So we have fully dispersed.

So it's more than we would expect by chance.

They're more different from each other than we expect by chance.

So it's not random.

But that's negative spatial correlation.

In between here, where spatial autocorrelation

has a value of zero is the random case.

Anyway, we'll talk a lot about spatial autocorrelation

next week as well.

So let's look at some examples of inverse distance weight

interpolation.

So here's a couple of maps showing annual rainfall over an area.

And the difference between them is the value of this power term P.

So if that has a value of one, then it smooths out the surface.

So globally, you get this rather smooth surface develop.

If you increase that to two, you can

see how the influence of close values becomes much stronger.

And you get this kind of bullseye pattern, which

doesn't look very realistic.

And that's one of the problems with this method.

Very easy to do.

Computationally, it's very efficient.

But knowing what this value of P should be is kind of hard.

So what value should I use for my power in the equation?

It's not a good method for landscape studies.

So if you're looking at topographic profiles

and trying to interpolate elevation data,

and you've got a very large amount of relief,

you've got a lot of ridges, you've got a lot of mountains,

you've got a lot of valleys, it doesn't work very well

in those situations.

So there are some limitations.

And one of the other limitations,

of course, is that this idea of spatial autocorrelation

is assumed.

It's not actually tested.

And that's an important underlying assumption.

So in that case, we tend to use this method called crigging.

It's an unusual name.

It's named after a South African mining engineer, Danny

Crigg, who first came up with the idea.

And as I mentioned, one of the important differences

between inverse distance weights and crigging

is that you get a value and an error

or a probability associated with that interpolation.

Now, the ideas behind it are pretty straightforward,

but mathematically, it's quite complicated.

So we'll have a look at this idea about a semi-variogram.

OK.

Yeah, we'll talk about that next.

OK, so let's imagine that we've got a point here,

shown by this red point, where we have a location where

we don't have any data.

And that's surrounded by other locations, which are in black,

where we have measurements.

One of the things that we can do is measure the distance

from our point of interest to each of the surrounding points.

So that's a bit like the inverse distance weight.

So we can work out those distances.

And the other thing we can do is to calculate

the variance between the value of our points,

between our points as well.

So we can work out a variance.

And then if we take that value and multiply it by a half,

then we end up with something called a semi-variogram.

So we can measure the distances between these known values here.

And because we know what the values are

and we know what the distance is, we can work out

the distance and the variance.

So this part of the formula here is just a formula for variance.

So it's just the value at some point i

minus the value of some point j squared divided by n.

That's your variance.

Multiply it by a half.

Gives you your semi-variance at some distance

that you've measured between these two points.

So once you've got that information,

what can you do with it?

Well, you can plot the distance between the points

on the x-axis here and their semi-variance on the y-axis.

OK, so you're measuring all the variances, all the distances

between a whole range of points.

And then you get something that looks like this.

And then what you try and do is fit

some kind of mathematical model to those points

to achieve something like this.

OK, so let's have a look at this.

So why is it going up like this with distance?

Would you remember our spatial autocorrelation,

or Tobler's law, things which are closer together

are more similar than things that are further away?

Well, these points here are all quite close.

They've all got quite short distances between them.

So we'd expect the variance to be much lower between them.

The variance should be much lower

because they're closer together in space.

So here's our distance measure, which

would be in kilometers, meters.

But as we increase that distance between points,

they become less similar to each other.

So the variance increases.

And that's why we see this increasing semi-variance

as the distance increases until we reach a point

where there's no change in the variance.

So that sort of distance, those points

aren't very similar at all.

And we define three things from this graph.

We define this thing called a nugget.

So this is where the curve comes down and intersects the y-axis.

Now, that's at a distance of 0 separation.

So two things that are at the same point

should have the same value, shouldn't they?

Shouldn't have any variance, any difference between them.

But there is usually, doesn't usually come down to 0.

There's usually some kind of offset

from 0, which is related either to some error

in the measurement.

So say you're measuring temperatures

and there's an error of plus or minus 1 degree.

That will make them slightly different.

Or it could be what they call microscale variability,

so things at very short distances

that change quite rapidly and can be quite variable.

And we call this point here the nugget.

Got some strange names.

It's all to do with mining.

Then there's two other things.

There's this thing called the sill.

So this is the maximum variance in our data.

So the curve folds over here and goes flat.

And this is known as the sill, this value here.

And then the point where it does that,

the distance at which the sill appears

is known as the range.

And Kriging uses that nugget sill and range

to work out the weighting of the points.

So it's more sophisticated than inverse distance weights,

which just depend upon the distance.

There's more taken into account during Kriging.

Now I just put the slide up to remind me

to say that there's lots of different ways of Kriging.

You're gonna be doing a practical this week

where you'll do some ordinary Kriging.

And ordinary Kriging is usually pretty good for most things,

but there are other methods of Kriging

which we won't go into.

And then in the last couple of minutes,

I just wanna show a couple of examples

So here's the practical you'll be doing this week.

These are some meteorological stations covering Africa.

Each of those is measuring temperatures.

So we have temperatures for a given month of the year

from each one of those stations.

And what we are going to use Kriging for

is to produce this interpolation map.

So this is showing temperature variations across Africa

where the color scale, warmer colors

represent warmer temperatures.

And then with Kriging, you also get an error map as well

or an error surface.

So where you have higher errors, you get darker colors.

And you can see that where you get higher errors

is generally where you have less data.

So in this area here, we have less meteorological stations.

So it's not kind of makes sense

that we should have a higher error associated

with our estimated value in that area.

Here's the semi-variogram that's produced from that data.

You can see our nugget, our sill running along here,

and then this will be the range somewhere out here.

And then what we can do is we can use

our interpolated surface to predict

what the temperature should be

at each one of these stations.

So we can obtain a predicted value

for each one of these meteorological stations.

And that allows us to plot predicted value

against measured value.

So it gives us a kind of idea

of how well our interpolation is working.

We would expect to see a good correlation,

a one-to-one line between the measured temperature

and the predicted temperature at each one of those stations.

And there's various ways that we can check

how good our Kriging surface is.

So we're given a summary table of information.

It tells us how many meteorological stations, 704.

It tells us what the mean value is.

So that's basically the average difference

between the known and predicted value.

So we want to make this as close to zero as possible.

So this is minus 0.06 degrees.

Root mean square is something we did last week.

This should be, it's currently 2.2 degrees,

which should be as small or as close to zero as possible.

And then we have other things that we can use

to assess how well our interpolation works.

Couple of real examples just to finish off.

So this is an environmental one looking at plastic pollution,

well, marine plastic pollution in Hong Kong

and neighboring region.

So here's Hong Kong Island here,

mainland China up here.

And here's some results of a Kriging interpolation

showing the distribution

where most of the marine plastic pollution is.

Hong Kong's got a serious problem with plastic pollution.

And here's the error surface.

So it's quite interesting because, you know,

it allows you to focus on places where obviously

most of the marine plastic pollution is occurring,

but also to look at areas where you might have fairly low

or, you know, places which you don't know.

For example, here we've got relatively low error measurements

but we don't have very much indication

of a pollution in that area.

So why is that?

So basically allows us to look for places

where we have a higher uncertainty

and then perhaps take more measurements in those areas.

Geological example here, this is the East African Rift

which is a classic area of continental spreading.

And this is, on this map here,

we have been shown in these little gray symbols

are all the gravity measurements

that have been made in this area.

And then this is a gravity, a kind of gravity map

that's been made from those individual point data

using Kriging and the brighter colors here,

the reds show areas of thinner crust

and the blues and the greens show areas of thicker crust.

So you can kind of make a crustal thickness map

based on those individual point data.

Okay, there are some errors.

So there are some errors in the interpolation methods.

So the actual model Kriging uses

will introduce some errors

and we can assess those using some

of the statistical parameters I've already mentioned.

There's bound to be some uncertainty

in the data themselves.

So either the actual measurements

or how they're distributed.

It becomes a problem with edge effects.

So with the boundaries of your study area

where you don't have sample points beyond that,

you can get distortions in your interpolation surface.

And then if you've got any weird data,

if you've got any outliers,

that can have a big effect

on your Kriging predictions as well.

Okay, so have a look at the relevant chapter

in the textbook.

Look at the quiz, have a go at the quiz,

check your understanding,

and then have a look at the ESRI training

on spatial analysis.

Take about an hour to do that.

Okay, I will, this week,

I will put up the assessment for you

so you can have a look at that.

It's not due in until week 11 or something.

So you've got plenty of time.

So that'll be all for this week.

Thank you.
