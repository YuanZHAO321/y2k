---
title: "EART29102 - 09-Mar-transcript"
source: "Sophomore/Hilary Term/EART29102/Lecture/Week 6/EART29102 - 09-Mar-transcript.txt"
type: transcript
---

'EART29102 - 09-Mar', automated transcript
03/08/2026
---

Hello, is it okay if we make a start?

Okay, good, thanks.

Okay, hello everyone.

So obviously I'm not Ray,

but hopefully you've been pre-warned

that there'll be someone different this week.

So I'm gonna be giving a guest lecture this week.

So I'm Peter Grindrad,

I'm based at the Natural History Museum in London,

but also have an honorary position

here in Manchester as well.

And so I'm here to give a lecture today to you

on remote sensing as part of this course.

But what you'll see is that,

although I use remote sensing in my research every day,

I'm actually a planetary scientist.

And I don't spend that much of my time

actually looking at the earth.

So what I wanted to try and do today,

which is a bit cheeky,

is to try and almost convert some of you

to planetary science along the way as well.

So we're gonna use the same techniques

that you'll learn for the earth,

but we use them on a planetary scale.

I wanna show you some of the fundamentals

of the approach we use as well,

because it does matter

when you go somewhere else in the solar system.

Let's say you go further out,

the amount of energy you've got in different wavelengths,

we'll talk about it.

It's important to consider.

So for example, if you see a background like this,

on this slide, this isn't earth, this is Mars,

and somewhere that we hope will land a rover

in about four years time.

But we've used remote sensing as the only tool

to choose that landing site,

and it took us about five years.

But okay, so there's quite a lot to get through today.

Hopefully you can follow this up online anyway,

because I think the notes should already be available,

or they will be soon if not.

I wanna go through some of the remote sensing data,

spend a bit of time on the electromagnetic spectrum.

I don't wanna reteach you A-level physics.

I want to try and show you the parts

that are relevant to the things

that we'll discuss later on in the lecture as well,

because it does matter.

Give a couple of examples of satellites around the earth.

Talk about really a basic introduction

to some of the pre-processing,

or the enhancements we can do,

and then very briefly,

depending if I run out of time or not,

touch on radar and LIDAR as well.

But the first thing to tell you about

is the kind of this distinction that,

so remote sensing bases,

you can define it as a way of collecting information

without actually going and touching,

collecting something.

So for the earth and for the planets as well,

this usually means a satellite

or some kind of object above the surface of the earth

that is collecting information

coming back from that surface.

So in our case, we're collecting energy

that usually, if it is a passive sensor, like on the left,

usually that energy is coming from the sun

and either reflects off the surface

or is absorbed and re-emitted from the surface.

And that energy is then collected above the surface.

And it could be from an aeroplane,

from a satellite, from a UAV, with different instruments.

And Landsat and Sentinel are examples

of satellites around the earth that do that.

There are also active sensors as well,

which aren't as common,

but they do exactly what you'd think.

They actually have their own energy source

and they direct that energy down to the surface

and then collect the information again.

They're not as common, but they have their advantages.

Now, the reason that I think the remote sensing

is such an important topic

is because it can be applied in so many different ways.

And so without even thinking about it,

you will have seen information that has come,

even today or yesterday with the news,

you'll see images that come back from satellites

that are in orbit around the earth.

They can be used for things like urban monitoring,

disaster response, climate change.

We've used it for a long time,

but there are loads of different strands to remote sensing

to do with climate change.

It's especially useful for spotting long-term trends as well.

If you're interested in crop health

or management of forests, for example,

you can use remote sensing data, archaeological studies.

It's really a tool that you can use

for lots of different end goals,

including for me, studying other planets as well.

Okay, so I don't wanna talk about physics

because I'm not a physicist by training,

but it's important to define the electromagnetic energy

that we're actually recording.

And so hopefully, for those of you who have done this

before coming to uni,

you know that there's energy that can go through a vacuum

and it interacts with matter.

And you can describe this using two different methods.

There's the wave method

and there's also the particle method as well.

Now for remote sensing,

the only thing I wanna mention is that

if we use the wave concept to describe

how the energy is propagated and reflected,

but we might use the particle definition

to describe how much energy is detected by a sensor.

So both of these kind of descriptions or definitions

are useful when it comes to remote sensing in certain ways.

So the things that we might be interested in,

let's consider that all objects above zero Kelvin

will emit this radiation

and it's that that we want to detect and record

in our remote sensing instruments.

And so you may well see wavelength in this lecture a lot.

So wavelength is one of the main properties

that we'll talk about as well.

But if you know your physics,

you know that we also have frequency and amplitude

and the function of the speed of light,

you don't need to worry about that too much.

It's just to be aware that if you're talking about

this energy as a wave,

it can be reflected back from a surface.

It can also change in wavelength as well.

So let's consider some energy.

We might as well just go straight to it.

Let's imagine we've got the energy coming from the sun,

comes to the earth and then interacts with,

let's say the surface of the earth

in a number of different ways.

It could be like this example on the left.

It could be an ideal specular reflector.

So the energy coming in has the same incidence angle

as the angle going out, as the reflection angle.

And that is a perfect situation.

You'd very rarely see that.

We could have something that is

the energy is actually absorbed by the surface

and transmitted and refracted down into that surface

and could do something like heat that surface up.

It could be absorbed.

We also have another end member

where the energy is reflected in a perfectly diffuse way.

So it hits the surface,

but it's reflected back in all directions.

So it wouldn't really matter where your detector was.

You're gonna get some energy back.

And then there's also the final case

where you might not need the incoming energy

in the first place.

Your body, like the earth,

could just be emitting energy out

that has already been absorbed.

And the earth does that at longer thermal wavelengths.

So these are the things to consider on the bottom left.

We have the volume phenomena, if you will.

These are where the energy is absorbed

from the surface down.

And we have the surface phenomena.

The scattering and reflection

are the ones we're most interested in.

Now I said I didn't wanna talk about physics too much,

but this is an important plot.

And I'll build on this over the next few slides.

So it's worth taking a moment to explain it.

On the X axis, you have wavelength and in a log scale.

And on the Y axis, you have emittance.

So emittance is just energy, if you will.

It doesn't really matter what we call it, but it's energy.

And so a black body, a perfect black body would emit energy.

And the hotter it is, the more energy it releases.

You can see that in this plot.

So in the bottom right, you can see at 100 Kelvin,

a body emits that amount of energy.

And then as you increase the temperature of that black body,

it emits more and more energy.

I mean, that's kind of what you'd expect.

It's not a surprise.

What's interesting, though,

and important for remote sensing,

is that the peak of the energy,

the peak wavelength moves

as a function of temperature as well.

So in this case, you can see, as something gets hotter,

the wavelength moves to the left.

It is going to shorter wavelengths.

So the green plot, you can see there at 300 Kelvin,

let's say a nice rough average for the earth.

The earth emits energy

at a peak at just less than 10 microns.

You can see the kind of orangey curve about 5,000 Kelvin.

Well, that corresponds to a nice rough average

for the temperature of the sun.

And so the sun has a peak in energy,

which is just there below a micron.

And interestingly, although not surprisingly,

that corresponds to what we call the visible

wave part portion of the electromagnetic spectrum.

And it's no coincidence that we see invisible wavelengths

because evolution has figured out

that the peak energy coming from the sun

is at those wavelengths.

And so it would be great to have our own instruments

that are sensitive to where we've got the most energy.

We could have infrared eyes,

but there'd be less energy for us to deal with.

So it's not great.

So that's the kind of the perfect black body energy plot.

But now obviously, no object is a perfect black body.

And so we have this thing called emissivity,

which is the ratio of energy, if you will,

from a black body, from that of the actual body itself.

And so you get a plot like this in orange.

This is the same data for the sun

just plotted on a non log scale now.

And so that black curve shows

what was previously an orange curve.

And this is the black body as the black curve,

and then the real energy coming from the sun

as the orange plot in the background.

So you can see it fits the same kind of trend,

but there are differences

because it's not a perfect black body.

But we've still importantly got that peak in energy

in the visible wavelength of the electromagnetic spectrum.

So it's worth taking a moment to talk about that, I think.

And so you are all aware of this,

that we have these different names

for different parts of the electromagnetic spectrum.

And now in reality, these kinds of names we give them

and where they are is arbitrary, that's up to us.

There are no sharp breaks, it's all gradual,

but it's so that we're familiar with these areas.

And so we use most of these different regions

in remote sensing for different goals.

And it depends on how much energy is available

and the method you use.

So don't worry about it now,

have a look in your notes afterwards,

but this is an example of the different regions we use

and their wavelength.

Again, because there are no sharp breaks,

you might see slightly different values for these wavelengths.

But you can see how we use these.

So say in the top, I can't find my cursor,

gamma rays completely absorbed by the upper atmosphere,

X-rays too, ultraviolet region partially absorbed

by the upper atmosphere.

And there are a few diagnostic features we can use there.

The visible wavelength, obviously we do use that.

We can use it from the surface

and above the surface of the earth.

And also in the infrared.

So we have reflected solar energy

in what we call the near infrared and the mid-infrared.

And then we have emitted thermal energy

when you go to far infrared.

This is kind of thermal wavelengths

if you think about thermal imaging.

And in some respects, the infrared

is one of the most important regions for remote sensing

because there are, I'll show you later,

many diagnostic features, we call them,

many unique spectral features that can help us figure out,

say, what the surface is made of

or what an atmosphere is made of.

And then as you go to these longer and longer wavelengths,

there's actually less and less energy.

Remember those curves?

The energy really drops off at the longer wavelengths.

And so you actually start to move

from what are passive techniques,

relying on the sun's energy

and moving into active techniques.

And so your spacecraft would actually be sending out

the radar energy, which you're familiar with,

or the laser energy to actually measure the surface.

Okay, so making this plot even more complicated now.

We've got the black line, which is our perfect body.

We've got the orange plot,

sorry, the lightish yellow-orange plot.

In the background, which is the sun's energy.

And then in red, we've now got the energy

that is received at the surface of the earth,

because now the atmosphere is absorbing

some parts of that energy.

And basically where you can see these big drops

in the red plot, those are areas where we receive

little or no energy at the surface

because the atmosphere has absorbed at those wavelengths.

And we can ascribe those absorptions

to different things that are present in our atmosphere,

like water, oxygen, carbon dioxide,

and there's even some smaller trace gases as well.

And so if you wanted to use those wavelengths

at the surface of the earth,

well, there's no or little energy available,

but if you wanted to, say, study the composition

of the atmosphere of another planet,

you can actually use that to your advantage

and say, we have absorption features at this wavelength

so we know that there is this molecule present.

And we do that, not just for planets in our solar system.

So Mars, for example, we've known about the composition

of Mars's atmosphere for a long time

from telescopes on the earth,

but now we're also in an era where we know

the composition of the atmosphere of exoplanets.

So going around suns in other solar systems,

we can work out the composition of the major gases,

at least in those atmospheres

using this same technique as well.

But this is really important because if you do want

to study the surface of the earth, say,

from a satellite above the atmosphere,

you have to pick windows where you've got

the most energy coming back,

where the energy isn't absorbed in the atmosphere.

And so let's say you've now,

your energy has not just come in from a black body,

it's coming from the sun,

it's gone through the atmosphere,

it's reached the surface.

What happens to that energy as a function of wavelength?

So now we've really zoomed in to just the kind of,

the UV, the infrared, sorry, the visible

and a bit of the infrared as well, the near infrared.

And you can see here the kind of plot

for three different things,

soil, vegetation and clear water.

And so what you see for, let's say, pick vegetation.

We know that it absorbs, you can see these dips,

my cursor wants to show, oh yeah.

You can see these dips for red and blue wavelengths.

There is less energy received in the visible portion,

but there is less energy absorbed at green wavelengths,

which is why vegetation typically appears green

because it's reflecting that portion

of the spectrum back to us.

But we can use the absorption features to say

that there's vegetation there.

We can also do things like compare soil to water as well.

And as you move into the infrared,

you can see there's a big difference there

between the way that soils absorb energy

and the way that vegetation absorbs energy.

And so if you wanted to say,

look at how vegetation has burnt away after wildfires

and you're left with bare soil,

you can do that when you go to longer wavelengths

because there's a real difference between the way

that the energy is reflected back from the surface.

Okay, that was A-level physics in about five minutes,

but as relevant to remote sensing.

Moving on to detectors.

Now, you'll forgive me for putting

a planetary aspect on this bit,

but most of the stuff you'll ever think about

during your degree will be with modern detector systems,

but it's not always been the case.

So I wanted to show you what a old detector looked like.

So this is the Ranger 9 mission to the moon in 1965,

which was basically a TV camera strapped

to the front of a spacecraft

that was just pointed at the moon.

And it did exactly what this video looks like.

They just pointed at the moon and they just crashed

and they just analyzed every frame

as it got closer and closer.

And it was an amazing achievement at the time,

but fair to say you will never work

with a detector system like this today.

And in fact, if you wanted a modern detector view

of where that spacecraft actually hit,

well, now we can use something

called the Lunar Reconnaissance Orbiter,

a camera, the narrow angle camera.

This image actually has a resolution

of 40 centimeters a pixel.

I'll talk about pixels in a second moment,

but basically that bright,

these are all impact craters on the moon, very small ones.

This bright feature here with this bright ejector

and dark pattern here,

this is the 10 meter crater made

by that Ranger 9 spacecraft hitting the moon

that we can now observe in great detail

with modern detector systems.

So this is what your images will look like

that you're working with.

But if you really were interested,

you could go back to say the earliest spy satellite images

and detector systems, which most of them,

or a lot of them have actually been declassified now.

So from the kind of early 1960s,

the start of the space age,

this is the system that was used

where an actual film camera was launched on a satellite,

orbited the earth, took photos on the film.

That film, sometimes they're actually developed

and processed in orbit,

and the developed negatives were then dropped

in a capsule on a parachute and caught

with a hook from an aeroplane, which is just unbelievable.

If you've ever seen Batman and he's caught by a plane

flying overhead, it's the same system

they used to catch these things.

But as soon as digital detectors were invented,

spy satellites switched to those.

But you could use those if you wanted.

If you wanted to say look at climate change,

we have very high resolution film images from the 1960s.

But the way that these work is they usually,

for the earth at least, go into orbit.

For planetary science like me,

we also have things called flybys that do what you think.

They just go past the planet once.

But for the earth, you're mostly in orbit,

and there's a few different orbits to consider.

There is a polar orbit where the satellite will go

around the poles of the earth,

and you rely on the rotation of the earth

to give you different coverage underneath.

So basically the planet turns

as your spacecraft goes around the poles.

These are quite high energy orbits.

And so either you have to have a lower mass spacecraft

or you have to have a bigger rocket

to get into polar orbits.

Because usually you go into something like an equatorial

or an inclined orbit because you use the earth's rotation

to give your rocket a kick off the surface.

So we tend to go into those kind of orbits.

And then you can also go into something

like an elliptical orbit where it's not

the same distance all the way around.

You might be in a high orbit at one point,

but on the other side you come really low down

to say just a few hundred kilometers above the surface

and you'll get really high resolution images.

But you can't stay there for long

because the upper atmosphere would degrade your orbit

so you come back up.

You know, we send these missions

to places like Mars as well.

Then things to consider is where your spacecraft

actually goes over the surface.

We have the ground track,

but also your instrument may well have something

called a swath which is wider

than the actual ground track itself.

And over time those swaths will build up

and you get global coverage.

Now luckily I don't need to explain detector systems to you

because you've all got phones in your pockets

with amazing cameras and you all know what a pixel is.

Hopefully you know a bit about bit depth as well,

but basically the color or even the gray scale

if you want to separate them out

into the red, green, and blue channels

of your phone cameras correspond to a pixel value,

a digital number that corresponds to, you know,

different brightnesses in that pixel

and you put those together and you build up a image.

In your cameras you actually have a detector

that will have red, green, blue filters on there

and you pick up different values

for those different colors

which are combined to make a color image.

But what you see in detector systems on satellites

quite often is a detector that will only work

in one wavelength or will have a filter

or filters at different wavelengths

and we combine them to make color images sometimes.

There are a few different concepts of resolution

to talk about here.

The one that most people think of

when they think about resolution for satellites

and satellite cameras, for example,

or imaging instruments is spatial resolution.

So this is basically the size of the pixel

as it appears on the surface.

So again, this is Mars

and there's actually a rover in this image as well

which you probably can't see on the screen

but in the top left you can see a simulated image

at 10 meters a pixel, five meters a pixel,

two meters a pixel, and the native resolution

of this instrument around Mars

which has a resolution of 25 centimeters a pixel.

So better than that one we saw for the moon before

and we use this to track, in this case,

the Curiosity rover driving on the surface.

So hopefully you can see that the better

the spatial resolution, the more detail you can see

on the surface but of course that also means

that you would need a bigger telescope

on the front of your camera

and also the size of your data is gonna be much bigger

than you're gonna need bigger data rates to get them back.

So let's try and demonstrate what this looks like.

So I think I've skipped ahead too there, yeah.

Let's take a surface, somewhere on the surface of the Earth,

simulated view of 100 meters a pixel in a color image.

You can see that you can't make out anything.

It just looks like a nice abstract picture.

If you then simulate what it looked like

at 50 meters a pixel, even if you're squinting,

you're not gonna be able to make out much detail

for this area of the Earth.

If we went to say 10 meters a pixel,

you start to pick up some colors, I think.

You might be able to join some of those colors together

into shapes but you're still not gonna make out any detail,

make any inferences about what you're looking

at this kind of scale.

Instead, if you go to five meters a pixel,

I think some of you should have got this already now.

Five meters a pixel is pretty good spatial resolution.

You can start to see greens, browns, reds, blues.

A one meter a pixel, which is kind of the resolution

we have for most of the moon, sometimes slightly higher.

Hopefully you start to see that you're looking

at where we are now.

This is the University of Manchester and Oxford Road

going down the middle.

Skip that.

Basically, around here we have images in Google Earth

freely available that are about 10 centimeters a pixel.

They were almost certainly collected actually

from an aeroplane rather than a satellite as well.

That's why the images are so good.

Another concept of resolution to understand

is that of spectral resolution.

I've talked about why wavelengths are important.

You can choose which wavelength you want to look at.

If you do and you combine, let's say you had one, two,

all these red dots, you could say,

I'm going to take an image at each of those wavelengths.

You can combine them and start to build up a spectrum.

So if you're looking for absorption features,

this is what you do.

But you have to think about how close together those bands

are to actually resolve a spectral feature now

in your wavelength plot.

And we have terms that can define this.

The full width half maximum is one way of defining it.

We talk about sampling intervals.

In terms of, I won't talk about more today,

but it's an important concept when we go into things

like Landsat and whether you can resolve spectral features.

Another one that you won't need to worry about too much,

but it's important if you ever get into, say,

designing an instrument, is that of radimetric resolution.

And this is basically the bit depth of your detector

and how much digital information you want to bring back.

And so basically the higher the bit depth,

the more information you're gonna get back.

So let's say we had an eight bit detector.

We could get gray scale images back,

but we would only have 256 gray levels,

which is that top right image.

If you had four bit,

you could only get 16 different levels of gray.

And as you increase the bit depth,

you can get more and more values back,

which means you get more and more detail

and you can see tiny differences in the brightness

or even the color of the surface you're looking at.

But it comes at the expense of your data volumes again.

The higher the bit depth,

the greater the memory you're gonna need

on your spacecraft or instrument

and the higher data rates you're gonna need back

from say your satellite to the earth.

And then one that is kind of maybe not thought about

that much for the earth

because we have such good temporal resolution,

but it's that of time.

And it's something we don't have great stuff

for say Mars or other planets,

but we're starting to build up as we go back.

So these planets with more and more data.

So what you're looking at here

is a timeline plot of Mars and some images,

how many images we have of Mars over time

from different instruments.

And I kind of stopped this plot in kind of the early 2010s.

But you can see how this fits

into different seasons on Mars now.

We have global dust storms every year on Mars.

We have seasons on Mars as well, like on the earth.

So when you're considering active processes

on some planet like Mars,

you need to consider what images you have available over time.

So the temporal resolution is important.

And to show that here's part of Mars

taken about 10 years apart, exactly the same image,

same region of Mars, 10 years apart.

And you can see a huge difference.

And all these black streaks

are coming from features on Mars called dust devils.

So very small tornado like features

that remove the dust and they appear dark.

But also there's a new impact crater,

a tiny one that's formed as well.

This black splodge here is actually a new meter about,

a new crater about 10 meters across

that formed in this time period as well.

So we can see active processes on Mars.

And you'll be more familiar with things like this,

recording active processes on the earth.

So these are three land sat images

of what was the second largest lake in Bolivia.

And when I talked about evidence for climate change,

it's things like this.

So this, it was the second largest lake

and because of agriculture and mining,

the water going into this lake, it's a saline lake,

has been diverted over the last few decades.

And now this lake is irretrievably dried up

and no longer is there.

And we can use evidence,

over 30, 40 years of satellite images now

that show geological processes happening

on human timescales because of climate change.

Okay, let's talk briefly about detector mechanics

because I'm not really that into it.

But all of you have got in your pocket, a framing camera.

When you hold up your phone, take a picture,

you're taking a frame, a single frame.

It's not usually how detectors on satellites work.

Instead, what we do is we would have a detector

that might be made up of a single line of detector.

And what you do is use this spacecraft motion

to build up that image.

And so you basically push the image

across the surface of the earth.

So we call it a push broom instrument.

And sometimes they can also scan sideways as well.

So there would be cross track scanners

and we have a long track scanners.

But they don't work in the same way

that just pushing a button,

taking a single image would do.

Occasionally that happens.

But we tend to use these scanning cameras.

And so the idea is they would have a fixed swath

or a fixed width and then you can control

how long your image will be on the surface.

And that's usually limited by the memory

of the instrument to be honest

and how long it can cope with a huge image.

These images regularly will go up to several gigabytes

for a single image that you then have to process.

So these are hard to deal with.

Okay, now this is an entirely planetary aspect

but when you're choosing the detector

you wanna fly on your satellite or your mission,

you need to think about where your planetary body is.

So here I've got two very different missions

but they're actually very similar spacecraft.

So the Magellan mission went to Venus in the early 1990s

and Galileo went to Jupiter in the kind of

mid to late 1990s, early 2000s.

And they were both similar size.

They were both launched from the back of the space shuttle

when that was a thing.

But Venus has this atmosphere and clouds

that completely obscure the surface

that are visible on most infrared wavelengths

which is what we'd use everywhere else.

So instead Magellan had basically one instrument.

It had an active radar that penetrated those clouds

in the atmosphere and it built up an image of the surface

using active methods.

Galileo, which was a similar size spacecraft

had loads of different instruments, all passive

because there was enough solar energy going out there

at different wavelengths for it to use ultraviolet,

visible, near-infrared, far-infrared

to actually study Jupiter and the Jovian moons

like the Galileo satellites.

But these had very different instruments

on very similar spacecraft just because of the conditions

and the energy available.

So when that comes to the Earth,

you've already seen this image now,

we can have color images which are usually made

from combining three or more wavelengths

and we can have grayscale images.

So we normally collect grayscale images

and then we combine them into color if you want.

All of this comes at the data volume cost

that I mentioned before.

Basically if you increase the spatial resolution

or the spectral resolution,

you might lose some of the resolution along the way

so you need to consider it.

So examples of this, I mentioned Landsat and Sentinel

are two really good examples.

Landsat you can access freely all the data

that have come back over time.

Sentinel too, you can as well and they vary in resolution

but one of the great things about Landsat for example

is this has been, it's a USGS or NASA US led mission

but there's been continuous coverage over time

and they'll overlap, they'll set up a new spacecraft

which overlaps with the previous one

before that satellite is decommissioned.

So we have continuous temporal coverage which is amazing.

Right, I mentioned the multispectral images

and color images.

So what we tend to do is have an instrument

that will take what looks like a grayscale image

but it would just be one particular wavelength

but actually it would take images at different wavelengths

and then you can combine them

into what is called multispectral imagery.

And so there'll be things called, we call them bands.

Usually Landsat has eight to 11 bands

depending on which Landsat it was over time.

Sentinel has even more bands

and they cover different portions

of the electromagnetic spectrum

but if you have say 10 bands

but you wanted a color image

you just choose three as your color band,

your color image.

You can combine them in different ways.

So top right, this could be a natural color composite.

You'd call this true color and the top right

you can use the bottom left is pseudo natural color

so you probably choose slightly longer wavelengths

or shorter wavelengths than our eyes would see

and it almost exaggerates what we would see

and then the bottom right

we've made what you'd call a false color image

where you just go to completely different wavelengths

for your red, green and blue channels in your image

and these can highlight different things.

So if you want to highlight water

you can see how that reacts very differently

in the infrared to say rock

and they heat up at different rates.

And so this is trying to show the,

this is Landsat now showing these over time.

So time on the X axis

and we have the early Landsat missions.

The Landsat four and five lasted for quite a long time.

Landsat six didn't work

but Landsat seven was still there.

Can you see how all these lines overlap with each other?

And so now we just need to hope

that this program called Landsat next

actually does happen

and can keep on going with this Landsat legacy

because we've got continuous data

where the great thing about this is that

they don't just overlap in time,

they overlap with, sorry,

wavelength from the bands that were chosen.

So you can see how the earth has changed over time

continuously since the 1970s with similar data.

It is a phenomenal data set

and it is entirely free for anyone to use.

It's amazing.

So examples now rather than me showing you Mars,

different spatial resolutions, we've got the earth.

We have Landsat, you know,

the spatial resolution has improved

but we have different resolutions from 30 meters,

300 meters, sentinel a bit higher

all the way down to 10 meters

depending on which band you go for.

And I mentioned the wavelength of these instruments.

These are, this is obviously a USGS slide

but you can see the wavelength on the X axis,

the different missions.

So the earliest ones at the top,

the latest ones at the bottom

and you can see kind of faded in gray in the background.

This is the plot I showed early in the lecture

that shows the absorption, sorry,

the energy that reaches the surface

through the atmosphere of the earth.

And then these different colored bands represent

where these Landsat missions record information.

And you can see there's been some refinement over time

but there's always this continuum throughout these missions

to look at the same wavelengths.

Some of the kind of visible near infrared ones

have actually been split as technology has improved.

We can actually record more data as well.

And then for the sentinel series of satellites,

you can see there haven't been as many

but there's still the same kind of overlap

and you can compare these with Landsat as well.

So you can see how we tend to choose bands

if we wanna look at the surface

that intersect these high energy areas

where there's a big gap, these bands will be chosen

to actually study the atmosphere.

And you can study the atmosphere

and you can also use the information in those bands

to improve your surface information.

Okay, this is why I said it's really important

that Landsat Next actually happens and isn't canceled.

On the left, you've got the Landsat 9,

which is the current one,

and the rate at which it repeats images over the surface.

On the right-hand side, you've got Landsat Next.

There's two images,

it's two satellites going around close to each other

in a similar orbit,

and they basically have global coverage

within about five or six days.

And then they can start to repeat after six days

when the current Landsat mission

is still trying to build up a single global image as well.

So this is an amazing, amazing resource

to get repeat coverage and global coverage as well.

Okay, some of the pre-processing in the last 10 minutes.

There's geometric processing.

Sometimes your satellite might not be looking straight down,

it might be looking to the side,

and you might have to correct for that.

You also have to georeference your image onto the surface

to know that it's in exactly the right place.

To do that, you need really good information

about your spacecraft position and pointing,

which is actually quite complicated orbital mechanics,

but hopefully someone else is doing that for you

as an end user of the images.

And you might also map, project those images as well

onto your planetary body so that it overlaps

with all the other information you have

for that part of the Earth.

We also have radiometric correction as well.

So on the left, you can see an image

that is almost the raw image,

and it shows the atmosphere as well.

The image can go through processing

to actually remove as best as possible the effects

that the atmosphere has in that image.

So in this case, we get much better clarity

or contrast at the surface

because we've removed the effects of the atmosphere.

And there's a few ways of doing that,

but it's an atmospheric correction basically.

And we can use some of those observations

in the atmospheric bands to help correct the images.

And one of the ways we do this on Mars, for example,

is that we collect data at the top

of a huge volcano called Olympus Mons,

which is actually so tall,

it's actually poking out of the top of the atmosphere.

The effects of the atmosphere at the top of Olympus Mons

is really, really small.

And so we take some data there,

and then we collect data from a deep, deep part

of the surface, and we can look at the difference,

and we can remove the atmospheric defect.

And that's how we do it for Mars,

and we can do a similar thing for the Earth as well.

Different enhancement techniques.

We can combine different bands.

I've already showed you that with a multispectral imaging.

We can pan-sharpen the bands.

I'll show you an example of this in a moment,

but you can have a low spatial resolution image

taken at lots of different wavelengths,

and you can have a high resolution image

taken at a single resolution,

and you can try and combine the two.

We can do things like stretch the contrast,

which you've all done.

We can do band ratios, which I'll show you as well.

So different combinations.

This is using the example of multispectral images.

For Landsat, you'll see some standard combinations

of the bands that highlight different things

for agriculture, for geology, for vegetation.

And these B4, B3, these are the different bands.

And you also start to see some band maths

creeping in here as well.

So there'll be subtraction, addition, ratios

that people have figured out over the years.

Best emphasize different spectral features.

So for example, in Los Angeles in 2017,

and a couple of years ago, there were massive wildfires.

In the top, you can see visible wavelength image.

In the bottom, you can see a band ratio,

a band combination called NBR,

which is using near infrared and short wavelength infrared.

And it's exploiting the response,

the difference between kind of healthy vegetation

and burnt vegetation.

And in these two spectral curves,

you can see on the right-hand side.

So all those red areas in the bottom image

are basically areas where the vegetation has been burnt.

Pan sharpening I mentioned.

So on the left-hand side, we've got a color image,

a multi-spectral image,

which has a low spatial resolution.

It looks pixelated.

In the middle, you have a single wavelength image,

which is high spatial resolution.

It doesn't look pixelated.

And then if those two images are really well

co-registered or aligned,

you can combine them to make a pan sharpened image

on the right-hand side,

which hopefully combines the best of both of these images.

You have the high spectral resolution,

you have the high spatial resolution.

That works best when you have a single instrument

pointing at the same place at the same time,

but you can try it from different instruments

at different times.

It's just harder.

And things like contrast stretching.

You've all stretched the contrast in the image, I hope.

On the left, you can see it looks pretty washed out.

There are different ways

of stretching the histogram for an image.

And you can even overdo it on the right-hand side.

You can equalize the histogram,

but it does serve its purpose.

You can highlight the edges

if you're after the boundaries of different units

or vegetation on the surface.

Okay, finally, rushing towards the end,

we have some active methods as well.

So RADAR, which is an acronym, is an active method.

We use this all the time,

but it's really good if, say,

you wanted to look at the Earth or another planet,

like Venus, when the surface is obscured

by something like clouds

and those other wavelengths, the visible wavelengths.

We can't see through the clouds, the visible wavelengths.

But also, you know, UV and infrared

are also obscured by those clouds.

RADAR at different wavelengths, at longer wavelengths,

can penetrate through things like clouds to the surface,

interact with the surface,

and be reflected back up to your detector.

And you can build up even images of the surface as well.

So RADAR might be used quite a lot

to just work out how long it takes for the radar

to go back to the spacecraft,

and you could build up a height map of the surface.

But you can also do things like interferometry,

where you can build up an image

of the surface with radar as well.

So we use radar imaging quite a lot.

The difference here, though, is in the bottom left,

is that the way that these images look

is actually different to the way

that a visible wavelength would look,

because you're working at longer wavelengths,

and so you're kind of dealing more in roughness

rather than the actual kind of surface itself.

So there are a few things to be aware of with this, though.

Because it's an active method,

the energy isn't coming from the sun,

it's coming from your spacecraft,

and it's almost like shining a torch on a feature.

You will get shadows, radar shadows,

and radar effects on the surface.

So for example, foreshortening,

where something will almost look like

it's leaning towards your detector.

If it's very steep, you get something called layover,

or even shadowing, where the radar can't see

past that really high or steep feature.

And I wanna show you examples of this.

So on the left, we've got a small volcano in the center.

This is actually a Venus.

And hopefully you can see this feature, it looks like.

You can see this little tiny pit on the top.

That is a caldera at the top of a volcano,

and it's more towards the left-hand side than the right.

And that's because the radar, in this case,

was looking from the left,

and everything looks like it's leaning

towards the detector, but it's actually in the center.

In the right-hand image, you can see

this is actually the Earth.

And this feature here is actually a glacier

flowing down a valley and mountains.

And this mountain looks like it's obscuring

or blocking the glacier, but it's not.

It's actually laid over.

It's so high and so steep,

it looks like it's over the glacier,

but actually it's not.

The radar this time was coming

from the top of the image down.

And so the surfaces can look very different

depending on your look angle.

So this again is Venus.

Two images, exactly the same region on Venus.

We're not looking at a different area,

but the surface looks very different.

Nothing has changed between these images

taken a few years apart.

But the way that it looks towards varies a lot

because on the left, the radar was coming from the right,

and the right image, the radar is coming from the left.

So it highlights different features

and different roughnesses in a different way.

And then to try and sum up,

because I'm nearly out of time,

we can also exploit the longest wavelengths for say radar,

and it won't just reflect with rough surfaces

or penetrate down to a few centimeters

or tens of centimeters.

If you use really long wavelengths,

it can actually go down meters,

hundreds of meters, even kilometers.

And so this is ground penetrating radar.

Now we use this on the Earth a lot in field work.

You would drag a ground penetrating radar

if you did field work somewhere

and you try and see into the subsurface.

You can do this from satellites as well.

Now I don't think this is used that often for the Earth

because you can usually go to that location

and have a much higher resolution

ground penetrating radar survey.

But for somewhere like Mars,

this top image is actually showing a slice

through something called the NPLD,

the North Polar Layer Deposits,

which are these ice-rich deposits

that build up on the edge of the northern polar cap.

And each season, some more dust and ice is deposited

and these layers are built up over

probably millions of years

and we can see those layers over time.

And the bottom image is actually showing a feature

which is much closer to the equator,

but it's probably ice-rich

than we think has flowed in the past as well.

So it can penetrate icy things.

And we can always use radar as well.

Hopefully you've seen images like this on the left.

You can use the kind of difference between radar phases

over time when something like an earthquake has happened.

So you can see these kind of patterns come away

from the earthquake location.

And this is called interferometry as well.

And we use this all the time in terrestrial remote sensing.

We've never been able to use it

in planetary remote sensing for this purpose

because we've never seen an active earthquake

on another planet using this kind of technique

because we've never sent this kind of radar

to another planet.

And then finally moving from radar to lidar

which is just using lasers rather than radar.

Again, this is really good for interacting with the surface

and can penetrate for the earth vegetation.

We use these on planets, but we don't have vegetation.

But if you have say a lidar instrument

flying on an airplane, like in this diagram,

it can penetrate through things like trees and canopies

and you get different energy returns

and you can remove those from the surface.

And this is where there's a difference

between something called a DTM or digital terrain model

which is everything or a digital elevation model

where you can remove the effect of buildings,

trees, forests, and you get representation

of the ground surface as well.

We use lidar for the earth all the time,

super high spatial resolution,

super high precision vertically as well,

kind of to like almost centimeters resolution vertically

so you get amazing elevation models.

Okay, now I know I rushed the last bit

which is kind of tend to, so I need to stop.

There are some more resources.

I think the slides should be online

and any questions you can ask me afterwards

or get in touch with Ray, but I'll stop there.

So thank you.

Or does anyone need to see the QR code again?

You're all good.

Yep, I'll put it back up.
