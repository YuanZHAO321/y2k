---
title: "Statistics for Natural Scientists L2P1"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 7/Statistics for Natural Scientists L2P1.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

- Asynchronous Lecture 2 Part 1

**Notes:**

***Hello. Thanks for tuning in to the second asynchronous lecture of for this unit. This lecture accompanies the handbook Chapter 3: Comparing the means of more than two groups.

## Slide 2

### Heights of 38 male and female students in the field course prep unit.

**Notes:**

Last week, we considered ways in which we can compare the means of two groups. In our example, we looked at the heights of men and women in a class at the University of Manchester. We found that, on average, men were 10 cm taller than women. We used a Monte Carlo analysis to show that, if there were really no difference in the heights of men and women in the population, then we would be unlikely to see a difference this large in our sample due to chance alone. Then, we used a t-test to show the same thing. So, we concluded that men really are taller than women among students at the University of Manchester.

## Slide 3

### The t-distribution approximates Monte Carlo outcomes.

**Notes:**

The figure in this slide illustrates the idea behind both approaches. We can use a Monte Carlo analysis or a t-test to find the distribution of differences that we might obtain by chance alone if our two groups were really not different. Here the blue distribution is from Monte Carlo samples, and the green line is a t-distribution.

Then, we plot the difference in the observed data on the same axis. In the blue area, the difference we obtained by chance was smaller than in the observed data. In the red areas, the difference we obtained by chance was larger than in the observed data. Since the red area is small relative to the full histogram (here 0.0038), we know that a result this extreme is unlikely to occur by to chance alone. So, we infer that there is something other than chance involved. That is, we infer that men and women really have different heights.

## Slide 4

### Partitioning variability

**Notes:**

But, there is another way to think about this kind of problem. To illustrate it, I will use a simplified data set with just 5 women and 5 men. Here, the red dots represent women and the blue dots represent men. The y-axis reports height.

We can calculate the mean height for these ten individuals, and I have plotted that here with a dashed line. Any given individual does not have exactly the mean height. Instead, we can think of each individual’s height as the mean plus (or minus) some amount that we call deviance from the mean. This deviance represents the part of each person’s height that is not explained by the mean.

Or, put another way, if we knew nothing at all about a person, and we wanted to guess their height, the mean would be our best guess. We call this our expectation. The deviance is the unexplained variability in people’s heights.

But, in this data, we DO know something about the people. We know that whether each person is a man or a woman.

## Slide 5

### Partitioning variability

**Notes:**

With that information, we can calculate a mean height for each group. I have plotted the group means here with dotted lines. The distance between the grand mean for the population and the mean for the group is simply the effect of being in that group. So, the grey lines in panel two show the part of the variability in the data set that is explained by the groups. We sometimes call this a “treatment effect,” even though sexes in this study probably are not treatments.

## Slide 6

### Partitioning variability

**Notes:**

Finally, we can look at the distance between each data point and the mean for its group. This is the part of the variability that is not explained by either the grand mean or by the groups. In other words, it is the variability that is still unexplained.

## Slide 7

### Partitioning variability

**Notes:**

For example, this person is this shorter than the mean for her group, and we do not know why. We call this the error.

## Slide 8

### Partitioning variability

- SStot = 235.56

**Notes:**

Now, every point in the data set has its own deviance, but we would like to be able to summarise this variability with a single number. To do that, we take what we call the “sum of squares.” That is, we square the deviance for each data point, and then we sum the squared deviance across all of the data points in the data set. Here, the sum of squared deviance is 235.56. We call this the total sum of squares, because it captures all of the variability in the data set.

## Slide 9

### Partitioning variability

- SStot = 235.56

- SStreat = 155.99

**Notes:**

We can measure the explained variability in the same way. That is, we square the treatment effect for every data point, and we sum that for all data points in the data set. Here, the sum of squared treatment effects is 155.99. We call this the treatment sum of squares.

## Slide 10

### Partitioning variability

- SStot = 235.56

- SStreat = 155.99

- SSerr = 79.57

**Notes:**

Finally, we can measure the unexplained variability in the same way. We can square the error for each point, and we can sum that across all data points in the data set. We call this the sum of squared error. Here, the value is 79.57.

When we have done this, we find that these sums of squares have an convenient property. The sum of squared treatment plus the sum of squared error adds up to exactly the total sum of squares.

## Slide 11

### Analysis of Variance (ANOVA)

- SStreat/Sserr

- observed:

- 155.99/79.57 = 1.96

**Notes:**

Then, we can compare the proportion of the variability that is explained by the groups to the proportion of variability that remains unexplained in the data. The higher that ratio, the better the explanation.

So, this is exactly the same data I showed in the last slide, but to make it a little easier to look at I have used gray bars to show unexplained variability and just one red bar to show the variability explained by each group. Here, the ratio of explained variability to unexplained variability is 1.96.

## Slide 12

### Analysis of Variance (ANOVA)

- SStreat/Sserr

- observed:

- 1.96

- SStreat/Sserr

- simulated:

- 0.09

**Notes:**

Now, we can follow exactly the same procedure we used last week. That is, we can reassign the observed heights among the groups, and we can measure the variability explained by these pseudo-groups.

This is one example of variance explained that we might get just by chance.

## Slide 13

### Analysis of Variance (ANOVA)

- SStreat/Sserr

- observed:

- 1.96

- SStreat/Sserr

- simulated:

- 0.09

- 0.57

**Notes:**

Then, we can repeat this to get another example…

## Slide 14

### Analysis of Variance (ANOVA)

- SStreat/Sserr

- observed:

- 1.96

- SStreat/Sserr

- simulated:

- 0.09

- 0.57

- 0.04

**Notes:**

And another.  And, we can do this 1000s of times. Then we can compare our observed value to the distribution of random values that we obtained by chance alone to obtain a p-value, just like we did last week.

This approach is called Analysis of Variance, or ANOVA, and it will give you the same answer as a t-test. And, it shouldn’t surprise you that it gives the same answer, because it asks the same question. What is the probability that two groups created by chance alone would have means that are at least as different as in the observed data. Intuitively, the more different the means are, the more variability they explain.

Now, since ANOVA gives the same result as a t-test, you may wonder why we need it. After all, we already have a t-test for this comparison. I will explain why this is useful in part 2 of this lecture.
