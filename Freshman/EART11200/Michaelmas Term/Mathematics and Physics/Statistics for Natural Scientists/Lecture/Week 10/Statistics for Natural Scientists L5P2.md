---
title: "Statistics for Natural Scientists L5P2"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 10/Statistics for Natural Scientists L5P2.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 5.2: Categorical responses to numerical predictors (an example of logistic regression)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

Hi everyone. Welcome back to lecture six. This is the last section of the last lecture of this unit.

In the last section, we considered the ideas behind logistic regression. In this section, we will walk through an example.

## Slide 2

### Mate preference learning in the Bengalese finch

- Lonchura striata var. domestica

**Notes:**

The data set I will use for this was collected by a Manchester student named Giorgia Caspani while she was on a year in research in Kazuo Okanoya’s lab at the University of Tokyo. You can read her paper in the journal Ornithological Science.

Giorgia was interested in how animals acquire mate preferences. She studied this in a bird called the Bengalese finch. In Bengalese finches, females evaluate potential mates, in part, by their songs.  Females tend to prefer songs that are similar to their fathers’ songs. But, there may be other factors involved in song preference. One of those is a behavioural pattern called “peak shift.”

## Slide 3

### Mate preference learning in the Bengalese finch

**Notes:**

The idea behind peak shift is that humans and animals do not always prefer exactly what our experience suggests we should like.
 
For example, imagine you go strawberry picking, and like most people, you taste some berries. You taste the one on the left, and it is not very good. Then, you taste the one on the right, it is very good. So, what you have learned is that the red color is better than than the green color.

## Slide 4

### Mate preference learning in the Bengalese finch

**Notes:**

But then, you see more berries. If you have to choose one, which one would you choose?

## Slide 5

### Mate preference learning in the Bengalese finch

**Notes:**

Well, you learned that this one was good.

## Slide 6

### Mate preference learning in the Bengalese finch

**Notes:**

But if you are like most people, you would probably choose this one, because it is even more extreme than the one you just learned was good. So, we tend to pick these extreme cases, even though we don’t have any experience with them. This is called peak shift, because our peak preference should be for the thing we have learned was good, but it is actually shifted away from that in the direction opposite something that we learned was bad.

## Slide 7

### Mate preference learning in the Bengalese finch

- Lonchura striata var. domestica

- (Caspani et al. 2020 Ornithological Science)

**Notes:**

So, Giorgia wanted to find out whether birds exhibit peak shift behaviour when they are learning song preferences.

To do this, she used a technique called operant conditioning. That is, she started by training females to like some songs and not others. She started with a male song that had an 8-note trill, and she use sound engineering software to modify the song so that the trill had either 6 or 10 notes. Then, she put the bird she wanted to train in a box with speaker. The birds were acclimated to the boxes, so they behaved normally. Giorgia would play one of the songs for the bird, and then a red peck key would light up. If the bird pecked the key after hearing the song with a short trill, it got a reward – a few pieces of millet. If it pecked the key after hearing the song with a long trill, it got a punishment. The light in the box would go out. Birds don’t like that. And, after enough trials, the birds would learn to respond to songs with short trille and ignore song with long trills.

So, we call this short song the S+, because it is the song the bird has been trained to prefer.

## Slide 8

### Mate preference learning in the Bengalese finch

- Lonchura striata var. domestica

| current song vs. last song | probability of response |
| --- | --- |
| shorter | +? |
| equal | ~? |
| longer | -? |

- (Caspani et al. 2020 Ornithological Science)

**Notes:**

Then, Giorgia tested the bird’s response to songs with a range of trill lengths. She played 120 songs for each bird, where songs had between 5 and 11-note  trills. For each song, she recorded whether the bird pecked the key. So, this is a categorical, yes-or-no response.

So, the first question Giorgia wanted to ask was, does the probability that a bird responds to the current song depend on the length of the trill in the previous song? That is, birds learned that a short trill was better than a long trill. So, are they more likely to respond to the current song if its trill is shorter than that of the previous song.

But, there is another thing going on in Giorgia’s experiment that may be important. Each bird listened to 120 songs, and had many opportunities to earn rewards as the trial progressed. At the beginning of the trial, the birds were hungry. At the end, they might not be hungry. So, maybe they stop responding not because of the songs, but because they just aren’t hungry any more. To account for this, Giorgia included each song’s place in the trial as a predictor in her model.

## Slide 9

### Mate preference learning in the Bengalese finch

**Notes:**

So, let’s start by looking at Giorgia’s data. I have loaded the data using a read.csv command, and then used the head command to show the first few rows of the data set. Each row is a birds’ response to a single song.

Starting with column 3, signal tells us which song the bird heard. The number tells us how the long the trill was. S+ indicates that this was the signal the bird was trained to prefer, and S- indicates that this was the signal the bird was trained to avoid.

In column 4, sigdif tells us whether the trill in thissong was shorted or longer than the trill in the previous song. 1 indicates that the trill was shorter, -1 indicates it was longer, and 0 indicates it was the same. So, for example, the song in the second row had a 10-note trill, and the song in row one had a 6-note trill. So, the song in row 2 is longer, and it gets a -1 in the column sigdif.

Column 2 reports the position of the song in the trial. These are scaled from 0 to 1. So, the first song in a trial gets 0.008, the next gets 0.016, and so on. The first song does not appear in the data set, because there is no previous song, so we cannot measure sigdif.

Finally, column 1 reports whether the bird responded to or ignored the song. 1 indicates the bird pecked the key. In these six rows shown here, the bird always pecked the key when it heard the 6-note trill it was trained to prefer. So, this bird seems to have learned the task well.

## Slide 10

### Mate preference learning in the Bengalese finch

**Notes:**

Okay, let’s build our model. I will call the model r.lr. This is just a name, so I can call the model whatever I want. I am using r for response, and lr to remind me that this is a logistic regression.

The command is glm, which stands for generalised linear model. Any regression model with a link function is generalised linear model. In logistic regression, the link function is a logistic function. There are models that use different link functions, but this is the only one we will talk about in this unit. The text “family=binomial” tells R that I want a logistic regression, and specifies the appropriate link function. If you ae wondering why it say “binomial” instead of logistic, it is because ”binomial” decribes the error distribution for logistic regression.

Finally, the main part of the command is the model specification, which follows exactly the same syntax we used for linear regression and ANOVA. The response is on the left, then there is a tilde, and the predictors are on the right.

## Slide 11

### Mate preference learning in the Bengalese finch

**Notes:**

So, we can execute our command, and look at the fitted model using summary, just as we did for linear regression.

So, what do we see? Well, there appears to be a strong effect of sigdif. But, the effect of signal position is not significant. So, let’s remove that before we try to interpret the model.

## Slide 12

### Mate preference learning in the Bengalese finch

**Notes:**

So, here is a reduced model. The only predictor left is signal difference, and the p-value is very low. So, we can be confident that the difference between the length of the trill in the current song from the previous song affects the response. But, how much does it affect the response?

## Slide 13

### Mate preference learning in the Bengalese finch

**Notes:**

Well, just as in the linear model, the effect size is this thing here. But, what on earth does this mean? This is what we call a log odds ratio. It is positive, so it mean that as the predictor gets bigger, the event is more likely. In this case, the predictor is positive when the current song is shorter than the previous song, and event is that the bird pecked the key. So, the bird was more likely to peck the key if the current song was shorter than the previous song. That is what we expected.

But, what does the number mean?

## Slide 14

### Mate preference learning in the Bengalese finch

- Log odds ratio:  1.88

- Odds ratio:

- exp(1.88) = 6.52

**Notes:**

For most people, the log odds ratio is not very intuitive, but we can make this a little better by converting this to an odds ratio. To do this, we simply take the exponent of log odds ratio, since exponent is the inverse function to logarithm. The odds ratio tells us how much the odds increase for each 1 unit change in the predictor. So here, the odds that the bird pecks the key are 6.52 times higher if the current song is shorter than the previous song than if the current song is the same as the previous song.

But, unless you are math genius or someone who bets on horses, that probably has not helped very much.

## Slide 15

### Mate preference learning in the Bengalese finch

- Log odds ratio:  1.88

- Odds ratio:

- exp(1.88) = 6.52

- Probability of event:

**Notes:**

So, let’s take this a step further and calculate the probability that a bird pecks the peck key. For this, we go back to the logistic function we looked at several slides ago. Recall that our predictor, sigdif, is 1 if the current song is shorter than the previous song. So, if the current song is shorter than the previous song, what is the probability that the bird pecks the key?

## Slide 16

### Mate preference learning in the Bengalese finch

- Log odds ratio:  1.88

- Odds ratio:

- exp(1.88) = 6.52

- Probability of event:

**Notes:**

To find out, we can just plug the values from our model into the logistic function. Here, 0.54 is the intercept. This captures the baseline case, before the effect of the predictor. 1.88 is the per unit effect of the predictor. We are interested in the case where the current song is shorter than the previous song, so the predictor has value 1. That is the number in the green circle. And, if we evaluate the function, we find that bird has a 92% chance of pecking the key if the current song is shorter than the previous song.

## Slide 17

### Mate preference learning in the Bengalese finch

- Log odds ratio:  1.88

- Odds ratio:

- exp(1.88) = 6.52

- Probability of event:

**Notes:**

If we wanted to find the probability that the bird pecks the key when the current song and the previous song are the same length, we just we use the same function, but now set the predictor to 0.

There has been a lot of math in this lecture so far, I don’t expect that you have learned it by listening to it. Or at least, I know I would not have learned it by listening to it. I hope though that having seen it will make it easier when you come to it in the practical. But, before we move on to the practical, I want to cover one more idea, and it is a less mathy one.

## Slide 18

### Mate preference learning in the Bengalese finch

- Lonchura striata var. domestica

| current song vs. last song | probability of response |
| --- | --- |
| shorter | +? |
| equal | ~? |
| longer | -? |

- (Caspani et al. 2020 Ornithological Science)

**Notes:**

In the analysis we just did, we asked whether the difference between the trill length in the current song and the trill length in the previous song affects the probability that the bird responds to the signal. But, there is problem with the way we did the analysis. Can you find it? Pause here, and give yourself a good few minutes to figure it out. I will explain it on the next slide.

## Slide 19

### Mate preference learning in the Bengalese finch

- Lonchura striata var. domestica

| current song vs. last song | probability of response |
| --- | --- |
| shorter | +? |
| equal | ~? |
| longer | -? |

- (Caspani et al. 2020 Ornithological Science)

**Notes:**

The problem with our analysis is that birds were trained to prefer songs with shorter trills. And, a song is more likely to have shorter trills than the previous song if it has short trills. For example, the 6-note trill that the bird was trained to prefer is shorter than almost every other trill in the experiment.

So, maybe the pattern we are seeing is not because birds are evaluating songs relative to the previous song. Maybe they just like short songs. So, how can we figure this out?

Well, the easiest way to do it is to include the song itself as a predictor in the model. I am going to treat the songs as categories. We could treat them as numbers (for example, 6 to 11, to correspond with the length of their trills), but since the birds were trained to prefer and avoid songs with intermediate trill lengths, their preferences may not change linearly with trill length. Treating the songs as classes means birds can have different preferences for songs of different lengths, and the preference does not have to depend linearly on the number of notes in the trill. If you have read the handbook, you will know that model that includes both categorical and numerical predictors is called an ANCOVA. You will also know that we can implement it just like any other linear model.

## Slide 20

### Mate preference learning in the Bengalese finch

**Notes:**

So, the command I am using here is exactly identical to the command we used to build our original model, but I have now added signal to the model. We can execute this command and look at it using summary.

## Slide 21

### Mate preference learning in the Bengalese finch

**Notes:**

So, here is our model. There is a lot going on here, but before we think about that, let’s notice that signal position is still not significant. So, let’s remove it from the model.

## Slide 22

### Mate preference learning in the Bengalese finch

**Notes:**

Now, you may have noticed that there are also some signals that non-significant effects. But, we put these is in the model as a single predictor, so we cannot take them out one at a time. So, this is out final model.

So, what does this mean? Well, among the signals listed in the output, you will notice that one is missing. That is signal 10. R has chosen that at the baseline against which it is comparing the others. So, for example, signal 6 is strongly significant and has a positive effect. That means that birds were much more likely to peck the key when they heard signal 6 than when they heard signal 10. This makes sense. After all, birds were trained to respond to signal 6 and avoid signal 10.

Signal 11 has a significant negative effect. So, birds were less likely to peck the key after hearing signal 11 than after hearing signal 10. This suggests that there might be some peak shift in response to signals.

We could try to assess the various pairwise comparisons between signals in this model, but I am not going to do that, because I don’t really care that much. My goal was not to assess the effects of the signals. It was to assess the effects of the difference between the current and previous signal while controlling for which signal the bird was hearing. And, for that, we can look at the effect of signal difference. It is still significant, but not as convincingly, and the effect size is not as large. Nonetheless, it still looks like birds evaluate each signal relative to other signals they have previously heard. And, Giorgia was the first person to show that.

## Slide 23

**Notes:**

**So, that was my last slide for the lecture, and for the unit. But, it is horrible slide to end on, so here is my dog instead.

As usual, you will find your practical in the Blackboard folder. When you start working through it, I think you will find that the practical is easier than the lecture. If you have questions, post them to the discussion board or ask me in the Drop-in session 11:00 to 1:00 on Friday. I hope to see you there!
