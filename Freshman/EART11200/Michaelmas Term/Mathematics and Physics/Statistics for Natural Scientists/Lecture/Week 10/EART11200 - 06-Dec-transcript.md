---
title: "EART11200 - 06-Dec-transcript"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 10/EART11200 - 06-Dec-transcript.txt"
type: transcript
---

'EART11200 - 06-Dec', automated transcript
01/08/2026
---

Okay, thanks everybody for coming still this late in the semester.

A couple announcements and then I'll talk about material.

First thing is about the assessment.

I mentioned last week that I'll put that up today and I will, but I'll do it

after the

practical session because if I do it before, the temptation to look at it before

will be

too much and people end up looking at it in class and I want to prevent that for

two reasons.

One is I want people to concentrate on the practical, not on the assessment in

class,

but also the practical really does need to be an independent piece of work, so

you can't

work on it in pairs, so it'll be better to not have everyone looking at it at

the same

time in class because it will just make things confusing.

If people have questions about it, instead of asking in practical, there's a

discussion

board that I'll put on blackboard and you can ask questions there and the reason

for

that is that that way anytime someone asks a question, everyone will get the

answer,

so it'll be the same for everyone.

So please do use that if you have questions.

You can post anonymously to it if you'd like.

So you might wonder why I'm putting the assessment up so early because in the

past it's actually

come out after Christmas.

It's not because the assessment is harder or longer this year than it has been

in the

past.

In fact, it's a little bit shorter this year.

It's not going to take you a month to do it.

I'm putting it up for the reason I explained in the first week, which is that

different

from last year, it's now become the case that a lot of the publicly available

AIs can do

a lot of the questions on the assessment or at least help with them.

I'm not requiring people to use AIs.

I'm not even encouraging you to use them, but I also can't forbid you from using

them

because I can't detect it if you do, so it wouldn't make any sense to do that.

So I imagine some people will.

If you're going to, I would encourage you to do the problems yourself first and

at most

use it to check your work because if you just pump the questions into the AI and

hope that

it comes out with the right answer, it may mislead you.

There were people last year who used AIs to get help on the assessment because

it wasn't

forbidden and in some cases it actually misled them rather than helping because

it may give

you an answer or it may give you steps to get an answer and if you just trust

what it

gives you and paste it into the exam, you won't do well.

So definitely, I would say at most, use it to check your work.

But if you do use it to check your work, that's fine.

The reason for putting it out so early is that a lot of you will go home over

Christmas

and different AIs are available in different countries and I don't want to have

some people

going home to someplace where they don't have access to the same things that

other people

do and then it's not fair for those people.

So I'm putting the exam up now so that everybody has at least a week to look at

it before they

leave plus whatever time after they come back.

So hopefully it won't be difficult.

The exam's not meant to be difficult and hopefully that will be fair for

everyone.

Does anybody have any questions about that before I...

Yeah, it's due the first day of that exam starts on the 9th of January, so yeah.

But it's not going to take you a month, so okay.

If I'll, yeah, again, I'll answer questions on that on the discussion board if

people

have them going forward.

So statistics is a really interesting thing because the more you do, the more

you realize

that you don't know.

I learn new things about doing statistics every day and I've been doing it for a

long

time and the more things I learn, the more I realize that I have left to learn.

So you can really get into, it's a dangerous trap to start to rate your progress

by what

you don't know because you'll just feel worse and worse as you go on.

So it's useful to step back, it's at a point in the semester like this and think

about

the things that you know now that you didn't know four weeks ago.

So four weeks ago you opened R, most of you for the first time, you got a blank

screen

and had no idea what to do with it.

And now people are importing data, the basic commands that you use every day

you're able

to use without much difficulty.

You can interpret things that come out, you probably haven't memorized all of

the little

bits of syntax but why would you?

You've got better things to do with your brain than memorizing syntax, you can

look that

stuff up.

But you can do a lot of things that you couldn't do four weeks ago.

So it's worth stepping back and thinking about what you've learned and how well

you're really

doing because I'm impressed with how well people have been doing on the unit.

Before I talk about things that I want to talk about this week, does anyone have

questions

about anything up to now?

No exam, just the take-home assessment.

It will be a problem set, a little bit like the practicals, but it will have

things from

each of the lectures.

So from all six of the weeks there will be problems where you can use things

from each

of those.

There's a practice one on Blackboard right now if you want to see the general

format

and the real one will be up tonight.

It's counted into the whole toolkit mark.

It will be the 9th of January.

It won't take a month, it's shorter than that.

Well it's not really short but it's not a month.

It might take a day, it could take a day or two.

It's about the same length as a practical, as many as you want.

So you can submit it and then you can change it and submit it again.

I'll mark the last one you submit.

The last one.

So if you get it all right the first time and then change it and get it all

wrong, you're

still stuck with the last one.

I'll only see the last one.

So I'm going to change a little bit the way I've approached this over the next

two weeks.

In the past few weeks I've talked about the things we did the week before and

I'm not

going to do that this week because there's not that much to say about chi

-squared tests.

They're pretty straightforward.

And the next two things that we'll do, logistic regressions and mixed models,

are conceptually

interesting so I want to spend a little bit of time talking about those.

So I'll talk about those in advance so we get a chance to do that.

And to motivate that, I'll introduce a data set.

So I'm just going to import the data using this read CSV command that we've seen

before.

This command is really important.

So there are a few people who are still struggling with importing data and if

you are, please

talk to me or the demonstrators in practical today to work on that because

importing the

data is really important.

And once people have got that, they seem to be doing pretty well but, okay.

I'm going to use this read CSV command to import a data set and then we'll look

at what's in it.

The data set that we have here is data that researchers collected on parasitism

in baboons.

So you probably know baboons are, they're apes, primates, and they live in

troops.

So they're groups that can be as small as sometimes 10, 15 individuals but all

the way

up to hundreds in some cases.

And like many wild primates, like almost every animal, they have parasites and

the researchers

in this case were interested in whether the parasitism in baboons depends on the

size

of the troop.

And we might expect that it could because you might think of baboons as, a

baboon troop

as being kind of like a net for parasites.

Baboons go out, they forage in the environment, they're digging food out of the

dirt, eating

near where they food, these kinds of things.

And so any individual might pick up parasites but once it does, it might be

fairly easy

for these parasites to spread around the troop because now someone in the troop

has these

parasites and then the parasites might be shedding eggs and other individuals

could

be picking them up.

So possibly the bigger the troop is, the more likely it is to get a parasite and

then once

the parasites are there, maybe they spread around.

If that is true, small troops might be less vulnerable to parasitism or at least

this

is a hypothesis.

So the researchers in this case were interested in testing that.

So the way that they did this was they went to the field and they observed

troops of baboons.

And so they would go out and they would find a group and they would count how

many individuals

were in it and then they would watch the animals and see when they defecated.

And then they would go and after a few animals had, they would go and they would

collect

that.

So they would never get, and then once they've collected it, they can look at it

under the

microscope and they can see what kinds of parasites are there.

And they were interested in particularly some parasitic worms.

So they can count eggs in the scat.

Because they're just watching a group for some amount of time, they never got

all of

the individuals in the group.

They would only get a handful from any group because there's only so many of

them that

would have made droppings in any particular time.

And then they have to be able to identify the droppings to the individual

because they

were also interested in the sex of the individual.

So were males different than females?

So they'd be recording the sex and have to know which animal did this.

So the data set that we've got here has this information for every scat that

they collected.

So there were almost 1,200 animals.

And you can see in the first row the sex of the animals.

This is easy to identify in baboons.

They're sexually dimorphic so you can tell the difference from a distance.

They're group size, so that's how many individuals there were in the troop.

The troop number, so this is just the arbitrary number that they give it so they

know this

one is different from a different troop.

And then these responses here, strangulae subriviata and streptophagus, are

three kinds

of parasitic worms.

And they've just recorded for each dropping were there eggs there or not.

Because if there are eggs, they know the animal is infected with the parasite.

And if there's not, then it's not.

So they didn't try to make any guesses about how infected the animal was.

So this is the data we're working with.

And we want to understand, does the infection status depend on the size of the

troop?

And this is different from what we've done in the past.

In the past, we've had data sets where our predictors are numerical and our

responses

are numerical.

Sometimes where our predictors are categories, like in this case the worms might

be categories

and our response might be some sort of number.

But in this case, we're doing exactly the opposite thing.

Our predictor is a number.

It's troop size.

So it could be anything from 20 to I think 120 is the biggest troop.

And our response is a category.

It's yes or no.

So today, we'll look at how do we analyze categorical responses with numerical

predictors.

And as is often the case, an easy way to start with this is to plot the data to

see what

kinds of things we're looking at.

So I'll make a plot so we can see what this looks like.

So here I've put uninfected and infected on the y-axis and the group size on the

x-axis.

So our predictor is on x.

Our response is on y.

By convention, people usually use one for the state that they're interested in

detecting

and zero for the other.

So in this case, I've used one for infected and zero for uninfected.

So here's what our data looks like.

But it's a little hard to see what's going on in here because in any of these

troops,

the researchers collected scat from several different baboons.

So in a lot of cases, we'll see lots of dots on top of each other.

So it's hard to tell what's really going on in this data set when it's plotted

this way.

So I'm going to add a new feature to this figure.

I'm going to add dither.

So dither is just a little bit of variability around the y variable, in this

case, around

infected and uninfected, so the dots aren't all stacked on top of each other.

And so I've just added a random number to each thing.

And we'll see something like this.

So at a glance, it's hard for me to tell whether there's a pattern here.

I'm going to zoom in and see if we can see it any better.

But no matter how big I make it, it's a little hard for me to tell.

And maybe, maybe there's a few more dots out here than down here.

But I mean, it also looks like maybe there's more here than there.

So by eye, I can't really tell what's going on here.

So how do we handle this?

Well, we might be tempted to slap a line through this, just like we did for

linear regression.

And we could try to draw a line of best fit through this data.

But there are problems with that.

The line is meant to be, the line of best fit is meant to be a prediction.

But a line that goes through, like a slanted line through here, isn't going to

be a very

good prediction, because our responses are always one or zero, they're either

infected

or they're not.

And so if our slanted line says 0.5, the animals aren't 0.5 infected.

They're either infected or not.

We might think of our line as a probability of infection.

But that's problematic too, because if we imagine a straight line, if it goes

far enough,

it's eventually going to pass one on one side and zero on the other.

And we can't have probabilities that are greater than, greater than one or less

than zero.

So that doesn't really make sense either.

So we need to do something different with this.

We might want to fit a curved line through it.

And that's what we'll, that's what we will do.

So as an example, we will fit, oh, that is not good, I'm going to shrink that

for a second

so we can get better pictures.

That makes that a little bit more visible.

So we can imagine fitting a curved line through this data.

We might have a, so in this case, we'd be saying that for low, maybe population

size,

the probability of infection is low.

And for high, it's high.

But it doesn't cross zero or one.

It just approaches zero and then gets slowly closer as the numbers get bigger.

So we might think about this curved line.

And the function that we can use for this is what we call a logistic function,

right?

So which is where this particular kind of regression gets its name.

So this is logistic regression.

And it's based on this function that's in the bottom right in this figure,

this one over one plus the exponent of the opposite of z.

So if we imagine that z is this thing on the x-axis, as z gets very small,

the exponent of, as z gets very small, the opposite of z gets very large.

So the exponent of the opposite of z gets very, very large.

And this thing becomes one over a very big number, so it's going to zero.

If we go the other way, if then as z gets large,

the opposite of z becomes a very big negative.

So the exponent gets very close to zero, and this thing approaches one.

So this creates this curve here.

And when z is exactly zero, the exponent of zero is one.

So this thing is one half, so we're exactly halfway in the middle.

So this function will create a curve that we can fit to this kind of data,

which is binomial data, where our responses are yeses or nos.

But there's a problem, and

the problem is that this thing on our x-axis isn't group size, it's this z.

And this function is going to always look exactly like this, right?

When z is four, the function is going to be exactly there, right?

So what we'll do is we'll fit a second function,

a regression model, where our predictor is group size, and our response is z.

So what we'll be trying to do is estimate

how this predictor z depends on the group size.

And so we call this thing z, the linear predictor, because it's a linear

function

of the parameters that we put in our model.

So it's, we call the logistic function in this case the link function,

that's linking this curve to the straight line.

So conceptually this is a little, it's a little difficult.

It took me many, many hearings of this and

a lot of thinking about it to, before I understood it.

In practice, implementing it isn't going to be that hard.

One thing I do want to point out that's important about this though.

So it, the logistic regression that produces exactly this curve,

and it's appropriate for binomial data.

But there, so it's a, this thing is, we call this a generalized linear model,

because we're converting a line to some sort of curve.

And there are lots of other generalized linear models.

We can do a Poisson regression that that converts this,

it links this line to an exponential curve.

We can do negative binomial regressions.

We can do any, there are, there are many,

many sorts, an infinite family of generalized linear models that we can do.

By putting different functions into this into this top this top figure.

And they're all generalized linear models.

But logistic regression is this specific thing.

And often it's a, if you're reporting what you've done,

this is, it's a generalized linear model, but specifically,

it's a logistic regression.

And if you tell me, I've done a generalized linear model,

I know you've linked this line to something, but I don't know what that thing

is.

And I know it could be, it could be Poisson, it could be, it could be anything.

So it's really important to tell people which one you've done,

in this case, logistic regression.

And, and I bring this up because there's some, somewhere,

someone at this university that has trained or

continues to train students to call this thing just a generalized linear model.

And then they report it and I don't know what it is.

And someday I will find that person and kill them and the problem will stop.

But until then, I, I will rant about it.

Okay, so, let's fit one.

So in principle, again, these logistic regressions are conceptually,

conceptually a little harder, but in practice,

it's just an extension of something that we've already done.

So in past weeks, we've used a, a, a model,

almost exactly like this one in line 37, a linear model,

to, to predict a response given some, some predictor, right?

Syntax very much like this.

I mean, in this case, I'm going to ask, I'll focus on just one of these worms.

I'll focus on abbreviata.

And I'll ask, how does abbreviata depend on,

the infection with abbreviata depend on the size of the baboon group?

I'm telling R here with this comma and then baboons, that the data is baboons.

And this thing, family equals binomial,

tells R that this is going to be a logistic regression.

It's a, a little, it's a little sad that they, that the that is family

equals binomial instead of family equals logistic.

That's because of the error distribution.

But if, if you, if you tell it family equals binomial,

you'll get a logistic regression.

The other slight difference here is that before our model was LM for

linear model, now it's GLM for generalized linear model.

But that's it, those are all the changes that we have to make.

And then we run this model exactly the same way that we would a linear,

a linear regression.

So I'll, I'll run one, and, and then let's look at what it does.

So here I've run it, I didn't get an error, so, so it's worked.

I can use the summary command, so as with many, many outputs in R,

if we want to see what it did, we use summary.

And, and we can look at the results for my regression.

And again, interpreting this is conceptually very much the same as

the, sorry, thanks, as the, as the linear model.

So the p values mean exactly the same thing they meant before.

So in this, this row, group size, the p value, the p value below 0.05 tells us

that there is some sort of, there's a significant effect of group size.

So the probability of infection is changing with the group size.

Then how much?

Well, that's this number in the estimate.

So this is another place that logistic regression becomes

a little bit conceptually challenging.

What, what is this number?

In a linear regression, it's the slope of the line.

In a, in a logistic regression, it's actually the, it's the slope of,

of that line, of the, of the, of the bottom line here.

But what does it mean biologically?

Well, it's what we call a log odds ratio.

Anybody spend a lot of time in betting shops?

No, no, okay, then you've probably not encountered,

you probably don't encounter odds all the time.

Everyone wants to know why there's somebody who knows odds inside and out.

If, if you don't spend a lot of time in betting shops,

odds can be a really unintuitive thing.

But the, the odds are, when, when we talk about odds,

you'll, you'll have something that says, for instance, one to four.

That says, this means that for every one time we see the,

the positive result, we see the negative result four times, right?

And the odds ratio, the log odds ratio means that if we if we

take the exponent of this thing, right, this is how much we multiply the odds

by for every for every change, one unit change in the predictor.

So, so in this case, this group, this effective group size, 0.00548,

means that for every, every time we, we add one animal to the group,

the, the prediction goes up by a factor of that, right?

So, it goes up by about 1.0055 times.

So, you, you might think, well, why, why do we need such a complicated thing?

And the, the answer is that there's sadly not something more simple.

And the reason is that if you think about, if we want to,

if we want to ask more, more directly,

how much does the probability change, that's the thing we're really interested

in, how much does the probability change per, per unit change in the group size,

for instance, it's not always the same, right, because this line is a curve.

So, for some parts, in some parts of this, this function,

maybe group size is around 60 in this case, then we're seeing a very

steep change for every new individual in the probability.

And then for, for bigger groups or smaller groups,

the change in the probability becomes smaller.

So, there's not really a simpler way to, to, to report this than log odds ratio.

So, for that reason, people often just report when you're,

when you're reporting results from a, a logistic regression,

they'll often just report the log odds ratio.

Even though it's a little bit hard for, for readers to get their heads around.

But it, it, it's a precise definition of what's going on.

Another thing that we can do is make a picture of what's going on.

So, I'll plot the baboons again.

We can add a line to this figure.

We, we, sadly, we can't do this with AB line the way that we did for

a linear regression, but we can add it.

We can add one by putting the, the function for our line

directly into this link function.

So, in this case, our line has an intercept of negative 0.4459, so it's this

here.

And then for every unit of, of group size, the, the thing that's going to be on

our x axis, it's increasing by 0.005487, 478, so that's this number here.

So here, I've just put the formula for the line, right?

Directly into the link function, 1 over 1 plus the exponent of the opposite of

z.

And if I plot that, we'll get the best prediction for the, for the response

variable.

So, as we can see, the, from the, as we knew from the, the output of the of

the analysis already, there's a slight increase in the probability of,

of infection for each additional member of the group.

Questions about this so far?

It will become more intuitive as, as you're doing it, at least it did for me.

But let me, let me ask, ask you a question then.

I just argued for a long time that the, the point of doing this is to make a

line

that's curved, and yet that line doesn't look curved to me.

So what, what's, what's going on?

Have I done something wrong?

Yeah, data set, but what if I got data set and I just put another,

I got like a variable stuff and then the logistic regression is giving me like

a really big volume of p.

Should I use it or should I just leave it?

Really big, like, like close to what?

Like 0.1.

Does that mean like, like the, the things I'm, this variable I added is not

Probably, yeah, yeah.

Usually, yeah, usually if you're, if it's very big, yeah.

So the question, the question is, what would have happened if instead of, so

group size here as a, is significant, but what if it weren't?

What if it were 0.5, for instance?

Then we have no evidence that group size affects whatever it is we're trying to

predict, and, and typically you would, you would leave this out of a model.

Yeah, exactly.

Okay, yeah, so this is, this actually is a curved line.

It's just we can't see it, because we're only seeing a tiny bit of, of, of this.

Of the figure, but if we expe, extended our axes out, we see that there is a

curve.

This function actually does curve, it's just our data is all piled up in

a little tiny section of it where it looks like a straight line.

And as someone pointed out last week,

these extended parts of the line aren't really very relevant, right?

There are no baboon groups of size negative 200.

There are none that they observed of size 400 or 600.

So, we can't really make predictions out there.

In the, in the part of the data that we're seeing, this fit is almost a straight

line.

But in, in principle, it is a little bit curved.

And you'll see today, in some of the data sets that we, we analyze,

you'll see cases where the curve actually is quite important.

Questions or, okay, I want to take this a, a step further.

Again, this is something that we, we've done before with, with linear, well.

I'll do two things.

Let's imagine that we want to make a prediction.

How many, what's the probability that baboons from a group of a particular size

are, are infected.

We can do this with the same, in the same way that we, we did for linear

regression.

We have our intercept, so in line 58, the intercept plus the effect of,

of our group size, and then whatever group size we want.

So, if I wanted to make a prediction for what's the probability that a,

an animal in a group size of 30 would be infected.

I can use the intercept plus 30 times the, the effect of individuals.

This thing creates the linear predictor.

Then I stuff this linear predictor back into the, into the link function.

And, and we'd see for, for a small group like that in a small group like that,

about 43% probability of infection.

So this is a, just an extension of what we did in, for, for regular linear

regressions.

And we can, another extension that we could do here would be to ask, for

instance, what if there's other predictors?

What if, could sex matter in this?

And we might think that it does, because for baboons the sexes behave really

differently.

The, the troops tend to be dominated by a, a single male.

And the, the females are, can be in the center of the group.

But the, the male tends to push the other male, the other less dominant males

out.

So they tend to be on the periphery of the group.

So maybe, maybe the other males don't encounter the,

the parasites that the rest of the group encounters.

So maybe the parasitism is lower in males.

Or maybe it's exactly the opposite, because in, in a lot of animals, and

especially a lot of primates, the male immune system isn't very good compared to

the female immune system.

So maybe, maybe males just aren't very good at fighting off parasites.

So we might, we might be interested in whether sex also determines parasitism

rate.

And we could make a, a plot where we've colored our points for the sexes.

So here I've, I've colored the female points red and the male points blue.

And it kind of looks to me like maybe there's more males in this,

in the bottom right, and more females in the top right.

But I, I, I still can't really tell by eye.

So if we want to test this formally, we can do exactly the same thing

that we did with the linear regression.

We simply add, in this case, plus sex to the model.

So I'm going to add, in this case I'll be asking, how does the sex affect

the probability of infection, controlling for group size?

And how does group size affect the probability of infection now controlling

for sex?

And we can interpret this model in exactly the same way.

So, so in this case the the sex M means that this is the effect of being male.

And you can see the effect of being male for

this particular parasite is strongly negative.

Males are, the log odds ratio of infection for

males is about point, negative 0.35.

So the, the likelihood of the probability of a male being infected,

if it had the same group size, is going to be the exponent of the opposite of.

So about 71%, the probability, 71% of the probability of females.

So, so the, the, the effect of sex is quite strong.

The effect of group size stays about the same, it's almost unchanged.

But there is the, it is true that in this, in, for

this parasite, it looks like males are, are less likely to be infected.

And we can do this for as many predictors as we, as we want.

Just like we did for, for regular linear regressions.

So for instance, we could add, we could ask, is there an interaction, right?

So the interaction would, would be, would tell us,

does group size affect males differently than it affects females?

Because, because it might, right?

If you, if you're males, if the reason that males are less,

less likely to be infected is that they're on the periphery of the groups.

Maybe it doesn't matter how big the group gets.

There, maybe for males, there's, there's nothing going on with group size.

And for females, there is.

So we could test this by, by adding the, the interaction term,

the sex times group size to the model.

And, and if we do, we find, well, no, no interaction, right?

So, interesting guess that maybe, maybe the effect of group size was different

for

the sexes, no evidence that that's true.

So, in this case, we're probably better off to go back and

interpret the original model, because notice that when we've done this,

the, the effect of sex and, and group size have, have, have changed, right?

We can't see them when the interactions in the model,

when there's not significant, significant interactions in the model.

So, we could go back and, and study the interaction,

study the model without the interaction in it, as our final model.

And if we wanted to, to add, if we wanted to add these

lines for this to the figure, we can do that again the same way that we would

have

done this with the, with linear regression a couple of weeks ago.

Now, in this new model, my intercept is a negative 0.282872, right?

So, so we put the, the function for the, the linear predictor in here, right?

So for, for males, it's the intercept minus the effect of being a male,

plus this effect of group size, if we're going to put group size on the x-axis.

And then we, we put that whole thing into the, into the link function, and

we'll get, we'll get the line for males.

We can do the same thing for females, it's the same same intercept, same

effect of, of group size, but no effect of being male, because they're females.

And we, we would see this line.

So these are the best predictions for the probability of, of parasitism in males

and

male and female baboons, given their group size, in this particular study

system.

So, again, in principle, in, in practice, this will be very much like doing

linear

regressions, so, so you'll be able to call in your, your knowledge of that for,

for doing.

Questions?

Okay, I want to show you one more thing, just for the purpose of illustration.

Before we, before we move to the computer cluster.

When you report your data, when, when you report your results, and

especially when you make figures, figures are about communicating ideas to,

to readers, and there's not necessarily a, a best way to do it.

Here I've made a, a scatter plot with some dither, but

we can imagine that there might be better ways to communicate this, this

pattern.

So for instance, I, I look at this, this scatter plot of points, and

I can't see anything, right, so as a reader, I might look at that and,

and be like, well, they tell me there's a line there, but I don't, I mean,

how do I know?

So, maybe there's better ways we could plot this.

So one possibility might be to take the average infection rate in each troop,

and plot that on the on the, on the y-axis.

So then for each troop, we'd have its group size, and

we'd have its average infection among, among all the observed individuals.

And we can do that.

If I plot that figure, I get something that looks like this.

And for me, as a reader, I think this is maybe better, okay?

It's, it's taking out some information.

I don't see the, the, the numbers of individuals as, as,

as much as I would in the other data set, but

it's condensed the information in a way I can see it.

And I, it almost looks like there's sort of a slope in these lines.

So, maybe this is a better figure.

But it doesn't have the sexes in it, so

I could imagine separating the sexes of the baboons out as well.

And, and if I separate them out by sex, now I've got the size of each troop on

the x-axis, but I have the proportion of the males infected on, as the blue dot,

and the portion of the females infected as the red dot.

And, yeah, maybe this looks even a little better.

I mean, it does kind of look to me like there's more blue dots at

the very bottom and more red at the top.

So, maybe this is a better illustration of the pattern we see in the data.

But I guess if I looked at this, I'd think, well, why is that red line not

steeper?

And there's all those red dots in the top right, and

it doesn't look like we go through it.

Any, any guesses about why that, why that might be true?

It, yes, it is, but why would that, why would that,

why, why would we not end up, so it looks like, and once we get, for

example, to the right of about 80, it looks like almost all the dots are above

the line.

Why does that line not curve up?

Something that's hidden in, from a, still in this figure,

is how many animals are in these groups, right?

How many animals are sampled?

What if these, these samples at the top, the, all these things that are one,

what if there's only like one animal sampled from that?

And, and it's possible.

That would make it really easy to have them all all infected or all not

infected.

So we could try even something else.

We could try scaling these points so that the, the size of the point

is proportional to the number of animals that, that were in that sample.

And, and if we do that, we see this one.

So these, these really extreme examples the really extreme

everyone infected examples are really small samples.

So they don't have much pull on this line.

The, the big ones, the, the, the big samples that are controlling this line

are the ones in the middle that are, that, that, that have some weight that,

that we can actually determine something from.

And this is a nice thing about working with individuals like this,

because we can weight the, the effect of each group by the number of

individuals,

because we're, we're studying the, the points as individuals.

And I'll use this, this figure to motivate some, some ideas next week.

So last quick plug for, for R.

One of the really nice things about R is making figures in R can be a pain.

But there, there's nothing you could do to make a figure like,

like this one in Prism or Excel or, or these,

these programs that are set up to make very specific figures and nothing else.

But in R, if you can imagine something that you want to do and

you're persistent enough to make it do it, you can make it do it.

So, so you can get some really, really useful figures that would be hard to get

in, in other code.

Okay, that's all I have to say for today.

We'll do the same, same basic plan as, as other weeks in the, in the practical.

There's a practical on on Blackboard and we'll,

we'll work throughout the demonstration as I, around to help as, as needed.

And yeah, I'll see you in the computer lab in, in a few minutes.

So I was wondering why the female is, I was wondering if the predictor and

the, is there only one, why can we, can we just use, you know, regression?

So in, sometimes people do, but the, the problem with proportion, so in,

these lines are still actually the logistic regression based on individuals.

I've just drawn the, the picture without the points.

But one problem with probabilities is that you, they're still bounded on one,

right?

So a straight line, if we, if we put a straight line through it, it wouldn't.

I just saw, oh wait, I think I can wait for you and then we can walk through it.

Yeah, you just take your things.

So, so like the logistic regression, I just saw like the training is very

interesting, it's like going to upward and then like it's at 20 points and

it's close to like, close to zero.

Yeah.

And I was thinking like, what if I, I apply like, because I know that the

equation,

and I also know like what the Z stands for, Z stands for beta zero and beta one,

like two, I call it two variables.

And I was thinking if, if, if I can differentiate like, like the, what is

regression, which means I, I want to find like the rate of change, I want, I'm

interesting on like the turning point, like when does it like going to like

slip around, so like if I got this value, I think, and if I know like the Z, if

I

know the component of Z, like the age and sex is, it is meaningful?

Yes, you could, you could definitely do that.

You could, I mean, you could regress on that line to find, to find turning

points

or, or inflection points.

Yeah, yeah, inflection points.

Yeah.

So the, like the simplest one, the main, the change in the second derivative is

going to be only at exactly at zero, but there will be other changes at

zero, but something happens.

I only know the second derivative.

Yeah.

So I think it's, well, it's infinitely differentiable.

I think I can apply it after, after next and we thought then how to.
