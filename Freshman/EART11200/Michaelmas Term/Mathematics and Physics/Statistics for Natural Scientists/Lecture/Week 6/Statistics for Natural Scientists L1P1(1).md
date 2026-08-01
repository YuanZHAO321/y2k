---
title: "Statistics for Natural Scientists L1P1(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 6/Statistics for Natural Scientists L1P1(1).pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

- Asynchronous Lecture 1 Part 1

**Notes:**

Hello! Thanks for logging in to the first asynchronous lecture in Statistics for Natural Scientists. In chapter 1 of the unit handbook, I argued that Science is about comparing ideas to evidence. In the remaining five practicals in this part of the toolkit, and in handbook chapters and lectures associated with them, we will explore a set of methods for doing that. Those methods belong to a family of tools called frequentist statistics.

## Slide 2

- The Super Bowl XLIII Coin Toss

**Notes:**

I will lead into this idea with an example. As you have probably already guessed from my accent, I am not British. I was born and raised in the US. The most watched sporting event in the US is the Superbowl, and some of you may know that the Superbowl starts with a coin toss.  That is how they decide who gets the ball first.

The Super Bowl coin toss is a big big deal. It does not predict the winner of the game. But, people bet on it. This year more than $4 billion were bet on the Super Bowl, and almost $40 million of that was bet on the coin toss. That is a lot of money.

## Slide 3

**Notes:**

Now, the coin toss is such a big deal that they mint a new coin for it every year. It is a very special coin, which is why the person in this picture is holding it with gloves. The Superbowl coin is only ever used once, for this one flip. Then, they whisk it away to the football hall of fame in Canton, Ohio and put it in a glass case where people can pay money to see at it. Americans are very strange people.
 
But, something you probably know is that not all coins are fair. A clever coin maker can weight a coin so that it is more likely to come up on one side than the other. And, with so much money bet on this one coin flip, someone who knows how the coin will land could make a lot of money. So, an interesting question to ask is, is the Super Bowl coin a fair coin?

There is a simple experiment we could do to find out. We can flip the coin. So, let’s imagine the NFL were to let us do that. It is a special coin, so they are only going to let us flip it 100 times. That is a constraint of the experiment. So, we flip the coin 100 times, and we get 62 heads. What does that tell us? Is that evidence of anything?

Well, just from the data, it is hard to know. We got more heads than tails, but maybe this is just chance. After all, it seems unlikely that we would get exactly 50 of each. So, how can we assess our evidence?

## Slide 4

### What would we expect from a fair coin?

**Notes:**

Well, one thing we might try is to compare our results to the results for a truly fair coin. If we flip a fair coin, and we often get heads 62 or more times in 100 flips, then getting 62 heads in our experiment probably doesn’t mean very much. It could easily happen by chance. But, if we almost never get 62 heads by chance, then that suggests that our observation is not just chance. And, if the result is not likely to happen by chance, then that suggests that the coin may be weighted.

## Slide 5

### What would we expect from a fair coin?

**Notes:**

Now, normally, I would pass out some coins and have everyone flip them to see what happens. But, since we are doing this online, I am going to simulate these instead. I did this simulation in R, but don’t worry about that. For now, just look at the numbers of heads. Here, each filled circle is a head and each open circle is a tail, and the number on the right is the number of heads in each set of 100 flips.

So, in the first 10 simulations, we never got even close to 62 heads. But, 10 is not really enough samples. So, what happens if we do this 1,000,000 times.

## Slide 6

### What would we expect from a fair coin?

**Notes:**

When I did this 1,000,000 times, I got 62 or more heads 10,510 times, and 62 or more tails 10,470 times. So, altogether, in 20,980 out of 1,000,000 trials I got the same result at least 62 times. That is about 2% of time. So, the probability of getting the same outcome 62 or more times from a fair coin is only about 2%. That suggests that our coin is not fair.

## Slide 7

### The fundamental question of frequentist statistics:

- What is the probability that we would obtain a result at least as extreme as in our observed data by chance alone?

**Notes:**

So, this brings us to the fundamental question of frequentist statistics. “What is the probability that we could get a result at least as extreme as in our observed data just by chance alone?” We call this probability a “p-value.” If the p-value small, then we have evidence that something other than chance is going on in our data. We call this statistical significance.

So, what do we mean by small? Well, most scientists agree that p-values less than about 5% are evidence of something. But, there is nothing magic about that 5% number. It is simply a convention.

So, I encourage you to pause this lecture and think carefully about this question and why it matters. If it is not clear, go back and listen to this section again. Because, everything we will study from here forward will be about answering this question for some particular kind of data.

## Slide 8

### Heights of 38 male and female students in the field course prep unit.

**Notes:**

Now, the coin-flipping example is a bit contrived. Most data that we might look at is both more interesting and more challenging. Here, I am showing you a real data set. These are the heights of 25 women and 13 men in this unit in a previous year. Women are in the first column, men are in the second, and their heights are on the y-axis. The red bar in the middle shows the difference between the mean height of men and the mean height of women in the data set. On average, men were 0.1 meters taller.

But, is this evidence that men and women really have different heights in the population as a whole? After all, any time we collect two samples from a population, those samples will be at least slightly different. Is the observed difference greater than we would expect to see by chance alone?

We can find out in the same way we tested our coin-flipping data. If there were no difference in height between men and women, then there would be no reason to expect the taller people in our data set to be men. So, we could combine all of the people in the data set into one group…

## Slide 9

### Heights of 38 male and female students in the field course prep unit.

**Notes:**

and then, we could randomly select 25 of these individuals to be “pseudo-females” and assign the other 13 to be “pseudo-males.”

## Slide 10

### Heights of 38 male and female students in the field course prep unit.

- pseudo-

- pseudo-

**Notes:**

and we could ask what difference we see in this randomized pseudo-data. So here, our pseudo-males are taller than our pseudo-females, but not by as much as in the observed data.

## Slide 11

### Heights of 38 male and female students in the field course prep unit.

- pseudo-

- pseudo-

**Notes:**

And we can do this again…

## Slide 12

### Heights of 38 male and female students in the field course prep unit.

- pseudo-

- pseudo-

**Notes:**

And again… notice the negative sign this time – this time our pseudo-women are taller than our pseudo-men…

## Slide 13

### Heights of 38 male and female students in the field course prep unit.

- pseudo-

- pseudo-

**Notes:**

And again.

## Slide 14

### Differences obtained by chance alone

**Notes:**

So, let’s make a histogram of what we have done so far. Three out of four times, our pseudo-men were taller, and once our pseudo-women were taller, but the difference was never as great as in the observed data. But, four trials is not enough. To really understand this, we might want to do 1000 trials, or 10,000. And, with a computer, we can easily do that.

## Slide 15

### Differences obtained by chance alone

**Notes:**

Here is a histogram the results after 10,000 trials. In the blue area, the differences we obtained by chance were smaller than in the observed data. In the red areas, they were greater. And the red areas are only a small proportion of the trials. In fact, they were 46 out of 10,000 trials. So, our p-value is 0.0046. We have evidence that the difference between men and women in our data set is not just due to chance. That is, we have evidence that men and women have different heights, on average, in the population.

We call this analysis a Monte Carlo analysis, after the famous gambling city, because we generated our distribution of possible results by chance.

Now, I want to pause here to introduce an important, but (for me at least) a difficult, idea. This is the idea of one-tailed and two-tailed hypothesis tests. The question we just answered is, do men and women in the population have different heights. The observed difference was 0.1 meters. So, any time the simulated difference was greater than 0.1, then the simulated difference was greater than the observed difference. That could be because pseudo-men were taller by more than 0.1 meters, as in the upper tail of this distribution, or because pseudo-women were taller by more than 0.1 meters, as in the lower tail of this distribution. So, the p-value is the sum over both tails. We call this a two-tailed test.

However, we could have asked a different question. We might have started this experiment already suspecting that men are taller than women, perhaps based on our past experience. Then, our question might have been, not do men and women have different heights, but, are men taller than women? In our observed data, men were taller than women by 0.1 meters. In the upper tail, pseudo-men are taller than pseudo-women by more than 0.1 meters. So, the simulated difference is greater than the observed difference. However, in the lower tail, pseudo-men are not taller than pseudo-women at all. So, the simulated difference is not greater than the observed difference. Thus, in this case, our p-value should include only the upper tail. We call this a one-tailed test.

For me this is a very difficult idea, and it took several readings (and in fact several years) for me to really understand it. So, don’t worry if it is not intuitive right now. But, I encourage you to revisit the idea in the handbook.

## Slide 16

### Differences obtained by chance alone

**Notes:**

The two examples I have talked about so far are meant to illustrate the logic behind hypothesis testing. In next part of the lecture, we will consider some ways to implement hypothesis tests.
