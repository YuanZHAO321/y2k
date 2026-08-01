---
title: "Statistics for Natural Scientists L5P1"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 10/Statistics for Natural Scientists L5P1.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 5.1: Categorical responses to numerical predictors (logistic regression)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

**Hi everyone. Welcome to the last lecture of Statistics for Natural Scientists.

## Slide 2

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

I want to start today by looking back a figure from an earlier session, because I got an interesting question about it. In this figure, I have plotted wages in Canadian dollars as a function of the worker’s age. Red dots are for women and blue dots are for men. The red and blue lines are the best fit lines for women and men, respectively. The slopes are significantly different. That means there is an interaction between sex and age. The effect of age depends on sex.

## Slide 3

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

We can see that here. The effect of being 60 years old is different depending on whether you are a man or a woman.

## Slide 4

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

Similarly, the effect of sex depends on your age. When people are 35, the effect of sex is smaller than when they are 60.

So, my question for you is this: Is there a significant effect of sex in this data set? I will talk about this on the next slide, but pause here and see if you can answer the question for yourself first.

## Slide 5

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

The answer is, it depends. Specifically, whether there is a significant effect of sex depends on your age.

For older people, the effect is significant. When they are 60, men make significantly more than women. So, there is a significant effect of age.

But, when men and women are 25, there is no difference in earnings. So, there is not a significant effect of age.

This illustrates an important point: if there is an interaction in the model, we cannot always make general conclusions about the significance, or even the direction, of the main effects. Whether the effect of a predictor is large or small, and even whether it is positive or negative, will depend on the value of the other predictors in the model.
 
So, if we want to say something about the effect of sex in this model, we have to specify the age of the people we are talking about.

….

So, let’s move on to the new material for today…

## Slide 6

### Choosing a statistical test

**Notes:**

The table on this slide is in Appendix 1 of the unit handbook. The object is to help you choose the right statistical test for your data. The right test depends on the kind of data you have.

In the past four weeks, we have studied several tests we can use when we have numerical response variables. If our predictors are categorical, we can use t-tests or ANOVAs. If our predictors are numerical, we can use linear regression. If our response variable is categorical AND our predictor is categorical, we can use the chi-squared tests we studied last week.

But, what can we do if our predictor is numerical and our response variable is categorical? This kind of data is common in many fields. For example, in ecology, mate choice data often has numerical predictors and categorical responses. We might conduct mating trails with male and female spiders, and ask if whether the male courts depends on the size of the female. Or, a common method in medicine is the LD50 trial. LD stands for “lethal dose.” In LD50 trials, researchers expose animals to different doses of medicines, or viruses, or pollutants, and they ask how the probability of death depends on the dose size.

This kind of data provides some special challenges, and we will think about how to handle those today.

## Slide 7

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

So, let's start by imagining a data set that has a quantitative predictor and a categorical response.  The example in the handbook is white tailed deer fawn mortality as a function of birth mass. I have made scatter plot of fawn mortality here. On the x-axis, we have the mass at birth for white tailed deer fawns. This is a number. On the y-axis, we have whether the fawn survived the winter. This is a category – it is either a yes or no. For convenience, people often represent this with an indicator, where 1 means ”yes” and 0 means “no.” But, it is still a category. “Yes” and “no” are not really numbers.

## Slide 8

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

And, as with any set of data points, we can draw a line of best fit through this data. But, as soon as we do that, problems begin to arise.

## Slide 9

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

First, our line of best fit cannot be a predictor of survivorship for any one fawn. For example, here in the green circle, the prediction would be that the fawn partly survives. But, obviously this does not make sense. In reality, the fawn either survives or it does not.

## Slide 10

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

Maybe we could interpret our line as a probability of survival. But, that does not quite work either. Our line starts below 0 and goes above 1.

## Slide 11

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

So, here, we would predict that our fawn has a less than 0 probability of survival…

## Slide 12

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

And here we would predict that the probability of survival is greater than one. This doesn’t make sense either, so this line cannot be a probability.

## Slide 13

### Survivorship of white tailed deer fawns as a function of birth mass

**Notes:**

So, what we really want is a curve that looks like this, where the probability of survival changes with mass, but tapers off as it approaches 0 or 1. Happily, a function describing this line exists. It is called the logistic function.

## Slide 14

### Logistic regression

- y

- z

**Notes:**

The logistic function looks like this.  It ranges from 0 to 1, and it has some very convenient properties.

## Slide 15

### Logistic regression

- y

- z

**Notes:**

First, notice what happens when z is exactly 0. The exponent of 0 is 1, and therefore y = 1 over 2.  So, if we think of y as the probability of an event happening, then when z equals 0, the probability of the event is 0.5. It is just as likely to happen as to not happen.

## Slide 16

### Logistic regression

- y

- z

**Notes:**

When z is a large negative, the denominator includes the exponent of a large positive, which is a VERY large positive. And, one divided by a very large positive is very close to 0. So, as z goes to negative infinity, the probability of our event happening goes to 0.

## Slide 17

### Logistic regression

- y

- z

**Notes:**

And when z is a large positive, the exponent part of the denominator is the exponent of a large negative, which is close to zero. So, the denominator approaches 1, and the whole function approaches 1. Thus, as z approaches infinity, the probability of our event happening approaches 1.

Now, think for a moment about this value z. A given a particular value of z, the logistic function always produces the same value of y. So, we cannot slide this red line to the right or the left, or change its slope. It is what it is. We call this value z the linear predictor, and it predicts the probability of our event.

But, somehow, we need to link this linear predictor z back to the true predictors that we want to study. For example, in the fawn data, we wanted to study the effect of birth mass. And, clearly, a birth mass of zero does not mean a fawn has a 50% chance of survival!

## Slide 18

### Logistic regression

- y

- z

- where x is the linear predictor

**Notes:**

So, to link z back to our real system, we assume that z is a linear function of the predictors that we really want to study.

In this function I am writing here, x is the predictor we want to study. So, for the fawn data, this would be birth mass. Beta_0 is the intercept, and beta_x is the effect of birth mass.

## Slide 19

### Logistic regression

- y

- z

- where x is the linear predictor

**Notes:**

Fitting the model consists of finding this beta_0 and beta_x. In principle, we do this by maximum likelihood. That is, we look for the values of beta_0 and beta_x that are most likely to produce the observed values of y. In practice, R will do this for us.

## Slide 20

### Logistic regression

- y

- z

- where x is the linear predictor

- where y(m) is the probability of the event

**Notes:**

Finally, once we have our values of beta_0 and beta_x, if we want to calculate the probability of an event, we can plug these back into our equation for y.

So, there has been a lot of math on the past few slides, and some of you are probably thinking that this test will be very hard. But, it will be easier than it seems, because implementing it is almost exactly analogous to implementing the linear regressions that we did two weeks ago. We will walk through an example in the second part of this lecture.
