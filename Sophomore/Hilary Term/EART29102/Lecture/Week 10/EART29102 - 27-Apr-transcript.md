---
title: "EART29102 - 27-Apr-transcript"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 10/EART29102 - 27-Apr-transcript.txt"
type: transcript
---

'EART29102 - 27-Apr', automated transcript
03/08/2026
---

OK, thanks for coming.

Good morning.

So I'll put this up at the end.

If I forget, somebody will remind me.

But just to say at the outset, this is the last meeting

that we have, so the last lecture.

Next Monday is bank holiday, so we don't have any classes

anyway.

And also a reminder that last Friday

was the last practical session, so there

won't be a practical either this week or next week.

OK, so I guess what I'm saying is the course finishes today.

All right, so there won't be any other formal classes.

The other thing to mention, I know

many of you have already handed in your assessment,

but just to remind you that that needs to be handed in.

I think it's 2 o'clock on the 30th,

which is Thursday, is that right?

So just to remind you to complete that and submit

the work through Canvas.

So what I want to really do today,

I don't want to go into too much detail about any one

particular topic, but I thought it

would be useful just to review all the topics that we've

covered in the course, highlight one or two

things, and then towards the end,

I'll talk about the format of the exam and other things

like that, and give you a chance to ask any questions

with time available at the end if you have any.

OK, so as I say, I'll put this up again.

So if you haven't caught the SEATS code yet,

you'll have another chance.

So just to kick off then, I'm not

going to go through in any detail,

but thinking back from the first lecture,

these were stated as the aims of the course,

so you can decide for yourselves how well you think we met those.

But essentially, sort of one and two there, and possibly part

of three, were sort of around the lectures,

and then four and five were more to do with the practical classes.

So as I say, I'm not going to go through them.

You can read them for yourself.

And the way we divided up the course

was into theory and practical, and then these

were the breakdown of the main topics

that we covered in the theory.

Again, I'm not going to go into any kind of detail,

but just to remind you of what we did cover.

And you had a lecture last week with Rufus,

where you did the sort of 3D visualization stuff.

And then the practical classes, I guess

what we were trying to achieve with those is sort of listed here.

So really getting you started with ArcGIS Pro.

If you know ArcGIS, then you can use other GIS systems,

QGIS, for example.

So it's kind of useful transferable skill.

Talk to you a little bit about digital map creation

and some cartographic principles, particularly

when you come to hand in your assessment.

You'll hopefully follow some of those.

Satellite imagery, you did a practical on that.

And then there were some sort of examples

on air pollution, wind turbines, flood hazards,

solar mapping, et cetera, and a little bit

on geological maps and renewable resources.

So a fairly wide range of topics that we

tried to integrate into the practicals.

So let's just recap on some of the main things

that we've covered in the lectures.

So one of the key things really is knowing what a GIS is.

So you really need to know that.

So you can think of it as really just a computerized system

that processes and manages spatial data.

So it handles maps and images and other types

of spatial data.

And then there was the functional components

of the GIS, which I showed on this diagram.

Essentially, you've got some means

of importing spatial data.

And that could be directly through a user,

or it could be using some other database that's linked to it,

or even an external program.

And then that spatial data is then stored and managed

in a database, geodatabase, from which you can extract the data

and manipulate it, analyze it, and then

output it in whatever form you need.

We considered these two concept views of geographical space,

so the object view and the field view.

And if you recall, object view is

a way of thinking about things being discrete entities.

So they have definite boundaries around them.

And very often, the vector data structure,

which we'll mention in a minute, is very much

related to the object view.

So we're talking about point, line, polygon type things.

And there's an example there showing a map of trees

as discrete objects.

So you can think of those as being in the object view.

And then the other concept was the field view,

where you have a continuous surface.

So everywhere on your map has some kind

of value that's related to, in this case, tree height.

And that's very much related to the raster data structure.

So object view and field view, pretty easy things

to understand, but fairly fundamental to the way

that the GIS stores data, and also

what you can do in the way of analysis.

And then to the data structures, so this

is just a set of rules that the GIS

has to follow in order to deal with this kind of data.

So vector data then, the example, the illustration

shown here.

So you have discrete features.

They have boundaries around them.

And they're represented as points, lines, or polygons.

So these are the kind of features

that we can represent using that data structure.

And there's certain advantages and disadvantages

with vector data.

And I've listed some of them there.

I think I've covered most of those things.

So one of the ones there, topological relationships.

Topology is just the spatial relationship between objects.

So maintaining their relative position in a spatial context.

So that if you're zooming in and out of a map,

they don't suddenly all move all over the place

relative to each other.

Their size and their position are fixed

so that they maintain their position and scale size.

I guess one of the main disadvantages of vector data

is that some of the spatial analysis procedures

are quite complex and process intensive

relative to raster data.

So although they give us an output that

looks very familiar in the way of the kind of maps

that we're used to seeing and quite realistic,

it does have some disadvantages in the complexity

of the data structure, which sort of slows down

any analysis procedures you might want to use.

And they're also not very good for remotely sensed data.

So image data, they don't work very well.

Raster is much better image data.

So moving on to raster data structures then.

Here we have our raster representation

as a grid of cells where the value

within each of the cells represents the feature

that we're interested in.

So your roads, houses, land use is shown

by the different cell patterns or values, colors,

whichever way you express it.

As much simpler data structure,

which means it's actually quite good at processing,

so you can carry out spatial operations analysis

much more easily.

The output's not quite so pleasing as vector data

and it does have some difficulties

representing topological relationships.

So you don't always maintain those

as you with this data structure.

It depends upon the number of cells

that represent a particular area of the surface of the earth.

So it depends on the spatial resolution to some extent.

Okay, so you should be aware of those

and know some of their advantages and disadvantages.

And as I mentioned, the particular data structure

kind of relates to how the data is entered into the GIS.

So typical vector data capture methods are shown

and raster data capture methods are shown there.

However, we should bear in mind

that there are procedures within the GIS

to manipulate the data and transform them

from one structure to another.

So it doesn't mean that if we collect the data

in one kind of representation,

we can't then transform that into the other

and do other kinds of processing.

Okay, so we have these procedures called rasterization

and vectorization that allow us to do that.

Moving on to map projections and coordinate systems.

So really we've got to have some rules

and some framework that allows us to identify

where things are on the surface of the earth.

And we usually do that using coordinates.

And in a general sense,

we locate things on the earth surface

using something called georeferences.

And if you remember back to one of your practicals,

one of the things you had to do with a digital image

was you had to georeference it

in order to allow the GIS to know exactly

where on the earth surface the digital image came from.

So the general term is georeferencing.

And we have to have some kind of mathematical model

of the earth in order to do this.

And we usually model it as a kind of sphere.

It's slightly flattened at the poles.

So sometimes it's called an oblate sphere or spheroid.

And the model that represents the whole of the earth,

there are a number of these that we had a table listing them,

but the one that most people use now,

the most modern one is WGS 84.

And often this mathematical model is enhanced

using a equipotential surface

of the earth's gravitational field at mean sea level.

So it becomes the geoid it's often referred to.

So WGS 84 is the mathematical model

of the shape of the earth.

And then it's slightly adjusted

according to the gravitational field

because of the way the earth's surface

reflects its interior composition, if you like.

And then we have a local datum

which takes account of regional variations.

So on top of that, we also have another model

which just accommodates the particular area on earth

that you're interested in.

So if it's North America, the North America datum 27,

is used for North America.

For the Ordnance Survey in the UK, we use OSGB 36.

So they have a variety.

There's a lot of these that you can use.

And then really we think of coordinates

as either being on a spherical surface.

So geographical coordinates of latitude and longitude

are the position of something on the surface of the earth.

And that's given in degrees.

Or we have a projected coordinate system.

So essentially we're going from a spherical surface

to a flat surface, a two-dimensional surface,

which is of course very advantageous.

You don't wanna carry a big globe around with you

and try and look at where things are.

You wanna carry a nice flat map

or look at it on a computer screen.

And that's what a projected coordinate system

allows us to do.

And there's some examples of those.

UTM, British National Grid, are different grid systems.

For positioning on the surface of the earth,

the Global Navigation Satellite System is fundamental, GNSS.

And this really just consists of a constellation

of satellites that are continually orbiting the earth.

If we're going to have global coverage,

it's thought that a constellation requires

somewhere between about 20 and 30 satellites.

And there are a number of these global systems,

depending on which country you belong to,

although most of them are accessible to everyone.

So you should be able to access the satellites

from any of the parent companies.

So it gives you the position, the latitude,

longitude, and some kind of elevation data.

And if you need all of those,

if you need your X, Y, and Z value,

then you need four visible satellites in the sky to do that.

And of course, handheld GNSS receivers,

such as your mobile phone,

allow you to know where you are

at any time on the earth's surface.

So once we've got our data in the right sort of data structure

and we know where we are on the surface of the earth,

then we can begin to analyze or model it

within our GIS system.

And we covered a couple of lectures

on spatial analysis, at least two.

And we tended to, they tend to get divided

into spatial operations and spatial statistics.

Spatial operations, you can think of it

as being related to the geometry of,

so the size, the position,

yeah, size, position,

and something else I've forgotten about.

The size, position, are the things that allow you,

you're interrogating your data using spatial operations

based on where things are, how large they are.

Whereas statistical analysis is looking more at modeling

and analyzing spatial patterns.

So how are the different objects related

rather than on their geometry?

That makes sense.

But there's a kind of overlap between them.

And some of the ones that we considered are listed here.

And I'm not gonna go into any kind of detail

about any of them.

I think we covered that quite well in the lectures.

But one of the, I guess the key features is that

spatial analysis not only involves location,

but also things like changes over time.

So the time aspect is quite an important thing to consider,

particularly in our branch of science

where we're looking for things which,

we're looking for changes over time.

So some of the methods in general terms,

spatial query, spatial operations,

and spatial interpolation

are some of the ones that we looked at.

Not really gonna talk about that much,

but I will say a little bit about spatial interpolation

given that we spent a bit of time on this.

We looked at two main methods,

inverse distant weight and crigging.

And if you remember, what you're trying to do

is you're trying to infer what the value of some property is

at an unknown location

based on the data that we have at known locations.

So in the example that's shown here on the map,

we have a number of points

which represent stations where rainfall has been collected,

rainfall totals.

So we have precipitation measurements at those points.

And then what we're doing with our interpolation is

interpolating what values are at locations

outside of those points, away from those points.

So you end up with a surface

showing the variation in precipitation.

So it's a prediction surface, if you like.

And the two that we looked at,

the inverse distant weight one

is called deterministic

because it just gives you a value

and that value you can create a surface from,

whereas the crigging method is geostatistical

in that it gives you an interpolated value

and a probability.

So it gives you some idea of what the error

might be associated with that interpolated value.

So in many ways, the inverse distant weight

is quick and easy, the crigging's more involved

in terms of the processing

and understanding that you need to have.

But you can see that in many situations,

such as the map shown there,

the results of both of them look quite similar,

which is what you would hope to see.

Both of them are based on

Tobler's first law of geography,

which basically means that

everything is related to everything else,

but near things are more related than distant things.

So if you have things which are close together,

they're probably going to be more related to each other

than if you're comparing things a long way from each other.

And you can imagine that with precipitation,

if you've got an area of high precipitation,

then you're trying to compare that with something

that's a long distance away,

probably not that closely related,

because they're going to be quite different from each other.

So Tobler's law of, first law of geography,

it's very, sounds very simple, but it's very fundamental.

And we also,

we also call it spatial autocorrelation.

So it's a measure of the similarity

between nearby observations.

And we can carry out a statistical test

to determine whether things are random

or whether they're clustered or dispersed.

And if you remember those three little diagrams

that are sort of showing the results that you might expect.

So if you've got negative spatial autocorrelation,

it means things are either very similar

or they're clustered together.

If you've got things which are as far apart

from each other as possible,

then they are completely dispersed

and that's positive spatial autocorrelation.

Or if there's no relationship between them,

then, and the pattern is completely random,

then spatial correlation has a value of zero in that case.

Moving on to spatial statistics then,

we looked, I think, mainly at these four statistics.

We used nearest neighbor analysis

to measure the amount of spatial autocorrelation

between using locations.

So it didn't provide a graphical output,

it just gave us a number between plus one and minus one,

which allowed us to assess the spatial autocorrelation

between locations to see if they're random,

dispersed or clustered.

We use Moran's eye as a measure

of spatial autocorrelation,

using either feature values and their locations.

So slightly more one step further than nearest neighbor

in that you can look at the feature values themselves.

Again, it returns a single statistic,

but you can use it to identify clusters and outliers,

particularly the local Moran's statistic.

Then the other two, Gettysord Gi star

was a form of hotspot analysis.

So here it's identifying statistically significant clusters

of high values, which we call hotspots,

and low values, which we call cold spots.

And then kernel density estimation produces a heat map.

So it's kind of a surface that it generates,

showing how concentrations, in this case,

ozone in the map shown there,

how they may change over an area.

You had a lecture on remote sensing by Pete,

if you remember Pete Grinrod.

And remote sensing really is just methods

of collecting environmental mental data from a distance.

So you don't have any sort of direct measurement

in contact with whatever it is you're interested in.

And it really measures the wavelength and the magnitude

of the electromagnetic flux that's either reflected

or emitted from the objects.

And generally we break it down into two types.

We have passive sensors,

which are largely measuring reflected sunlight

at different wavelengths,

or we have active sensors,

which are generating a signal,

which is then directed towards some object,

and then we measure whatever is returned.

And there are examples of those.

So you land certain sentinel satellites,

and then things like LIDAR, radar, and sonar

fall into the active sensor bracket.

Looking at the passive sensing,

as I said, it's largely measuring different wavelengths

of reflected sunlight from the Earth's surface.

And this just shows a graph of the amount of reflectance

in percent against the wavelength.

And I've marked on here the area of the visible spectrum.

So sort of blue down at the low wavelength

towards green in the middle,

and then red at this end, the higher end here.

And then beyond the visible in the infrared is shown here.

And then for different materials,

you've got water, vegetation, and soils,

showing how they reflect at those different wavelengths.

So for example, vegetation here

absorbs quite well in the blue,

and in the red here, but reflects in the green area.

So you get more reflectance.

That's why things appear green,

but reflects strongly in the near-infrared area.

And it has different reflecting properties

than, for example, soils and water.

So by using different wavelength bands,

we can infer information about various things,

but vegetation health in particular.

So the kind of images that are collected

by Landsat and Sentinel-2,

they have the sort of characteristic visible image

at different wavelengths, sorry.

So we've got multispectral images collected

at different wavelengths here.

So blue, green, red, near-infrared, middle-infrared,

thermal, and another one, middle-infrared here as well.

I don't know why it's not distinguished,

but you can see that you get different light

and dark areas shown on the image.

And we can give those bands different names,

band one, band two, band three, et cetera.

The width of each band in terms of its wavelength,

so the wavelength that it includes

is known as the spectral resolution.

Each of these images is collected in raster format.

So it's a grid of cells,

and I don't know why it keeps doing that, sorry.

Hmm.

A grid of cells which has a digital number

associated with it.

And because this is stored in computers,

it has to be stored in a binary format.

So those numbers can range from whatever the resolution is.

So in this example here,

we might have eight-bit resolution,

which means we can have values in those cells

ranging from zero to 255.

And if you remember, the high values

are sort of at the white end of the gray scale,

and the low numbers are at the black end of the gray scale.

And we call this the radiometric resolution.

So you can have eight-bit, 12-bit, 24-bit.

12-bit resolution allows you to have something like

about 16.8 million shades of color,

which is perfectly fine for the human eye.

But you can go to higher resolutions.

So we talk about this resolution, this value here,

whichever scale we're using.

We call that the pixel depth,

or the radiometric resolution,

so the number of values that any particular cell can have.

And in this case, it can have any value between zero and 255.

And then the other piece of information that we have

is pixel size.

So how large an area does each one of our cells represent

on the surface of the Earth?

So obviously, if each cell covers a small area,

then we've got relatively high resolution

if each cell covers a very large area of the Earth,

then we have a low resolution,

and we call this spatial resolution.

And I mentioned that we have all these different bands

representing our spectral resolution.

So here's a table showing band numbers.

Some of them have names.

So NIR on there is near-infrared.

SWIR is short-wave infrared.

The central wavelength of each of those bands

is shown in one of the columns there.

And then the spatial resolution,

so the area that each of our cells covers,

is shown in meters.

And I've just added a column at the end there,

just basically indicating what each of those bands

or combinations of bands are useful for.

So some of them are useful for atmospheric science,

looking for aerosols or cloud types.

Some of them are looking at vegetation health.

You can use them in agriculture and forestry.

Or you can look at burn areas, moisture contents.

You can separate rocks from snow.

You know, there's lots of things you can do with it,

as well as getting these three bands here,

two, three, and four, blue, green, and red,

which give our nice color images

that we're most familiar with.

Okay, next thing I want to talk about then

is terrain analysis, just to remind you

that we can represent surfaces,

elevation data in a number of different forms.

So we can use lidar points, contours, rasters,

and triangulated irregular networks, or TINs,

to represent our surface.

And I talked a little bit about comparing rasters and TINs

and the advantages and disadvantages of each of those

during the lecture.

Based on the elevation data that we have,

we can derive some primary terrain attributes.

So these are things like elevation, slope, aspect,

plan and profile curvature.

And then by combining these,

we can work out secondary attributes.

And we looked at particular,

we looked at solar radiation as one of those,

but there are others.

And we also used this to understand the movement

and distribution of water in the landscape.

So basically working out where watersheds are,

pour points and divides and things like that.

So we did cover catchment hydrology.

We mentioned line of sight and viewsheds.

We did something on solar radiation mapping,

and you did a practical based on that as well.

Then moving on to cartography.

Yeah, first thing I wanted to mention

was this idea of map scale.

So look at the four little images on the bottom here.

We start on the right hand side.

The smaller the scale,

the larger the area that's covered.

So if you look at this map here,

has a little square in the middle here,

which represents the next step up in scale size.

So this little area is represented by this square.

This square in the middle here is represented

by the larger square here.

And then finally this square is represented by this.

So the larger the scale,

the smaller the area that's covered

and the more detail you get.

And that's very much linked to how maps are edited

and generalized because obviously if you're showing a map

at small scale, you can't show as much of the detail

as a large scale map.

So somehow you've got to kind of generalize it

and make it meaningful and an accurate representation.

But somehow you have to simplify the whole thing

in order to communicate what the map is.

So there's a number of ways that you can do this.

So to begin with, you may need to edit your map in some way

and then you might need to generalize.

And there were a number of operations

that we talked about in the lecture.

And I think this table covers most of the ones we discussed,

but just to make you aware that it is a much bigger topic.

So this is a more comprehensive list

of the different kinds of generalization

that are applied to maps.

Now I wouldn't expect you to know all of these, okay?

So don't try and learn them all,

but try and remember some of the ones that we actually did.

We covered in the lecture in a little bit more detail.

We did talk about different types of maps.

So we sort of differentiated

between general purpose maps and thematic maps.

General purpose maps divide those into two really,

one which we use for reference purposes,

such as the sort of topographic maps

that you're very familiar with using for Google Maps

or just paper maps that you may have come across.

And then the other type are base maps

which provide the sort of context

for superimposing additional layers of information.

So they're a kind of stripped down version

of your topographic map

where you might just be showing some features

like roads, towns.

You might have contours on there,

depending on what you need to show.

Thematic maps then are really there

to try and communicate a particular piece of information.

So you might show spatial distribution

of a single attribute or variable

or try and display relationships

between a variable over an area.

And then there were a number of these

and I won't go through them,

but some are listed there

of different types of thematic map.

Of course, when we're making a map,

design is all important.

So there are a number of stages

that you need to go through,

select your area, your features,

your projection, your scale,

what it is you wanna show.

You may need to group them or categorize your data

to simplify things a little bit.

Obviously, you want to display things using symbols.

So they need to be visually appealing

and represent the data in a logical way

so that people can understand it.

And then you need to design it

using cartographic elements that are essential

all on one page.

And hopefully you should be familiar with this now

having, you know, going through your assessment process.

You've got a nice map layout showing all of these elements

and they're all arranged appropriately on the page.

Talked a little bit about animated mapping

and how you can use animation,

which is a very effective way of communicating information,

particularly showing changes over time.

And, you know, they can include a time element

or they may not.

Missing a page.

Are you missing a page on yours?

Should be a page here, I think, showing.

No, I'm not sure.

Maybe I just did it twice.

No, it looks like I've got an earlier version.

Let's skip to this one.

So three-dimensional mapping, then,

you did with Rufus last week.

And the first thing you probably did,

I think, was differentiate between

what we call 2.5D and 3D mapping.

So if we drape a layer over a map,

so here we've got a geological map

that's draped over a topographic map.

So it's showing elevation and relief.

This isn't really 3D mapping.

All you're doing is plotting points

according to their X, Y position.

And then the third, the Z value, the up and down value,

is just based on one attribute.

In this case, it's elevation.

If you're going to do 3D mapping,

it needs to include volume.

And this doesn't include volume.

It's just a single measure on a Z coordinate.

So true 3D, then, involves volume.

And there's a couple of examples here.

You can make geological models,

three-dimensional geological models,

which is a bit like you did in the practical last week.

Or you can create digital twins of cities,

having faithfully shown the volume of all the buildings.

So in this case, you need three coordinates, X, Y, and Z,

because it's a volume measurement.

And that is illustrated on this diagram here,

showing the difference between the pixels

and what we call voxels, or volume elements.

So these are truly three-dimensional,

and usually in the form of some kind of cube.

Okay, right.

So whistled through that,

but hopefully I've sort of highlighted

some of the key things that you need to know and understand

in preparation for the exam itself.

So let's talk a little bit about the exam.

And so hopefully you should have an exam timetable

now telling you when and where the exam is.

So the exam is an online exam

carried out under controlled conditions.

So that means you can't use any notes

or anything else to help you answer the questions.

It represents 70% of the final mark for the course.

There will be 50 questions.

The majority of these are multiple choice,

but there are some other types of questions,

which I'll talk about in a moment.

Most of the multiple choice questions

are very similar in style to the lecture quiz questions.

So if I had any general advice,

I would say go through all the quizzes,

because you're probably going to encounter

something quite similar in the exam.

So if you feel confident in answering

all the quiz questions from the lectures,

that really will prepare you well for the exam.

You've got quite a lot of time.

I think the exam is an hour and 30 minutes.

It's a standard time.

So take your time and read each question carefully.

You've got plenty of time.

You don't need to race through it to the end.

I've reproduced here the cover sheet.

So this is what the instructions will be,

and you'll get these during the exam.

So you can see this on the 8th of June.

Now you need to answer all the questions.

So attempt all the questions that you can.

As I mentioned, it's closed book.

Now it has 50 questions, but there are 80 marks.

So some of the questions carry more than one mark.

And you'll be told, for each question,

you're told how many marks it's worth.

Now the complication is that

some of the questions are multi-answer.

So you need to select more than one correct answer

from a list.

Now the way the marking works is that you gain a mark

for each of the correct answer that you select,

and you lose a mark for each incorrect answer you select.

So you get partial credit, but you also,

it's also a kind of negative marking.

You don't lose any marks if you don't select a question

and answer.

So if you don't select it, you don't get anything.

And the minimum score for each question is zero.

So that means if you, for example,

you answer two incorrect answers,

that would be minus two, but you can't go below zero.

So if you selected all five, you'd still get zero.

Say you had five answers.

You selected all of them, you'd get zero.

All right, so think carefully about your strategy.

If you definitely know one answer,

and you're not sure about the other,

if it's asking you for two,

then go for the one that you really know,

and then consider whether you should

choose the other one as well.

Because if you just choose one, you will get one mark.

If you choose two and one is correct and one is incorrect,

you'll get zero.

I'll try and explain that with an example.

So here's a question.

Which two of the following are forms

of geometric corrections applied

to satellite multispectral images?

And that's worth two marks.

So you've got to select two correct answers

from the list of five, which is given to you, A to E.

And the actual, the correct answer is A and B in that list.

So if you don't make any selection,

then obviously you'll get zero.

If you get both your, if you got A and B as your selection,

then you get, that's great, you get two marks.

If you just select A or just select B and nothing else,

then you'll get one mark.

If you select one that's correct,

so say you selected A and you selected C,

well they effectively cancel themselves out, you get zero.

Or if you selected any combination

of incorrect answers, you get zero.

You get the idea, yeah.

What I've done is, for this week,

I put up just a very few practice exam questions,

which cover all, I think,

pretty much all the main types of question.

I don't think it's a true or false in there,

but every other type is in there,

because there are a couple of other types in there as well.

And I've put a little bit of explanation

about whether they, partial credit is applied or not to those.

So have a look at those.

So I think there's about four.

Includes this question here.

If you've got any questions about that,

you can ask me now or at any time before the exam, okay?

Because the last thing I want to do is confuse everyone.

Okay, I think that's everything I want to cover.

Does anybody have any last questions before we break?

No, okay, well, you can always email me

if you have anything you want me to explain

or if you didn't understand anything

from any of the lectures,

or if you have anything else that you need to know,

just feel free to email.

All right, well, thank you very much.

I hope you found the course interesting

and it'll be useful for you in the years to come.

Yeah, let me just put this one on the laptop.

Yeah, do you want to go first,

or do you just want to charge the laptop?

I just have a quick question.

I've done the fly-through,

but I did it into high-risk, low-risk,

and medium-risk buildings.

Is that too over the top?

That's fine, yeah.

I'm not being too prescriptive about what people do,

so I'm very much gonna be led by how you've done it

and then I'll judge you on the basis of that.

But that sounds fine.

And also, I managed to do the outline of the borough.

Should I do the whole thing

or just zoom into the effect of the area?

It might be that you want to show things,

yeah, so, you mean it looks a bit odd.

Yeah.

So you might want to show just a small part of it.

Yeah, the bits that are just not actually.

That's right, the bits are most interesting.

Okay, great, thank you.

I just have a question about the coursework.

Yeah.

I've done the first little bit of tests.

Yeah.

Just between this map and this map,

but the exact same, I've just had the base map.

Yeah.

Which format would you prefer?

It's entirely up to you.

Which one you think is most useful,

or you could put both in.

Okay, and are you expecting us to like

write kind of like a little.

It would be useful if you just summarized

what you think, what the main message was of the map.

I see, so like closer to the cities and.

Yeah, that's right,

but don't try and interpret what it all means.

You know, don't say, well, this area has got higher,

whatever it is, because, you know, so.

Oh, did you just say, I've noticed it's closest.

Yeah, just, was that kind of, was that hotspots?

But this is for the test.

This is for the test, yeah.

I'm just putting the probability number, the p-value.

Yeah, that's fine, yeah.

And then I've not really developed it.

No, that's fine, yeah.

Just basic kind of low-level.

Yeah, low-level stuff is fine, yeah.

And then same for the maps.

Same for the maps, yeah.

Okay, perfect.

Okay.

And yeah, but this one again,

is that fine without the base map?

I thought with the base map, it was too much.

Yeah, that's right, you're too busy, isn't it?

No, I think that's fine, yeah.

Cool, thank you.

Bye.

Basically, this is what I wanted to ask,

because, first of all, was,

do I need to scale everything for all of the maps,

even though I wasn't sure how to.

Which one are you doing?

The air quality one.

So I've got quite a lot of things that are showing them.

You know, the same area,

but I can't really overlay them, because they're all.

Yeah, it's fine to have separate maps,

no problem with that, but yeah,

try and include a scale.

So put them on a separate page,

so you'll have a,

you'll probably want to submit a PDF

with some map images, and some statistical data.

You want each map on a different page?

It's up to you.

If you think it's useful to have

side-by-side comparisons, then that's fine.

If you want to put them on a separate page.

We've got a class in here now.

Can we plug it in outside?
