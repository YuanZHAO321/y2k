---
title: "EART11200 - 15-Nov-transcript"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 7/EART11200 - 15-Nov-transcript.txt"
type: transcript
---

'EART11200 - 15-Nov', automated transcript
01/08/2026
---

Okay, good afternoon everybody.

Thanks for coming.

So just to reiterate from last week,

I've not put a seats code up,

and the reason is I've been asked not to do that

for a session that's not mandatory

because we don't want to be setting off

alarms all over the university for people

coming to something that I've said isn't mandatory.

I'm gonna start pretty promptly with these

because we've got a long walk in between sessions

and I don't want to run too close to the end of the hour

if people have a lot of questions.

So again, like I said last week,

my goal for these sessions is to,

if possible, to have them be very interactive,

almost mostly question and answer sessions.

So I'll start each one by asking for questions

and then if people don't have questions,

I'll talk about some extensions from the unit

or other applications of tests,

things that we can do that aren't necessarily

core to the practicals but are useful

and I think will be helpful to you throughout your careers.

But starting before I start talking about the things

that I want to talk about,

let's start with things that you might want to talk about.

Does anyone have questions from anything from last week

or this week or about statistics in general?

Life questions, I'll try,

better to stay with stats for me.

Okay, I'll go ahead and start talking about the things

that I want to talk about today.

But at any point, feel free to interrupt me

with questions about this or other things that come up

and I'm happy to change course at any point.

Okay, so the first thing that I want to do today

is walk through just one worked example

from the practical from last week

just so that people can see how I approached it.

The answer key is posted,

so if you want to compare your answers to my answers,

that's now posted on Blackboard.

But I'll walk through this question three

that we did in practical last week.

So you may remember in the practical session last week,

you had some data sets that were morphometrical measurements

of different species of frogs from museum samples

that were taken in the US.

And each sample had 15 male and 15 female frogs

and we were trying to compare their sizes

using different measurements,

masses or femur lengths especially.

And in question three, we were interested in this species,

Dendrobatus auratus,

which is one of the poison dart frogs.

And we were interested in whether the females

are more massive than the males.

So how do we address this?

Well, going way back to the beginning of the process,

so I'm gonna start right at the start of what we did.

I'm gonna import a data set.

Now, the first thing that I've got on my code here

is a set working directory.

So I recommended when people set their working directories

last week that you copy this code into your R script.

And I've done this because I saved this data set years ago

and I don't remember where it is when I moved this file,

but R remembers it.

So I can just set my working directory from the script.

And I'll go right back to the directory

where I saved the data.

And then I can read in this data set

with the same read CSV command that we used last week.

So this is one of the commands

that you probably will memorize,

not because you have to, but by default,

you'll use this many times every week.

So here, I'm gonna read in this data set

that's called dendrobatus oratus.

It's a spreadsheet, a CSV,

but I'm gonna read it into an object called den-or

so that I know what it is.

So highlight the code, run it.

In this object, den-or appears in my environment.

And if I want to see it, I can click on it

and I can see what the data is.

So just to remember from last week,

the first column is the species.

The second one is the country where it was collected.

There's a column for sex.

And then there's these three different measurements.

Mass, which is the mass of the frog.

The femur length, which is the length

of the largest of the leg bones.

And this SLV is a snout vent length.

So it's the distance from the tip of the nose

to the base of the tail,

which can be variable because it depends

on the position of the frog.

Whereas femur length tends to be pretty consistent

because it's a bone.

It doesn't change as the frogs dry in museums.

So the question that we're interested in

is are the females more massive than the males?

And we'll do this with the t-test,

which is the test that we were using last week.

So for this, I'm gonna collect all of the female masses

with this command that you used last week.

So in this command,

the square brackets are subsetting for me.

So this is taking the data in the mass column of den or,

so it's the list of masses.

And it's taking only those values for which sex equals F.

So it'll get me the list of female sexes.

There's a list of female masses.

And I can run the command.

It hasn't given me an error, so that means it's worked,

but it's not showing me the output.

If I want to see it, I can look at it in the environment,

or I can just highlight this mass and run that.

If I put the word female mass into the console,

I'll get the list of female masses.

So we can see that they're there.

You can't see much from those by eye,

but we can see that this worked.

I'll do the same thing for males.

So now I have both masses.

And I'll just run the t-test.

So this is the thing that we were doing most of last week.

So here, we're interested in females

are larger than males.

So this is a, we have a hypothesis coming in, right?

I'm not just asking, are they different?

I specifically am interested in are females larger?

So this is a one-sided test, a one-tailed test.

And I'll ask in the command,

I'm comparing females to males,

and this alternative, greater,

means I'm asking, are the females greater?

Are they larger in this mass that I'm measuring?

And if I run the command,

we get the standard t-test output.

So this is the critical information

about this test that we've run.

In the bottom, at the bottom here,

these means are telling you the means of the two groups.

So X is the first group.

So this means that the female mean was almost 2.6 grams.

The male mean was about 2.15 grams.

So it looks smaller, but how sure are we that it's smaller?

Well, not that sure, right?

Our p-value is 0.08.

So there's nearly an 8% chance

that we could see a difference this big by chance alone.

So what do we interpret from this?

Well, there's this rule of thumb

that if the difference is less than 0.05,

we call it significant.

We think this is evidence.

If the p-value were like 0.8, 0.9,

then we'd think, okay, it looks like

there's nothing going on here.

Here, well, it's really hard to tell.

It's not impossible that we could get a difference

this big by chance, but it's also not really likely.

So people will often call this marginally significant.

We're not quite, it's inconclusive.

So how would we report this?

Now, one of the, when I looked through the practicals,

thanks everyone, by the way, who submitted practicals,

that it's really helpful to me to see

what your answers looked like so that I know

what things we might wanna talk about in these sessions.

But the ones that we got this week were very good.

So it didn't leave me a lot to complain about.

One thing that did come up a bit though

was the reporting results.

A few people just took this output from R

and pasted that onto their answer sheet

and called this their answer.

This is a report of results.

And we really can't do that in science.

In science, we need to communicate our results

to a broader public.

And a lot of those people don't code in R

and they don't read R output.

If you're, maybe some scientists do,

but especially if you're communicating

with members of the public, policy makers,

these people aren't necessarily trained

in the same programs that you will be.

So this means very little to them.

So we need to convert this into something visual

that they can use and plain English.

So I would typically report this in something like this.

My sentence for this was,

we found a margin of significant evidence

that female Dioratus were more massive than males.

And then in parentheses, I have the sizes of the two.

I might have the test that we used,

the t-statistic and degrees of freedom,

which a lot of journals require you to report,

and then the p-value.

So this really has all the information that we need

to understand this result in one simple sentence.

We know that there was a difference.

We know which way it went.

We know how significant it was.

And I have a figure to support it with a legend

because whenever you have a figure,

you'll need to have a legend that explains what that is.

Because when people read your papers,

if they just look at your figures and don't read the text,

which some readers will do

because they're trying to save time,

you want them to be able to understand what's in the figure.

So there should be a legend that allows them

to understand the figure without reading the text.

If they want the details, they'll have to go to the text.

But this is enough for them to understand

the difference that we're seeing.

So this is what I was looking for.

This is the kind of answer I was looking for

on the practical sheet.

Questions about this.

This is more or less review from last week.

Yeah, so it's because the one-tailed tests

or one-sided tests are,

if we're coming into it with a hypothesis

that's directional, we know that

if we're asking females are greater than males

or males are greater than females,

then this would be a one-tailed test.

Yes.

Yep, yep.

And the p-value will be...

Yeah, in general, it'll be larger

if you're doing the two-tailed test.

Because in the two-tailed test,

you were just asking, are these things different?

So it could be females larger than males,

males larger than females.

We don't care which way.

When we analyzed this data,

I jumped right into analyzing it

without looking at the histogram.

But let's look at what the histogram

of the data looks like.

So one of the assumptions of t-tests

is that the data is approximately normally distributed.

So this is just the mass data for the females

we just analyzed.

Do people think this is normally distributed?

No?

Why not?

Okay, yeah, so it should be.

So if we had a big data set,

we'd see a peak in the middle

and it would tail off on the sides.

So this isn't what we'd expect it to look like.

Is there anybody who thinks

it might be normally distributed?

So personally, when I look at this,

I'm not completely sure

because it's a really small data set.

If you have a really small data set,

you can get a lot of variability just by chance

and we don't necessarily see that bell curve.

So with a small data set, it can be hard to tell,

but I think your intuition here is maybe good.

I mean, it looks like something's going on.

There's this clump of small animals.

So if it's not normally distributed,

any guesses as to why not?

You might have to think about the,

this isn't a stats question.

It's more of a biology, field science kind of question.

What might be going on here

that would cause us to see this difference?

These are all females of the same species.

Why would we see clusters like this?

Might be.

Yeah, that would be the first thing that I would think of.

Maybe these three small ones on the end are juveniles.

Possibly.

And we don't know, right?

We don't have the frogs.

We just have the data.

But it's possible that those are juveniles.

And if those are juveniles,

and if the juveniles are smaller,

then our data is not normally distributed.

And that violates one of the assumptions of our t-test.

So is there anything we can do about this?

I'll actually ask two questions.

And I'll give you,

take a couple minutes, talk to your neighbor,

and see if you can,

and I'll ask again after you've had a chance

to talk to each other about this.

Two questions.

One is, is there something we can do about

this lack of normality

that will help us with an analysis?

And how does this potentially affect

how we interpret our results?

Take a couple minutes.

I'll pause for a minute,

and then I'll stop and ask people

what they think in about two minutes.

Okay, I know some people are still thinking about this,

but let's see if we've got any thoughts, any answers.

Any ideas about what we might do about this non-normality?

Solutions, magic tricks?

Okay.

You might.

What do people think of that?

Is it viable, workable?

I've seen people do that.

There's a risk, though.

The risk is that if we knew,

if we were sure that these things

on the bottom were juveniles,

then we could pull those out and ask about adults.

But we don't actually know.

Maybe they're small adults.

So possibly, if we throw those things out,

we might be throwing out information about our data,

and then we might assume that females are bigger

than they really are,

because we've thrown out the small ones.

So there's a risk there.

Okay, any thoughts for tests to do?

Okay, we could do a Wilcoxon test on this,

because a Wilcoxon test doesn't demand normality.

So we can try that.

And I've got one written here,

because I also thought that was a good idea.

And if we run a Wilcoxon,

I'll point out two things about this.

First, I've just run the Wilcoxon test

with exactly the same code that you used last week.

So this is just Wilcox test,

comparing female mass to male mass,

alternative grader, same syntax as the t-test.

When I do this, I get a warning.

Sometimes when I spit out a warning, it's a problem.

This one's not.

This one is just telling us

that the Wilcox test can't compute exact p-values with ties.

And what this means is that Wilcoxon tests,

when they compute p-values,

they do it by looking at every possible permutation

of the data.

And if there are no ties,

you can compute the p-value analytically.

We can know to an infinite number of decimal places

exactly what that p-value would be.

If there are ties, we have to estimate this,

which means that a p-value isn't precise, it's an estimate.

But it's estimated to like five, six decimal places.

So we probably don't care.

This is a warning that you can mostly ignore.

And what we see is that we get a p-value of 0.04.

So this difference, we're a little bit more sure of it

when we use the Wilcoxon

than we were when we used the simple t-test.

Now the Wilcoxon asks a slightly different question,

and I'll talk about that in the next example.

But it looks like there may be some difference

between the sexes.

Females may be bigger than males.

But what about how we interpret this?

Does this non-normality tell us something

about what this test might mean?

So I said females are bigger than males,

but what population are we talking about?

Like what females are bigger than males?

This is something that natural scientists run into a lot,

because it's really hard to do controlled experiments.

So often we end up with situations like this

where we have potentially a mix of juveniles and adults.

This is some sample of frogs from the field.

If we could be sure that the researchers

who collected these frogs went out

and randomly sampled from the frog populations,

then we could say these frogs are a random representation

of the population.

So this tells us about the species,

about Dendrobitis auratus.

But we really can't be sure of that.

These are museum samples.

What if it's easier to catch juveniles

than it is to catch adults?

So maybe juveniles are overrepresented in this data set.

A really common thing with museum samples

is that the researchers went out

and they tried to get the best ones.

They only bring back the biggest frogs,

the ones that they think are the best specimens.

So maybe this is skewed in that way, too.

So I think when we see something like this,

where it looks like there's something in this data set

where there might be potentially a bias

depending on which groups we're picking from,

we have to think really carefully

about what our population represents.

And here, I think it represents museum samples from the US.

And I'm not sure we can really extend this that much

to frogs in the field.

It might hold in the field or it might not.

And that's something we'd have to do further testing

to find out.

Questions or thoughts on this so far?

If not, I'm gonna go on to talking about Wilcoxon's.

And with the Wilcoxon,

I'm gonna use a slightly different question.

This is from a paper that was actually done

by some undergrads here at Manchester.

They were interested in,

well, they were marking flies and trying to figure out,

because people mark flies when they do experiments

and they wanted to figure out

how the marks affect their behavior.

But in order to mark them, they have to anesthetize them

because you can't paint a dot on a fly if it's flying.

So they anesthetized them either with ice or CO2

and they wanted to find out if having been anesthetized

affects their mating behavior later.

So they anesthetized these flies, they waited three days

and then they put them in small universal tubes,

a male and a female,

and they recorded how long it took them to mate.

And what they're interested in is,

do the flies that had been anesthetized,

do they mate more slowly than the ones that weren't?

So that would suggest that having been anesthetized

is affecting their behavior later.

So we can get their data,

and I'll just read this data in the same way

that we read in the frog data,

the data, I'm gonna call it flies.

This is the data from Tysall and colleagues 2019.

And we can look at it by clicking on it in the environment,

but I can also run it just with this view command

and we can see the data that there is.

So in this data set, we have the date of the test,

whether the fly was a control or a treatment fly,

we have whether it mated and we have its latency to mate

or whether the pair mated and the latency to mate.

Now, we'd like to know all of the codes

in this treatment column so that we know

if maybe there were different kinds of anesthetic,

in fact, we know there were, there was ice and CO2.

We could just scroll through this column

and try to find them all.

But sometimes if it's a long column,

in this one, there's hundreds of flies

and you don't want to risk missing them.

This command unique will take that list

and it will find all of the unique entries.

So we can see that there were three types of flies

in this data set, control, those anesthetized with ice

and those with CO2 and no typos.

If there were typos, you'd see another name here.

So it can be a useful thing to do.

Before we analyze this, so I've hinted that,

I guess I said we're gonna do this with the Wilcoxon.

Which probably already tells you that I expect this data

not to be normally distributed,

but does anybody have a sense for why?

I mean, what would you expect this data to look like?

So this is a case where there's theoretical reason

to believe that the data might not be normally distributed.

Imagine that we have these flies

and they all have the same probability

of mating in any minute.

And we start with a population of N flies,

so a large number of flies.

And the probability of mating in one minute is R.

So in the first minute, we would expect

N times R flies to mate.

Then in the second minute, we would expect,

so our one minus R of the flies have already mated.

So they're out of the experiment.

And of the flies that are left,

that's N times one minus R times R might mate.

And then in the third minute,

they've had two minutes to mate.

So this one minus R squared will take out,

this will account for all the flies

that have already mated.

So we're gonna get, we will reduce,

with each step, we're getting fewer flies mating.

And if we carry on, sorry, this computer,

eventually, the same pattern will flow through

for as long as we do the experiment.

And this is what we call an exponential distribution.

So the point is not to memorize this distribution,

but just to think, when you're deciding

whether data set is normally distributed,

often there's a theoretical reason

for believing it wouldn't be.

And with this mating data, there is.

And with an exponential distribution,

sometimes you can correct it just by logging the data.

But you can't, if the data's discretized,

if you have everything piled up in this first time step,

logging it won't solve the problem.

So in this case, we really do have to do a Wilcoxon.

So to do this, I'm gonna do the same thing

that we did with the t-test.

I'm going to create a list of the latencies

for all the flies that are in the control group.

So that's this command in line 54.

So the first part of this command is telling me

I want the information for the latency column,

and then I want it only for the flies

where their treatment equals control.

And just like we did with the masses,

we can look at these if we want,

and we can see the latency and see the outputs.

And I can do the same thing for the flies

that are treatment flies.

But this time I want the flies

that are both ICE and CO2.

So I'm using this exclamation point equals,

that means not equals in R.

So I want now the latencies for all the flies

whose treatment does not equal control.

And I can get these latencies.

And then we can run the Wilcoxon just like we did,

just like we ran the t-test

or the Wilcoxon on the frogs.

So I'll ask, is the latency to mate for control flies

less than the latency to mate for anesthetized flies?

Because that's our hypothesis.

If we, and here's our, here's our Wilcoxon result.

So this is a one-tailed test.

What, what does this, what does this mean?

There's something unusual about this.

Oh, which?

I saw the p-value is too big.

Okay, it's too, okay.

The p-value is huge.

Yeah, it's really big.

So yeah, that should surprise you, right?

That's like, when you see a p-value that big,

you're like, what, this is so close to one.

What's going on here?

It definitely should make you think.

So what, what does it, what do you think?

Okay, so it, well, it, maybe.

So it looks like you'd have something this big by chance.

So the trick here, and this is something

that the first time you see it is a little,

a little surprising and hard to notice,

but this is a one-tailed test, right?

And it turns out that if you do a one-tailed test,

the p-value for the, the question of

is control latency less than anesthetized latency

is one minus the p-value of the opposite.

And the reason for this is that if we,

if we make a picture of the,

I'll explain what this is in a second.

So a Wilcoxon test is different from a,

it's different from a t-test.

A t-test is asking whether means are different.

A Wilcoxon is going to ask if I randomly choose a fly

from one group, the control group,

and I randomly choose one from the anesthetized group,

and I ask which one is bigger,

and then I do this again and again and again and again,

it's going, it's going to ask,

is the proportion of flies that are in the,

in one group, the proportion of times

that the larger fly is in one group

larger than we'd expect by chance.

So it's not actually asking about means,

it's asking about, about ranks.

Or some people sometimes call this superiority.

It's still a question, if we're looking at,

at controls and anesthetized flies,

it's still asking, is the control latency

less than the anesthetized latency?

But it's asking by pairwise comparisons instead of by means.

This blue distribution is, are the,

are the proportions of times that we might expect

the anesthetized flies to have

greater latency just by chance.

This red tail is, is the,

well this blue tail is what we're capturing

in the, in our p-value of .995, right?

This is almost all the time we expect the opposite,

and yet we see this tail.

So our hypothesis was, was wrong, right?

It's, it's definitely, it's, it's pretty clear

that it's not true that anesthetized mate,

anesthetized flies mated more slowly.

It looks like they mated faster,

which is completely the opposite of what we expected.

Now, it's a little bit, it's a little bit wrong

to just take a, I've done a one-sided test.

I've, I've computed a p-value of .995.

Like you said, it's, it's, it's weird.

It jumps out as, as my hypothesis wasn't right.

Can I just reverse my hypothesis and use the other one

and then have a low p-value?

Not really.

People do it, you probably shouldn't.

And the reason is that if you,

this is what they call harking.

You're hypothesizing after your results are known.

We already know that the p-value is gonna be small

because we can see it from this test.

So if we, if we run the opposite test,

it's not really a new hypothesis test.

It's something that, that we knew before we did it.

So it's not the probability

that we would see this by chance

because we know the probability

that we're gonna see this significant p-value here

is close to one, we've seen it.

It doesn't mean that it's not worth computing these p-values

because it does tell us something

about the pattern in the data set.

But it's not quite right to call it a hypothesis test.

But even so, it looks like, it looks like these flies

are mating, the anesthetized flies were mating faster,

which is a bit surprising.

Okay.

Questions about this.

Okay.

So this is actually something that surprised me

the first time I looked at this in the data.

Let's look at the means of the anesthetized group

and the control group.

So these are the mean latencies to mate.

And the mean latency for the control group

is smaller than the mean latency

for the anesthetized group.

But we just saw in our Wilcoxon,

that the, it looks like we had a strong pattern

with the anesthetized flies mating faster.

So these two things seem to conflict.

So what gives here?

And what is, what's wrong with this?

I'll give you a minute to think about it,

but while I do that, I'll put a picture up that might help.

These are the histograms for the anesthetized,

for the mating times to mate,

for the latencies to mate, for the anesthetized.

And those are unfortunately a little hard to see.

Let's see if I can get this, make them a little better.

Okay.

So those are the histograms for the anesthetized flies

and the control flies.

Can anybody explain why we're getting different results

when we look at the means,

or when we look at the ranks?

Take a couple minutes, talk to your neighbor,

see if you can come up with an explanation for this,

and I'll come back to it in a second.

Okay, can anybody explain or give a hypothesis

as to why we're getting really different results

from these two tests?

How about, and if not a hypothesis,

how about just a wild guess?

Okay, yeah, so that's,

yeah, you're exactly on the right track.

Why would that,

why would it flip the results in this?

Sorry, I left the screen here.

You're right, it is about,

it is about the difference between the median and the mean.

And in this data,

it turns out that the median and the mean

tell us really different things.

Because if you look at these anesthetized flies,

look at that distribution on the left.

It's closer to, it's closer to zero.

They are, it does look like most of those flies

are actually mating faster.

So the anesthetized flies are piled up on this side,

so the median for the anesthetized flies

is pushed to the left, so it's smaller.

But there's also this pillar here on the way right.

Those are the flies that didn't mate at all.

At two hours, the researchers ended the experiment

because the flies didn't mate.

And there's more of the anesthetized flies

that failed completely.

So this is dragging the mean way up.

So the median is, for the anesthetized flies, is faster.

But when we include these extreme flies,

the ones that failed completely,

which are represented by 1.20s in the data set,

the mean goes and tells the opposite story.

And this is really interesting.

Well, it's interesting in this data set

because it looks like, for some reason,

that we don't understand.

The anesthetized flies that did mate were quicker,

but then some of them failed.

So maybe anesthetizing flies doesn't affect a lot of flies,

but if they're ones that are kind of slow anyway,

it pushes them to complete failure, possibly.

We don't really know.

This is a take-follow-up work.

But from an analysis point of view, it's interesting

because it really illustrates very clearly

that t-tests and Wilcoxon's aren't the same thing

and they're not asking the same question.

So people will often think that,

so if you can't do a t-test, you just do a Wilcoxon

and it tells you the same thing.

It doesn't.

It's a different story.

It's still telling you something

about how these flies compare,

but it's not the same information.

And it's worth keeping that in mind

because people, even experienced researchers,

often ignore that and often miss that subtlety.

Okay.

Last question for you.

If you were, this is a hard one,

but what if we really cared about the mean?

And what if we really wanted to compare the means

and median is not good enough for whatever reason.

We want to know the means and we want to know

if the means are different in these datasets.

Any thoughts on how we might do it?

So very quickly in the handbook,

there's mentioned a test that we don't work on implementing.

It's called the Monte Carlo test.

And the idea with the Monte Carlo test

is that if there were really no difference

in the latencies of these two groups,

then we could create a null distribution

by just randomly assigning latencies to anesthetized flies

and latencies to control flies,

make a random assignment,

compute the difference in this random assignment,

we can compute the difference in mean,

we can compute the difference in median,

we can compute the difference in variance,

anything we want.

And then we can do this again and again and again

to create a distribution of things that we might have seen.

And then we can compare that to our observed distribution.

And I'm going to show you this

for comparing the means in this group

without going into the details of how it's done.

The reason that we don't teach it in the unit

is that you have to write a lot of code to get it to work.

But it's a very flexible test

because you can use it for almost any kind of weird data

that you have.

And it really can tell you about the specific things

that you're interested in.

In this case, this distribution,

these are the differences in mean latencies

that we might have seen just by chance

by randomly reassigning flies among groups.

The observed differences are these black lines.

So we almost always see differences

at least as large as the observed difference.

So we don't really have any evidence

that these means are different.

And I show this not because I expect anyone

to learn this test,

but just because it's useful to know it's available

because it's something that you can use.

People sometimes also refer to this

as a nonparametric test

because unlike the t-test,

the t-test computes, it will compute means,

it computes variances and it works from those.

This doesn't compute anything except your test statistic.

So there are no parameters.

It won't tell you about variances, for instance,

unless you specifically compute them.

But the, so it doesn't give you as much information

about the thing that you're analyzing,

but it does tell you about differences between groups.

So it's a useful thing to know.

Okay, that's all I have to say for now.

When we go to the practical session,

we'll look at a test that allows us

to compare the means of multiple groups

and that's the ANOVA test,

implemented in a way that's not that dissimilar to t-tests.

And again, we'll, demonstrators and I will come around

and help you as you work through it.
