---
title: "EART11200 - 29-Nov-transcript"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 9/EART11200 - 29-Nov-transcript.txt"
type: transcript
---

'EART11200 - 29-Nov', automated transcript
01/08/2026
---

Okay, so thanks. Thanks everybody for coming

Quickly before I start people have asked a couple of people have asked about the

seats codes again. It's it's been a

Difficult to get that sorted, but I've been told that that's been fixed as of

this morning. So

and it sometimes takes like 24 hours for these things to go through but and

Hopefully that will be that will be sorted as of by by the time you're looking

at your attendance by next week

It should be you shouldn't see absences

Related to to this unit. So so hopefully that will be sorted

And if it's not then I'll chase it again, but I've been told that it's done

Before I launch into the things that I that I wanted to cover

Does do people have any any questions from from last week or anything up to now?

Hey, sorry, unless you've any objections, I'm going to do a head count sometimes

Okay, so

Was that a question just okay, okay, then I'll go ahead and talk about the

things that I wanted to talk about and

and then

If you've got questions interrupt me as we go along

Right

So

In the lectures up until last week the first couple of weeks

We looked at the lectures are organized by the types of data that we study right

categorical data and numerical data

And in the first two weeks, we looked at cases where the response variables were

numerical and the predictors were categorical

so predictors were things like

species of frogs or or sex of frogs and the responses were things like their

femur length or their

Their body their body mass, right?

So they're the the predictors are categories things that we put names on and the

responses are numbers

Last week we moved on to thinking about cases where our predictor is numerical

and our response is numerical

So we were looking at things like how does the body mass vary with the femur

size?

So in this case both both predictors are both the predictor and the response are

numerical

For that we use regression models and regression models are really in a lot of

ways

They're the core of this unit in the the core of much of what you'll do in

statistics

now and going forward because

Almost everything that you'll you'll work on many many of the models that you

you might use going forward are built on regression models

They're they're extensions of these in some way. So

they're really the probably if there's only one thing that you

Walk out of this unit feeling comfortable with regression models are would be

the best one

Today we'll look at regression models. I will take it for because they're so

important

I'm going to go back and work through an example of of

Another regression using a different data set and it's one that you will have

seen if you if you saw the recorded lectures

I'm going to use it again, but I'm going to use it for a slightly different

thing

so

I'm going to use

Data from its from a Canadian income survey in 1993 and I'll show you what that

data is in a second

But I'll read this in with the read CSV command that we've used every week

So people should be getting used to to seeing this command

And so here I'm just reading in a data set and naming it CI for Canadian income

So I run it I don't get an error

So so my data has been created and I'll look at that data frame to see what

what's in it

So this is a data set

It was that the Canadian government connected collected in 1993 and they're

interested in

Understanding wages across the country and this this particular data set was

collected in, Ontario

I've only taken a hundred people out of it because otherwise there's too many to

too many points to plot and we can't see what

What's going on? But but in the hundred and in the set of a hundred is enough to

pick up some interesting patterns

Most of the data in here is fairly straightforward

So wage was the so these are surveys

So they sent people surveys and people filled them out themselves and wage was

their there's what they reported that they were earning per hour

Age was their their self-reported age since they they reported age they were

School in this case is is education. So this is how many years of formal

education they had so in Canada

There are six years of primary school six years of

What they call secondary school so that goes through high school and then

anything beyond those 12 years goes into university

So you'll see in this in this data set

people who had

Anywhere through anywhere from just beyond primary school education all the way

through to to PhDs

so full university educations or full

Undergrad and and in some cases PhDs city was where they where they lived

The other two are a little bit more complicated. One of them is language

So for this one that this is broken down just into this the native language and

it's broken down just into English and other

Ontario was the borders Quebec. So a lot of people are native French speakers

there, but this is this is mixed

All all other native languages are mixed into one group

And then there's sex and so this was

This thing that they've called sex probably isn't and so this is a survey that

they were taking in 1993

They they sent forms out to people and and people reported that they had to put

something on this form

It's 1993. So they had two choices and they had to put either male or female

so for

Probably a lot of people they their gender matched their sex and they just put

that

Anyone who is who is was non-binary or

They would then be faced with the question. Well, what do I put here and we

don't know, right?

They there were no instructions for for people at this time. So

So maybe they threw out the survey. Maybe they they chose something

So what this thing is is probably self-reported gender

but we really don't know exactly what it is and the the take-home message for

this is in

Science we often can't get the data that we really want and in this case

it's not even clear what data we would really want and we're interested in

studying the the effect of wage of

Demographic parameters on wage, but what what do we really want to study? It's

not clear

But often we can find some surrogate that's that's close enough to get something

out of it. And that's what we'll do today

The question that I want to look at

first is

How does

age

affect wage

so the people's wages change with with their age and we might expect that they

Maybe they would because as they as they get older, they've spent more time in

their job. Perhaps they've picked up more skills

Perhaps they're they're more efficient

So maybe that maybe that justifies a higher wage or perhaps they've just gotten

themselves into positions of power where they can pay themselves more

So so maybe that doesn't justify it, but but we're interested in whether it

happened

so

So that's what we'll start by looking at

Often

The best way to to start

Trying to understand a question like this is just to make a picture so that we

can see what we think might be happening

And so I'll start by doing that

just plotting

Wage as a function of age with the with the scatterplot command that that we

used last week

And we see a pattern like this one

So

Does it look like age increases with wage increases with age

Maybe I mean certainly

Nobody was making a more than about 15

Canadian dollars an hour

Until they were in there at least their late 20s

So so it does look like maybe there's an increase but it's a little bit hard to

tell because there's this long

There's this tail at the end where the wage is low again

So

By I it might be hard to guess

So I'm going to fit a line put a line of best fit through this and I'll go back

and talk about what this

What these commands do in a second?

But for now, I'm just going to put in the line

So a line of best fit this red line is the line that

Explains most of the it's the best line for explaining the variability in the

data set

So what what this line does is it minimizes the length the distance the squared

distance between each of these points in the line

so if we look at the

The distance from each point the vertical distance to the line we square those

sum it across the whole data set

There's exactly one line that minimizes those squared distances and that's that

this line

All right

If it were higher

Then the squares on the bottom would be too high and if it were if we're tilted

in the rock in a different way

The squares in some parts of the the data set would be would become larger

So this is the best this line of best fit. It's the best explanation for the

data

But does it mean anything?

Well, just from looking at the picture. We don't know we're

What we really want to know to know if this means something is

So any any cloud of data points is going to have a line of best fit, right?

if even if these things are completely random you can draw a line of best fit

through it and

Except in a very special lucky case that line is never going to be completely

flat

So we want to know is is this line more more sloped than we would expect by

chance if the if the predictor

Age will completely unrelated to to age

How much slope would be could we see by chance and is this slope greater than

that and to do that?

We'll look at the model

So we already built a model to to get the line of best fit

But I'll go back and look at it specifically now

Here in line 16 this LM command builds a linear model and the syntax for this

Wage with the tilde age is asking how does wage depend on age and I'm telling

our

With this data equals CI that it's going to use the data. It's going to find the

data for wage and age in the data

Set CI

And I'll name this model wage LM. So I've already built this model. I did it as

part of the

before I fit the put the line of best fit because we needed that model to get

this line, but

I'll run it again. Anyway, and then

We'll look at the summary. So running it doesn't produce an error. That means

it's worked. But if we want to see the output

This summer command will do that. So this is this is our result. This is our

analysis

the most important thing the question that we're interested in is how does age

affect wage and the answer to that is in this row that's

labeled age

The first thing we can notice from this but easily is in this last column

The p-value is low and it's it's much smaller than

Than our five percent threshold. So there's an effect of age on wage

and

This estimate column tells us what that effect is

Specifically the this point one seven six seven means that for every one unit

change in

age

There's this much of a change in the response variable response variables

Canadian dollars. So

For every year older that people get

They're earning

17.6 cents more per hour 17.7 cents more per hour

That is the slope of this line, right? So so this

This estimate because it's telling us the change in the response for each unit

change in the in the predictor is the slope

The other piece of information that might be useful here or it might at least be

be interesting here is the intercept

So in general if you think about a line if you think back to algebra from from

high school

The intercept is where a line crosses the y-axis

And aligns a line crosses the y-axis when the when the X value is zero, right?

So the intercept is the expected value of the response

When the predictor is zero, so the easiest way to see that is

To re-plot this figure with a longer axis so that we can actually see the zero

line

So if I re-plot it like like this, I've just all I've done here is expand the

the x-axis

so that it includes zero I put this dotted line to show you where the the the y

-axis is and

Right here this crossing point is at the value eight point six nine Canadian

dollars

So that's that's our intercept questions

Yeah

So

Okay, so two really good points here and I'll let me answer the second one and

come back to the first one

Okay. So the second one is

Should we can we look at this R squared to tell us something?

Well, we can

R squared tells us what proportion of the variability and the data is explained

by our predictors

So in this point in this case

this

this

Adjusted R square. Well think about multiple R square. The multiple R square is

about

0.088 right so about eight point eight percent of the data of the variability in

this data is explained by age

So this this means that age is telling us something

But there's still a lot of unexplained variability in this data set ninety two

percent of the of the of

the

Variability in the data is still unexplained. So so this is what R squared means

and

R squared is an interesting thing because if you if you talk to

Physicists they look at something like it with an eight percent

Explanate explanatory power and they'd they'd like this is this is junk

This doesn't mean anything right because physicists like to get like ninety

percent on these these predictions

For natural scientists eight percent is really good. There's so much there's so

much complication in our data sets

The date percent is often often quite interesting

The other part of your point is exactly right

In Canada people don't work when there's zero years of age, right?

so

It's the intercept is a bit nonsense

And in general it's it's bad practice to to try to and to try to

Infer values outside of the range of the the values that we've observed

so we've observed values from eight people aged probably six seventeen eighteen

through to the the

Late sixties we can make inferences in there

But trying to make inferences about what people would earn as children

We wouldn't expect this line to necessarily stay straight and and even more than

that

It doesn't make sense right children don't don't work in Canada up to it up to a

point

so

The intercept isn't actually very useful

but sometimes we can make it useful and

and there's a way we can do this and the

The idea here is what we call mean centering. So I'll walk through how I'll walk

through what it does and then I'll

Well, I'll do it and then I'll and then I'll explain it a bit more. So for mean

centering

I'm going to compute the mean age for everyone in the data set

So all I've done is take the average. So the average age in this data set was

37 point almost 9

Then I'm going to compute a new variable and I'm going to call this thing mean

centered age

So I've just I'm just calling it MC underscore age

but it means mean centered age and

This thing is going to be the reported age

minus the average and

I'm calling this CI dollar sign MC age because by doing this by calling it CI

dollar sign

I'm putting this variable directly into my my CI data set and then

I'm going to use this C bind command just to put the two ages

the two things side by side

so that we can look at them and

what we what we've got in this first column is the people's true age and

The second column we've got their mean centered age

So this mean centered age it just tells us how much their age differs from the

population mean

So this first person is 40 years old

They're two point one two years older than average and this next person was 39

was 19 years old

So they're eighteen point eight years younger than average

Then I can use this mean centered age

To fit this the same model that I used before so in the in the last

Version of this model we regressed wage on age here. I'm going to regress it on

mean centered age and

I'll just plot there. I'll just produce the summary at the same time. So here's

the results

the first thing to notice here is

that

The effective age hasn't changed at all

The the estimate is exactly the same it's seventeen point six seven

The p-value is exactly the same

Our is rounded it to four decimal places this time, and it didn't before but

it's the it's the same

It is the same value, but the intercept is different

This time the intercept is fifteen point three nine so

What does that intercept mean and what is it telling us? I can tend that this

one's actually useful the so it's the

the

the age so the

So this one

the fifteen

It's the

Okay, yeah, so it's it's the wage for the average a person of average age in the

data set

So and the reason the reason for this is that now in this mean centered

data

The average we've we've set this new data set so that the average age is now

scored with a zero

And we're just and everyone else's age just tells us how they differ from the

average

So

so now

This thing actually is useful

It's right in the middle of the data set is the average age and and it tells us

the the wage for a person with average age

and

The easiest way to see this for me is to plot

figures for both

The the raw age and the mean centered age

So here on the in the top figure. I'm showing wages as a function of people's

true age and in the

Bottom one I'm showing wages as a function of their mean centered age the data

points look exactly the same

Because all we've done is move the axis

But now the intercept is moved to to a more sensible place

So a lot of times

Many times you can use mean centering to take intercepts and turn them into

something that's actually useful and interesting

If your intercept is if your raw intercept falls outside the range of your your

data set

So yeah, good good question good good good observation on this that but there's

a that

The raw intercept isn't very isn't interesting. It can be in some data sets if

we're looking at

If you're looking at something

Across temperatures that range from negative Celsius to positive we might

actually be interested in what happens at zero, but ages

Age zero is not an interesting thing

Questions are you could yeah, so

Femur length the so that the regression on femur length was is another case

where that zero isn't very interesting it because

Well if a frog has no femurs, it's it's not because it's tiny

It's there's some other reason for that so it probably doesn't fit in the in our

model

right, so so mean centering can be a sensible thing to do for that too, so I

Want to go a step further now and look at there's more predictors in this in

this data set

And I want to ask if there are other things that are affecting people's wage in

particular

I'm going to look at self-reported sex

So here I'm plotting the same data. We looked at before

But now I've color-coded these points, so we still have age on the x-axis

but these red points are for people who self-reported as as women and the

The blue ones are for people who self-reported as men and we might ask

Is there is there some effect of?

this self-reported

self-reported gender on

on a wage

And it's a little hard to tell

partly because the colors aren't as easy to see as I'd like them to be but

It it does look like at least at the very top those most of those points are

blue

It does look like maybe there's a cluster of

More red points at the at the bottom on the right

So we might ask

Did did men and women have different mean wages in in 1993?

in Canada and

We might be interested we could just ask this with a

simple

t-test right, but

We might actually be interested in something more

More nuanced than that we might want to know

for people of the same age

Did the wage differ by gender?

so the effect of gender controlling for age and

That's what we'll study in in this this next model. So building the model is is

very straightforward

When we looked at the model for the effect of age on wage

It was just wage tilde age now, we're just gonna add a plus sex to this model

so we're adding another predictor and we can do this with any number of

predictors, but

We'll do this with just one for now. So the data is still CI

and I'll still use the summary to

To look at it. Okay. So here's a result from a multiple regression. So what is

this telling us?

well

one row

the top row age is

still

Still significant. In fact even more significant the p-value is dropped by an

order of magnitude

The slope has changed a little bit it's a little bit steeper it looks like

people are earning about 21 cents more per hour

But there's also an effect of sex now I didn't tell our

whether to choose

Men or women as the baseline sex so it's going to

Choose in its own way and it does this alphabetically so F comes before M

so it's chosen to make to make women the the baseline sex and it's told me which

one it's it's

Coding for here by by pending this M to the end of sex. So this is the effect of

being male in the data and

What this is showing us is that there's a very strong effect of sex on wage on

in Canada in 1993

Specifically

It looks like men were earning

$5.07 more per hour. So there's still an intercept up here. But again, this is

at age 0

So it's it's it's maybe not very interesting

so it's easier to see this again if we if we plot these results and

I'm going to plot them

With these a beeline commands and to show you what they do. Well, I'll collect

this coefficient table from the from the output

This is telling me the these values here are

The values from this this table the intercept is this 4.27 a this is the effect

of age and the effect of sex

And then this time I'm going to use the a beeline command the format that I'll

that I'll use for this is the a beeline

And I'll put in the the intercept and then the slope

so for

females

The intercept is the is the overall intercept this 4.27. So it's the

The first number from our coefficients table and the slope is the the change

with age

So that's this second value from the coefficients table and I'll add this as a

red line

And then I can do the same thing with

to add a slope for men

the difference is that

Men have the same intercept, but there's also an effective age of effective sex.

So for every man earns

$5.07 more

Given the same age as females so we can add this to the intercept and plot plot

the line for

for men

So our model this is what our model is predicting

It's telling us there's a significant difference between the ages of between the

wages of men and women

There's a significant change with age and in this model. These two things are

additive

each one is controlling for the other so

Given a particular age at age 50

Men are earning

$5.07 more same thing at age 20

It's giving us the same the same difference across the whole across the whole

range of values because these are this is an additive model

questions about

This part. Okay, so I'm going to move on to I think the one of the most

important ideas from from last week and also one of the one of the ones that's

Hardest for people to understand the first couple times. They see it. This is

the idea of an interaction

An interaction means that the effect of one predictor

Depends on the value of another

So in this case we might think and if we look at this data we might think well

Is it true that?

The effect of that wages change with age the same way in the sexes

Because it it might be but it kind of looks to me like there's a lot of red

points in this bottom, right?

So what if maybe the wages for females aren't going up at the same rate as they

are for for men

So when we include an interaction in the model

We can do this by adding a multiplicative term

so in this case

I'm going to add we're interested in the effect of age the effect of sex and

Whether agents whether the effect of age differs by sex

so I'm going to add age time sex to the model and

Run the summary and we get it our result

It's a very clear result age

Time sex in that age time sex column the p-value is very low so the effect of

the effect of age on wage

Differs between the sexes. I'll plot that and then and then come back to

To think about the model

So

What I'm plotting this time is is what we see in the in the model output

When there's an interaction in the model

so the the this age time sex is telling us that there's an interaction when

there's an interaction the

effects of the main effects are

Reported for when the other predictor is at zero

so

the effect of age is

Reported for the sex that's coded as zero the baseline sex

So this effect of age that they're reporting here that it's reporting here is

the effect of age on wages in women and

The p-value is point nine eight

so in this data, we have no evidence that

wage was changing with age in women the effect of sex is

how the how the wages of the sexes differ at

When the age is zero, so this one is actually telling us that

You might be surprised to look at this and see this is negative for men you

think well

We just saw in our other data set. It looked like men were earning more

Why are the why are they suddenly earning less in this model? Well, it's because

This effect is reported at the intercept and if we look at where these lines

would go back at the intercept and

The the wage for females isn't predicted to change the wage for for men is

Going up which means as it goes back to the intercept it goes down

So by the time we get back to the intercept, we'd see that

that

at age zero

Women are earning more than men. But as you pointed out, it's nonsense right at

age zero

There there is no that we can't we can't extrapolate the data to that point the

in the

The

The interaction is telling us how the effect of of age

Differs for men. So in this case

While while there's no change in the in the effect of in the wages of women with

age

For every year of age men are earning about 38 cents more per hour

At least in this data. Does that does that make sense?

Questions

Yeah, yeah, it would um, so

Yeah, that's that's a okay. That's a good observation. Um, I'll do that in just

a second

so

to do this I'm going to

Just go back to the the same model that we had before

and

I'm going to make this mean centered age and

Let's see, let's see what we got

Right I

Didn't change it in the intercept. So I'll have to change it in the intercept

and the and the main effect

So now we see same effect of sex

or same same interaction

same same effect of age for the baseline sex, but

The effect now this this difference is for the for people at the population mean

age

It's slightly difficult

to

To interpret if you have an interaction in the model, it becomes more difficult

to interpret main effects

Mean centering helps in this case. We know that

because we've mean centered we know that this is the effect of

The effect of age at the population mean

This quite but this question about whether the effect of the effect of sex is

significant

becomes a little bit of a

It becomes not a completely meaningful question because now that we've done in

this specific case at at the

Population mean there's a significant difference between between the wages of

men and women

But if we were to look over in this part of the data set

It's not different. All right, so

Once there's an interaction it it's not always sensible to ask any more

Just strictly do men or more than women because the answer is well, it depends

depends on how old they are

For old men seem to earn more than than older women but

At younger ages

There's there's not a clear difference

questions or thoughts, so I want to take this one step further and

Build a model that uses all of the information we have or at least most of it

One of the really nice things about linear regressions compared to t-tests is is

that we can put in multiple predictors

right, so we were interested in

In the last model how how does?

How does wage change with age and sex but we could also ask if we could also

control for language and education

And we could even include we could even ask at the same time

Does the effect of age education differ for the for the for the sexes in in the

wages and

and to do this we can simply add these extra terms to the model and so I'll do

that and and and

Show the model result. So now it's a it's a big cumbersome model

It's a little hard to interpret because there's a lot in it

But one thing that we can notice is that now we have an interaction that's not

significant

We have this interaction of between

sex and education and it there's no evidence for

That that that that introduction is real. In other words, there's no reason to

believe from this data that

Education affected the wages of men and women differently

But when that interaction is in the model it becomes harder to interpret the the

main effects for

for everything else, so

Typically if we have an interaction that's not significant

The best thing to do is remove it. So I'm going to refit this model with that

interaction removed and

Now the other patterns change a little bit and become a little bit clearer. So

we still have

this interaction between age and in sex

We see specifically it looks like men are earning about

36 cents more per hour per for each year of age

Whereas for women there's there's no evidence of a change of in wages with age

We can see that there's a big effect of

education for every additional year of

Education people were earning about 90 cents more per hour and that's across

both sexes, right? So there's no

There's no

No interaction with with sex

we

These these are this effect of age looks like it's not significant, but we can't

pull it out of the model because it belongs in

It's in this interaction with age. We might ask

For language we have really no evidence that it affects wages at all in Canada

in 1993

So we might ask well, should we leave this in the model or should we pull it

out?

That's a that's a decision that you would want to make based on your

understanding of the system

If you think if we really think that

Maybe we know that in other provinces

Your your native language affects your wages. Maybe we'd want to leave that in

we might want to control for it

Even though we don't see a significant effect here

if we've done this across other provinces and and and found out that it

There there really is no effect anywhere. Then this might just be noise and we

might just want to remove it

There's really not a wrong answer here. It's something that you'd justify in

In the explanation of how you analyzed your data

But in this case, I'm going to leave it in

It's also not going to matter very much because the effect is very small

Plotting this would be much harder because now we have two

Numerical predictors we have your expected wages change with your education and

they change with your

With your age if you're at least if you're you're a man

so

We'd need to plot this in we'd need three dimensions to plot it and it becomes

much harder to represent

But people will often represent these things in in tables because it's it's easy

to see

Okay questions about

Yeah, yep

You can yep and it it becomes increasingly difficult to understand, right?

People can just kind of get their heads around it

If you put it if we did this if we did it with three like you like you said

English-speaking English-speaking white men

You you would and I think you could probably get an audience to understand that

if you put four in there

They just cry it becomes really hard. But

But in practice, yes, you could you can have

the in in that if we did that we would we'd be allowing that any combination of

Of self-reported gender and native language might have a different slope

and you can do it with continuous predictors to it so we could have an issue a

question of

Is there an interaction between

education and age and

And sex and that becomes

quite hard to understand because we'd be asking

does your

does education affect your

Wages differently depending on your sex depending on how old how how how old you

are and and then they become harder to understand

but sometimes you need them because sometimes that's the only way to model

things other I

Do want to just point out in passing here that I really like this data set

because it's it's a it's really interesting set to use

but I'm not putting this I'm not

making the argument that

This is the way it should be right. This is

Part of the value of science is that we can pick out things that are that are

wrong and fix them

All right

So a lot of science is focusing on climate change because if we can identify

these problems and understand them

We can potentially do something about it and the same thing is true with with

with societal problems

We we might look at a situation if we look at a situation like this and we can

say here

Here is some evidence that that there's unfairness in the way that that wages

are distributed then then potentially we can

Get politicians or or or other business people to do something about it

In this case, it's an interesting and there's an interesting pattern because it

looks like the effect of

The effect of age on wage differs in the in the sexes, but so for older

for people who are older

Men are earning more and women are not but for younger people men and women are

in the same

So we might actually think that

Well, this is going to work its way through the through the system and and these

younger people as they get older are going to

progress at the same rate and this problem is going to solve itself in 30 years

because

yes, there's this relic of people from from 30 years 30 years older who are

still getting paid less, but

But if we look at the young people it it's all it's all balanced out

This is just this is just going to work and in fact, that's exactly the argument

that people made

And it's exactly the argument that they're still making today because this is 30

years ago

And if we look at the pattern, it's still there. So

so it's not solved but

but being able to point it out is

And being able to provide evidence for it as scientists is something that we can

can do to press. Yeah. Yeah, so, okay

you you can and

and

And I know I was I was I was gonna skip it but I'm gonna do it because that's

that's okay

So yeah, this is a so really good observation

It does look like this data set goes up and then like this data the values go up

and then down

So maybe maybe the relationship with age is curved

Maybe people make more it when they're in and in the middle of their careers and

then and then less at the end

in the way to deal with this

Or the way to model this is to include a quadratic term in the model so

The model that we're building here is forcing it's it's a linear model, right?

So there are all these terms are linear

We're we're forcing a line through this data set

but if we had a

Quadratic term in a term that's age squared to this model then we can allow this

this to curve

So

I'll do this and and I'll do it with I'm gonna add age squared

and I'm also going to add the interaction between age squared and and sex to the

model because we think we have some evidence from

our original model that

That the effect of age depends on or the fact of sex depends on age. So I had

both of these things at the same time

and

And if we do it the first thing that we see is that

There's no one there's no evidence

That the quadratic term so the the curvature of wage is different for for men

and women

So there's a point nine in that in that bottom p value

So I'll take I'll pull that one. I'll add that one. I'll take that one back out

of the model

so removing the the interaction between the quadratic term and and and

Sex I'll leave just this quadratic term of age in the model and

Then we see yeah, you're when when we when we do that

we see

there is a

This this model we see an effective age and an interaction between age and sex

So it's still true that that manner earning now

It looks only about 24 cents per hour more than per hour per year more than than

women

But there is this this curvature

Okay

So the effect of age is not just a straight line it curves and we can plot that

and it's it's slightly uglier to plot, but if we

If we plot it what the best fit for this model actually looks like this

So

There is an increasing gap with age between between men and women but for both

for both sexes

The wages seem to go up and then and then back down

Guesses as to

Why that happens?

Yeah, you're right. You're definitely right. It was there. It's a good spot

Okay. Yeah, I think it's I think it's exactly that so so we don't we don't know

from this data set

But I think what's happening is that so I I think it's very unlikely that people

who were earning a lot suddenly start earning less

I think what happens is people who are earning a lot

Retire because they can and people who weren't people who are who are struggling

by it at the

Canadian minimum wage can't retire

right, so they they continue working and and the wages look like they tail off

because because some just because some people are there's a

bias to who's staying in the system and

That's quite possibly what's happened

it also is true that when you look at the the very tail end of the status that

is predominantly women that have stayed in the

in the in the

Workforce after 60 and that may have something to do with the the curvature

And I don't know if that's because they're actually the ones who are still alive

or or because

Yeah, or

Or because they're more in a position where they they have to be in the

workforce. This is something we can't pull out from this data

but

This kind of data these these kinds of results can send social scientists to the

field to start asking those questions

other

questions or thoughts

Okay

Very quickly

Before we head to the other

To the computer room. I want to show you one thing that we'll do today

and today we're going to work with chi-square tests in the practical and it's

Probably the shortest and most straightforward of the tests that we'll look at

over the

Over the time over the few weeks that we're doing this

So at the end of this practical there'll be some more regression models just for

for practice and there's also in this

in the code for the for the first time I've written a function and

One of the nice things about are is that you can if there's a set of commands

that you know

You're going to use again and again you can write them up in a into a function

That you can you can compile and run and then just use it to produce to produce

results

Many times so the the function that I've written here is in you'll see it in

there when you see the code

It says function starts here, but it's in line 29, and it makes a picture

It makes a tape. It turns a table into a figure and to create it so I've

Next to the next to line 29

You'll see a little a little triangle if you want to see all the all the code

that's in the function

You can leave it open and you're free to look at it

But if you want to get rid of it

You don't have to see it if you click that triangle. It'll close the function to

activate the function

you can just highlight the line and run it and

What this is going to do is it creates a figure a function that's called?

CT to bar plot and what this stands for as a continued it turns a contingency

table into a plot and so if I

if I have this function in the

It once I've created this function I can use this

CT to bar plot just like any other command

to

to make figures and then so

I'm not telling you this because I expect anyone to to write functions

it's simply a tool that will be that becomes very useful and

It's easier than making your all your chi-squared plots by hand every time so so

I've written that here if you want to use it

Otherwise, that's all I have to say we'll

then we can

give other questions we can chat in the

in the engineering building
