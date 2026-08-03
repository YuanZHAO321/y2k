---
title: "EART29102 - 21-Apr-transcript"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 8/EART29102 - 21-Apr-transcript.txt"
type: transcript
---

'EART29102 - 21-Apr', automated transcript
03/08/2026
---

on a Tuesday. So this is my one and only appearance for Geospatial other than

the practice that's associated with this on Friday.

So I think Ray Burgess has put in all the groundwork and I'm just coming in.

I think this is the last week. Is this your last lecture in Geospatial? Have you

got something next week as well?

Who knows? All right. Okay. So what are we going to do today then?

Okay. So most of what you've been doing so far has been in 2D. You might have

been thinking some of it's been in three dimensions,

but actually you've mainly been working in the 2D realm. So we'll go on and

essentially I'll explain what 3D means in the digital world.

We'll also recap some of the stuff that you've been learning over the course of

the course and have a look at what you've been learning so far,

sort of how it applies in the three-dimensional world. We'll recap over things

like continuous and discrete raster vector data and things like that.

And then we'll go on and have a look at applications for 3D GIS. Okay. So what

is three dimensions?

So most of the time, most of the times we're interacting with GIS data rather

than doing it on a computer screen or we're doing it on a paper map.

And both of these are 2D surfaces. So how can you have 3D in a GIS world? So

just to sort of have a quick look at the history of it,

Wolfenstein was one of the first computer games that thought of itself as a 3D

one. It actually started way back in 1991 where it definitely wasn't a 3D

computer game.

So it started back in 1981. Ten years later, it was revamped to this kind of

thing. So you're a sort of object,

careering around in a world. You have to avoid these obstacles and stuff like

that. Is that a three-dimensional? It's kind of GIS.

You're interacting with topography. You're moving around a spatial world. So a

computer game is essentially a GIS program.

But is that three-dimensional? Shadows, things like that. Is it three

-dimensional? I suppose the answer is no.

So it uses what's essentially known as raycasting, which is a method of

effectively popping things up to give it the appearance of three dimensions.

But when you're in these corridors, when you're in these rooms, when you're sort

of navigating around, you don't have any access to third dimensions.

So this is essentially still a two-dimensional game. Sometimes you refer it to

sort of two and a half D.

So as soon as games like Doom came along and you could start jumping up onto

levels, running along the top of walls and stuff like that,

then you've got access to the third dimension. But games like this are not

really in the three-dimensional world.

Okay, so let's go back to stuff which is more relevant to your degrees. What is

meant by 3D when we're using something like ArcGIS?

So here's a map of the Isle of Mull. It's just a digital version of the paper

map, the BGS paper map that exists for the Isle of Mull.

So if we wanted to locate ourselves on any point on this map, we could find

ourselves by using some kind of GPS and locating ourselves with an X and a Y

coordinate.

That can take us to any point on the map. Okay, we could do something to make it

look a little bit more fancy.

So we can display a digital terrain model of the same area. Then we can plot

that same geological map on top of it.

So now we've kind of got a geological map which conforms to the topography that

we've got there.

So is this version of GIS 3D? So essentially it's still a surface, kind of

existing in 3D space because we're draped over that DTM.

But if I give you a coordinate, if I give you an X and Y coordinate, you can

still go to any point on this map. So it's still effectively a 2D surface.

And if we look at it in terms of mathematics, if we're looking at topology, then

a surface is always 2D.

So what's important? What's important for defining something as 3D? And the most

important thing is it contains volume.

So two examples here. We've got peak distribution in the Netherlands. So we're

looking at different soil types and that's at the surface, but it's also below

the surface.

So in order to pinpoint where we are in the subsurface and identify that soil

type in the subsurface, we need to involve the Z direction.

Same with the sort of structural model developed at the subsurface. If we want

to investigate what's happening in the subsurface, we need to know the X, Y and

Z coordinates of that point.

And of course, this generates all sorts of problems. If you've got volumetric

data, you can only see the edges of it. You can't see what's going on inside it.

So in order to make it useful, we need to have ways of interrogating it, ways of

slicing it up and looking at it in more detail.

OK, so that Z dimension is always a bit problematic. You've probably been going

through this with some of the stuff that Ray's done.

So where do we measure from when we're looking at a coordinate system? So if

we're in the UK, we measure, well, it's relatively easy.

We measure the X direction, so the longitude direction. We define it from its

relation to the prime meridian.

And the prime meridian is located in Greenwich, just near London. The Y

direction, so the latitude, is defined by the equator.

And the equator itself is a point which circumnavigates the globe, which is

equidistant from the two poles.

OK, so how do we define Z? So the prime meridian and the equator are both

effectively 2D things, 2D phenomena.

So how do we define height away from that? So Z is always a bit problematic, and

it's partly problematic because the Earth is not spherical.

It's always good to put flat Earth up in a geospatial lecture. So Earth is not

spherical, and it's been known that it's not spherical for a long time.

So Isaac Newton, who was one of the first people who worked on this, who first

theorised, you know, used thought experiments to think about what shape the

Earth would be.

And his basic idea was that if we drilled two wells, one down from the pole to

the very centre of the Earth, and another down from the equator to the very

centre of the Earth,

and then we filled these two wells up with water so that they were a linked

system, he thought the equator, or the equator well, would have to be longer in

order for the system to be in equilibrium.

And he sort of assigned this to angular momentum. So he thought as the Earth

spins, it's going to effectively propel the water or lessen gravity in the

equatorial well.

So it's this sort of first ideas of angular momentum. But he also applied that

to the mass of the Earth as well, thinking the Earth would have a different

diameter.

And he was essentially prove right later on. So the Earth, the shape of the

Earth is what we would call an oblate spheroid.

The equatorial diameter is 12,700 kilometres, and if we take a polar diameter,

it's about 40 kilometres shorter. So this is all relatively well known.

So early thoughts on where we measure the z direction from. The centre of the

Earth is kind of not valid because we've got this problem of effectively the

distance from the centre of the Earth to the surface of the Earth changing as we

go on a transect from equator to pole.

So there's a whole study, a whole field of study out there known as geodesy,

which is the science of measuring the Earth's shape, also its orientation and

its gravitational field as well.

And I'm sure you've been working on these kind of things, but just to sort of

recap on what we've been doing.

So we can kind of mathematically describe the shape of the Earth using something

known as an ellipsoid, and that's an idealised model.

It just covers everything, averages everything out.

And you'll find that most of the sort of global scale things like your phone

uses an online version of WGS 84, which is related to these global ellipsoids.

Local national grids tend to use a different ellipsoid, one that's a little bit

better approximates the shape of the Earth's surface in the area that you're at.

So these generally have different functions, the sort of national scale maps

versus the global scale maps.

So if we want to look at this in more detail, we use what's known as a geoid.

A geoid is a gravitational equipotential surface.

So it's the point where the gravitational measurements of the Earth's surface

are sort of equal around the planet.

And it's broadly equivalent to sea level, but it changes.

It's not a constant thing.

It changes as things that have mass move around the planet.

So things like tides affect the gravitational equipotential surface.

We've got longer term geological processes like continental drift, the

activation and relaxation of magnetic plumes, things like that.

They all affect this geoid surface.

So we know it's affected by things like lithological density, erosion

deposition, mountain growth is all going to affect this kind of thing.

Tides, plectectonics, water depth, crustal heating, tectonic dynamic loads, all

this kind of thing affects the geoid.

So we've got interesting points here.

So we've got a view of the Earth, this side of the Earth, and we've got two

points on it.

So we've got the sort of Europe area over here is red.

So we've got positive, higher gravitational attraction in this area.

And this is due to extra thick crust that we've got sitting below Europe.

So essentially we've got very thick crustal area, partly due to it being a

stable craton, part of the Earth.

And this gives excess mass, which means the gravity above it is higher.

We've also got over the tip of India here in the Indian Ocean, we've got the

Indian Ocean geoid low.

And actually, if you go to the Indian Ocean geoid low, sea level is 106 meters

below the sea level there.

So we kind of get a dip in the water level in the sea surface.

And that's because there's less gravitational attraction to pull, less

gravitational attraction or less different gravity in that area.

OK, so local methods of measuring our vertical dimension.

If we stick with the UK, so the UK Ordnance Survey is one of the oldest ordnance

surveys on the planet,

one of the oldest methods of actually calculating the X, Y and the Z

coordinates.

So the Ordnance Survey uses or still sort of uses the Ordnance Survey of Great

Britain 1936 Coordinate Reference System.

And that's tied to a tied gauge in Newland in Cornwall.

And this is a very traditional network.

So we've got Newland and then we have a set of triangulation pillars which

expand out from Newland.

So it produces a triangular irregular network grid, which expands from Newland

and covers the whole rest of the country.

So in those early days, the sort of cartographers, the people who were surveying

the UK,

would have gone to these individual trig pillars and sighted to the next trig

pillar.

So they would have worked out the orientation, direction and height of the trig

pillars that they could see from the trig pillar that they were at.

And this triangular network was what was used to initially map out the UK.

Of course, colonial UK did this all over the world.

So the initial mapping of India and the area around that started in Bombay, as

it was at the time, and then moved outwards.

And you'll find that the accuracy that they did, that they were involved with at

these times,

means that the measurements they took in northern India were actually only 8, 10

metres out compared to modern satellite GIS measurements that are conducted

today.

So just the accuracy involved with these measurements is quite impressive.

So that's the sort of traditional network.

We've also got more modern Ordnance Survey GPS networks,

which are tied to the European Terrestrial Reference System of 1989.

And if you're doing live RTK, real-time chemetics, GPS measurements,

which get you down to sort of millimetre accuracy, then they're tied into this

GPS network.

General GPS, so GPS on your phone, used at the Global WGS 1984,

to the World Geodetic Reference System of 1984, and that is the one that you'll

most regularly find.

Now, all of these produce slight, well, if you measure, for instance, if we were

to climb this mountain and measure the top of this mountain,

if we were to use different coordinate systems, we would end up with slightly

different measurements.

And the reason for that is that our measurement position is defined effectively

perpendicular to the reference system that we're using.

So if we're using the geoid height, which is more sort of ups and downs, more

complexity associated with it,

it can produce, when we measure sort of perpendicular to it, to the point that

we're measuring at,

it can produce a slightly different X, Y and Z coordinate than if we use a more

global ellipsoid.

So because there's differences, you need to use translation systems in order to

convert from one coordinate system to another,

which can generate all sorts of complexity if you've got data in different

coordinate systems,

or data with an unknown coordinate system is your worst case scenario.

Digital space then. So you've been working with 2D data. So you all have been

working with raster data and vector data.

So raster data is lines in space, things like roads. Pixel data is what you find

in raster information.

So it's a regular array of data values where each pixel has an X, Y in location

and a set of descriptors.

So it's what you use to create aerial photographs, digital elevation models,

things like that.

All that information is encoded in a 2D raster. We can take this idea and expand

it into what's known as a voxel.

And it's essentially a three dimensional raster image. So each voxel in this

cube of voxels here has an X, Y and Z position.

And we can also apply other descriptors to it, things that might be useful.

So we might apply a discrete class. We might apply time if we're looking at how

things change.

We might apply, if we're looking at the subsurface density of the rock that

we're looking at, the type of rock or its reservoir properties, things like

porosity.

So they're quite useful if we're dealing with anything like that.

So building on that idea, we can create our 3D models using the same sorts of

data that you've been using in the 2D world.

So we can create them using discrete data or continuous data.

So, well, two examples here. Dutch soil profiles. Here we're looking at discrete

data.

This is a classification system. We assign different values to our different

soil types here.

So discrete data is effectively a coding system.

Or we can use continuous data where our variable can vary from one point to

another and all points in between.

So this is good for measuring things which can vary, things like temperature and

stuff like that.

So again, just to go over that, just to sort of reinforce those ideas, discrete

data is information which is encoded using defined values.

So we can have different functions associated with this, but they usually have

defined boundaries.

So a good example is something like a geological map.

So each of these different geological units is encoded.

And if we look around it, we can see there's a defined boundary between our

different geological units.

So we can encode information like that or we can have counted variables as well.

So counted variables might be things like a town population.

So again, information encoded in a GIS way have numeric values.

So other examples of classification, things like land use, road type is another

one.

So we can classify different scales of road and assign a road type and a

symbology to them.

Quite useful in the GIS world.

Continuous data is a measured variable that can have any numeric value.

So there's no value, there's no boundaries within these.

So here we're looking at an elevation map and we can see that our elevation goes

from low to high continuously.

So there's no boundaries between our different height values here.

So other examples of continuous data, things like rainfall, satellite photos as

well, gravitational maps.

There's another one that can be quite useful.

Okay, so 3D. How do we create 3D for the information we've got?

So we can use ArcGIS and it has tools within it in order to convert spatially

limited data into three-dimensional data.

So quite often when you're dealing with the subsurface, when you're dealing with

what's going on below ground level, you don't really have access to it.

You don't have access to that full 3D volume.

The information you've got is things like boreholes.

That's where people have drilled a hole and recovered a small amount of rock

which you can identify.

So it gives you a very small window into the subsurface.

You can have things like ground penetrating radar or seismic surveys where you

fire energy into the earth

and then look at the reflected patterns that come back and use that to interpret

surfaces in the subsurface.

But it's not a complete picture.

So usually we need to interpolate between that limited data in order to get a

picture of what's going on.

So the method that we are going to use on Friday is a method known as empirical

Bayesian Creeging.

So Creeging is a method of interpolating between point data, so between

unlimited bits of data.

Bayesian is employment of prior knowledge into a calculation.

So what Bayesian does in this case here is use...

Well, it basically uses the information it's got to calculate statistical

relationships between the variables that we've got

and then run that experiment repeatedly until it comes up with a model of how

the relationships work.

And then it uses that to effectively fill in the space between the points that

we do know.

So our empirical Bayesian Creeging produces a set of horizontal slices that move

through the data

and then we use ArcGIS again to convert that into a volume to basically

interpolate between those 2D slices to come up with a three-dimensional volume.

So quite useful.

And in the GIS world there's loads of other things that you might use.

It's quite powerful for investigating three-dimensional data.

So we can use it in the subsurface for resource calculation, possibly aquifer

calculation.

We can use it for atmospheric data.

So here we've got an example of relative humidity with height.

Or we could do similar things with oceanic data.

So we can look at temperature profiles, pollutant profiles, anything like that

that we can do.

So once you've got this information, I was saying it can be quite problematic to

actually make it useful.

So once you have that information, you often have to sort of subsample it into

2D in order to be able to visualize it properly.

So we often use things like 2D slices or ISO surfaces.

So an ISO surface is where this red area here is an ISO surface.

It's where you map out equal values that sort of wrap around your data in order

to visualize the shape of the phenomena that you're trying to image.

And we'll be slicing on Friday.

OK, so I don't get an option to introduce you to a link practical, so I'll do

that now.

So the practical that we're doing on Friday is a three-dimensional GIS

practical, and it's associated with resource geology.

So we're going to go to a place called Wales or a place called Coda Brennan in

Wales.

So it's on the sort of southern end of the Snowdonia ranges, and it kind of

looks a little bit like that.

So the reason we're going to look there is because there's a fairly large copper

deposit that sits underneath it.

And just to sort of quickly go over the ideas behind global demand for critical

metals.

So this is the expected global demand for critical metals, which has been

brought on by Net Zero World.

So the general idea is that making energy without burning oil and gas and coal

requires other elements.

And these are other elements which essentially require geologists to find and

extract.

So the metals that we're particularly interested in are things like copper.

So copper is used for all things that use electricity.

Copper windings in electrical motors, copper windings in wind turbines, all of

the sort of electricity generating mechanisms.

We also need things like cobalt and nickel for stability in lithium ion

batteries.

We also need various critical metals associated with electrical vehicles and

solar panels and things like that.

So the demand for these is increasing as the world sort of moves away from oil

and gas, and it can be a reasonably dirty business.

So cobalt, a lot of cobalt comes from the Democratic Republic of Congo.

So lots of big companies, so I'm talking the Apples and Teslas, Samsung,

Microsoft, all these companies are implicated in a supply chain that effectively

uses child labour and slave labour in the Democratic Republic of Congo.

Mining this stuff is not particularly good for you.

It's linked to all sorts of physiological problems, particularly if it's done

like that rather than using sort of modern mechanised systems.

But still, an awful lot of the world's cobalt comes from the Congo.

Nickel is important in the cathode for lithium ion batteries.

It's important for making a stable battery, so one that doesn't burst into

flames if you overcharge it.

So it seems to be mostly prevalent below rainforests.

So Sulawesi and Maluku are being dug up in order to mine nickel.

And a lot of these operations in the back end of beyond, where they're not

really visible, are essentially illegal.

And the problem with illegal operations, a bit like the Congo, is that there's

big implications or consequences for the environment,

particularly due to poor control of contaminants and waste materials that come

from these mines.

And it has similar sorts of toxicology as well.

So what I'm essentially asking, is it better for critical metal extraction to

take place in places like the UK,

where we have environmental policy, robust environmental policy and

accountability for the companies would be doing the mining and the processing.

So, as I say, copper is important.

Copper is important for all aspects of the electrical economy.

But it's just one of these critical metals.

So just to reinforce that idea, an electrical car requires six times more

mineral input than a car that's running on hydrocarbons.

So six times more mining has to take place in order for your car to work.

Megawatt for megawatt, a wind farm requires 13 times more mineral resource than

a gas power station.

So, again, significant more resources are needed in a net zero world.

So should the UK aim for copper self-sufficiency in this new world?

So this is where we go to Coderbrennen.

OK, so I don't know if anyone's been there.

It's sort of famous for its mountain biking. Is that why you've been there?

Yeah, it's good fun.

So I think the black trail goes around here.

So we're kind of interested in this, the Athen Wen up here and Cappel Herman,

which is over in the background here.

So this is where we have quite a large copper deposit associated with it.

So we're kind of interested in the geometry of that copper resource,

characterizing it in three dimensions, seeing what it looks like and seeing what

it would look like.

So just to sort of reinforce what a copper porphyry is.

A copper porphyry is associated with volcanism, and it's particularly associated

with destructive volcanism.

So what essentially happens is we have our down-going plate, which is water

laden, and it produces hydrous melts.

So as those sediments, basically water, which is held in the down-going slab,

are heated and driven off,

we get these water-rich or hydrous melts, also containing a lot of oxygen.

Now, as this material, particularly these fluids, sort of go through the mantle

wedge and the lower part of the crust,

they deplete sulfides, which are present down there.

So they pick up sulfides, and we find that copper and gold have an affinity for

these sulfides.

So as these sulfide-rich waters pass upwards and through, they pick up copper

and gold, essentially.

So these initial melts are initially quite rich in these metals.

So as they ascend and start solidifying, start turning into magmatic bodies,

things like that, these sulfides are not compatible.

They're incompatible with these magmas.

So they tend to either be driven off in hydrothermal fluids or form sort of very

late-stage mineralization associated with these.

So that's essentially what a porphyry deposit is.

It's these sort of ore-bearing hydrothermal fluids which are driven off these

systems.

So there's a lot of porphyries around the world, not many in the UK, but we do

have a few.

And they tend to have a particular pattern associated with them.

So they're associated with relatively shallow intrusions.

So we're saying sort of one to seven kilometers deep, where the copper tends to

accumulate at the top of these.

So we have this process again of high-pressure fluids, magmatic fluids,

effectively hydrofracking the ground or the subsurface area associated with this

magmatic ascent, hydrofracking it and then depositing within these fractures.

But we also have sort of disseminated copper and gold deposition taking place.

They're just basically sitting in the pore spaces of these sort of country rocks

and also partly in the magmatic bodies as well.

So the metal sulfides usually form these sort of halos around the intrusion.

So our intrusion is down here in orange.

We're interested on this side here, the porphyry deposit, and we get sort of

copper associated with the sort of fracture systems directly above the battle

lift and also in the vent systems and fractures higher up within the system as

well.

It can be concentrated by modern surface processes.

So meteoric waters, oxygen-bearing waters, can again re-pick up these deposits,

carry them down to depth where their conditions are less oxygenated, more

reducing, and this is where we get sort of concentrated layers of copper can re

-form.

So they're relatively low grade.

So a good one might be sort of 2% copper.

So just to sort of look at these different bits.

So in Coda Brennan, the battle lift itself, although the magmatic body is a

microtonalite, so intermediate to volcanic rock,

the copper forms these sort of disseminated and crack-filled greenish bodies,

which you find at surface today.

We can also find sort of breccia pipes and things like that.

So breccia pipes that we can see at the top here, so these sort of shattered

country rocks.

And sometimes the porosity in those shattered country rocks can become very

strongly mineralized by the fluids that were moving up through them.

We also see an awful lot of pyrite associated with them as well.

So they form large bodies, big plutonic bodies and sort of big areas that sit

above them where we have these sort of hydrothermally altered rocks and these

hydrothermally precipitated bodies.

As I say, we can also enrich them using this supergene process, this redox

associated supergene process, which can enrich your deposits.

It could double it from 1% to more than 2%.

And it's by this sort of method, this redox method of oxygen-rich waters, taking

these sulfides to deeper levels.

OK, so this is the area that we're interested in.

And the data set that we've got was a set of boreholes that were drilled in the

1970s.

So they were investigating whether or not Coda Brennan is a potential copper

mining site.

So they were kind of interested in the geometry of it, the extent and the grade

of copper,

what would be the return on their investment if they were to dig it up.

This is all based on previous mining.

So it was mined, it's been mined for a very long time.

The gold mining in particular that's associated with it has been conducted for

hundreds of years.

But the copper mining sort of mined from the 1850s, probably up to about 1915.

And they retrieve significant quantities of copper.

But strangely enough, the whole operation was closed down because it affected

the fisheries.

So they're left over tailings.

So after they'd removed the copper from the ore, crushed the ore, removed the

copper,

what was left, they just sort of dumped it into the valleys and the rivers took

it away.

And in the rivers, it sort of ruined any fly fishing or any sort of inland

fishing that was taking place.

And offshore, all this sort of extra sediment and particularly the sort of

acidic,

sulphide-bearing sediments effectively caused a collapse in the fisheries.

So it affected other industries. So it was forced to shut down in 1915.

OK, so, but we still see evidence of it at the surface today.

They say it far too often. But yeah, we got some of this in right at the

surface.

So there was something that looked, that was called the turf mine.

And the turf, there were sort of redox conditions within the turf mine,

particularly sort of rotting vegetation, which produces reducing conditions,

which led to a sort of precipitation of copper, quite high concentrations of

native copper,

where they just effectively dug up the turf and burnt it in order to extract the

copper.

We still see evidence for copper being at the surface or close to the surface at

the present day.

And we can see it partly in the vegetation.

So these are pink flowers, known as sea pinks.

You get them around the coast because they're metal tolerant.

So they're tolerant of the salt, essentially, that you find,

the sodium and other salts which are present at the coast.

But they also thrive above metal deposits as well.

So if you see lots of these when you're wandering around Wales,

it's probably because you're on top of some kind of sulphide deposit.

So I have sort of collated the information from this well,

from these wells which are present below Cabell-Herman.

And what we're going to do on Friday is have a look at sort of getting it into

GIS,

getting it into ArcGIS Pro and trying to sort of plot out the geometries

of these copper-bearing bodies which are present below.

In the 1970s, they considered it not worthy of an extraction.

But I'd be interested to hear your opinion.

Would you dig up some Snowdonia in order to access this copper?

It would essentially look a bit like that, I think.

All right. I think that will do us for today.

So I'll see you again on Friday.

And we'll have a look through this.
