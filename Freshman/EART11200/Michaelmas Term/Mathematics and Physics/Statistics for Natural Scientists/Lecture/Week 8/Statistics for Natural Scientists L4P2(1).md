---
title: "Statistics for Natural Scientists L4P2(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 8/Statistics for Natural Scientists L4P2(1).pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 3.2: Understanding the effects of quantitative predictors

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

Hi all! Welcome back to to the second part of this week’s lecture on understanding quantitative predictors.

## Slide 2

### Mean-centering can make the intercept more useful.

**Notes:**

I ended the last section of this lecture by asking about the interpretation of the intercept in a linear model with a mean-centred predictor. I hope you took a few minutes to think about it.

## Slide 3

### Mean-centering can make the intercept more useful.

- C$3.03 ->

**Notes:**

Let’s start by thinking back to what the intercept mean when we plotted hourly wage as a function of years of education before mean-centering the predictor. In this case, the intercept told us the wage we might expect for someone with no education. But, this was not very useful, because everyone in Canada has at least some education.

## Slide 4

### Mean-centering can make the intercept more useful.

- C$15.39 ->

**Notes:**

But now, let’s look at the intercept for the plot of hourly wage on mean-centered education. We already saw that the slope and p-value do not change. But, because the position of zero on the x-axis has changed, the intercept has changed. And, what is this new value of zero? Well, it is the population mean education. So, the new intercept is the expected wage for a person with average education. And, this is much more useful to us!

## Slide 5

### Mean-centering can make the intercept more useful.

**Notes:**

So, the intercept in the model of wage as a function of mean centered education is the expected wage for a person with average education.

If figured this out before I told you, nice job!

## Slide 6

### Linear regression with dichotomous predictors.

**Notes:**

So, I will move on to a new idea here. Some people will tell you that the predictors in a linear regression must be continuous variables. That is nonsense. We can use discrete variables as predictors. We can even use dichotomous variables as predictors. But, the predictors in linear regression do have to be numbers. So, somehow we have to turn our dichotomous predictors into numbers. To do that, we can create what we call an indicator variable. I will explain with an example.

The survey data we have been looking at today is from 1994, and at the time it was common for surveys of this sort to force people to identify as either male or female. This is called coercive gendering, and we now realise that it loses information about the population. Nonetheless, in this data set, everyone is reported as either male or female, so we can treat sex as dichotomous variable in this data.

## Slide 7

### Linear regression with dichotomous predictors.

**Notes:**

To turn the dichotomous variable sex into a number, I am going to create a new variable called “male.” ”Male” will be an indicator. It will have the value 1 if the person is male, and it will have the value 0 otherwise.

In the command I am showing here, the part in the parentheses will return TRUE for all persons who have an m in the column sex, and FALSE for everyone else. The command as.numeric turns these TRUEs and FALSEs into 1 and 0, respectively. And, we are saving this list of 1s and 0s with the name “male.”

## Slide 8

### Linear regression with dichotomous predictors.

**Notes:**

To see that this has worked, we display sex and male side-by-side. So, every male has a value 1, and everyone else has a value 0.

## Slide 9

### Linear regression with dichotomous predictors.

**Notes:**

And now, we can fit a linear regression exactly as we did for education. In the command, I have simply replaced “mc_school” with male.

So, what does this tell us?

## Slide 10

### Linear regression with dichotomous predictors.

**Notes:**

Well, the p-value associated with being a male is small. So, our sex predicts earnings in the data set. Moreover, we know the effect of being male. Males earn 4.135 Canadian dollars more per hour than females.

*****
Now, to be clear, I am not arguing that this wage gap is right or good. In fact, to me this indicates a problem. But, as societies we cannot solve problems unless we know those problems exist, and part of what Science does is demonstrate that problems exist.

## Slide 11

### Linear regression with dichotomous predictors.

**Notes:**

Okay, before we move on, what does the intercept mean? I will tell you on the next slide, but I encourage you to pause the video here and see if you can figure it out yourself first.

## Slide 12

### Linear regression with dichotomous predictors.

**Notes:**

The intercept is the value of predicted response (in this case hourly earnings) when the predictor is zero. In our indicator, the predictor is zero when the person is female. So, $12.87 is the predicted hourly wage for females in the data set.

*****

So some of you are probably looking at this and wondering why we would bother to make a linear model with a dichotomous predictor. After all, a t-test would answer the same question, and we already know how to do that. Why do we need another method? The reason is that linear regression allows us to do something that a t-test can’t do. With linear regression, we can study several predictors at the same time.
 
This can be very important in survey studies. The reason is that, in survey studies, our samples are often not balanced. For example, in this case, men and women might have different educations. Maybe our data set just happens to have a lot of highly educated men. Then, the difference between the sexes that we saw in our model might not really be due to sex at all. It might just be because the men were more educated, and therefore they earned more. To sort this out, we would like to be able to study the effects of each of the variables while controlling for the other.
 
Happily, this is very easy to do.

## Slide 13

### Multiple linear regression

**Notes:**

We can simply add both predictors to the model, just as we did with two-way ANOVA.

## Slide 14

### Multiple linear regression

**Notes:**

And these are our results.

Notice that the p-values are still small for both school and male. So, we have evidence that both of these things predict hourly wage. In particular, the effect of being male is that a person earns $4 and 25 cents more per hour. And for each additional year of education, a person earn 92 cents more per hour.

## Slide 15

### Predicted hourly wage as a function of education and sex

- o men         o women

**Notes:**

To understand that better, we can plot the results in a figure. This figure shows education on the x-axis, and hourly wage on the y-axis. The blue circles represent men, and the red circles represent women. The blue and red lines are the best fit lines for men and women, respectively.

Some women earn more than some men. But, for men and women with the same education, men earned $4.25 more per hour. We call this the effect of sex controlling for education.

## Slide 16

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

The next idea is one people sometimes struggle with. Sometimes, predictors interact. That means that the effect of one predictor can depend on the value of another.
 
To illustrate this, let’s look at the effect of age on wage in our data set. In this slide, I am showing the average wage for workers of different ages. Ages are on the x-axis, and wages are in the y-axis. Blue dots are men, and red dots are women. And, it looks like there is an interesting pattern here. Men’s wages seem to go up as they get older. It is not clear that that happens with women’s wages. So, how age affects your wage may depend on your sex.

## Slide 17

### Linear regression with interactions

**Notes:**

To test our intuition from looking at the figure, we can include an interaction in our model. Again, this is easy to do. I already mean-centered age, and named that variable mc_age. So here, I am building a model that includes mean-centered age, the indicator male, and the interaction between them. To include an interaction, I just add a multiplicative term.

## Slide 18

### Linear regression with interactions

**Notes:**

And what we see is very interesting. There is still an effect on being male. Men of average age earn about C$4.79 more per than women of average age.

## Slide 19

### Linear regression with interactions

**Notes:**

The model also reports an effect of age. The main effects of predictors (that is, the part outside of the interaction) is reported when the other predictors are zero. So here, the effect of age is reported when male equals zero. In other words, this is the effect of age on hourly wage for women. The p-value here is nearly 1, so we have no evidence that a woman's age affects her hourly wage. That is, older women do not earn any more than younger women.

## Slide 20

### Linear regression with interactions

**Notes:**

But, there is an interaction between sex and age. Older men DO earn more than younger men. In fact, the average wage for men increases by almost 38 cents per hour for every year of their age.

## Slide 21

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

We can represent this in a figure. Here again, I am showing age on the x-axis and hourly wage on the y-axis. The blue circles represent men and the red circles represent women, and the blue and red lines are the lines of best fit. The predicted hourly wage of men increases with age, but the predicted hourly wage of women does not.

Now, there is something important that this analysis does not tell us. Young men and young women seem to be making about the same amount. But, older men make more than older women. There are two possible explanations for this. One is that the problem has been partly solved. Young men and women are making the same, and maybe as these young people get older their wages will increase in the same way, and the pattern we see here will disappear. The other possibility is that the problem is ongoing. Men and women start their careers making the about same amounts, but men get promoted and women don’t. We can't distinguish between these possibilities in the data. But, we do know this. This data is more than 25 years old, so if the first explanation were true, we would expect the pattern to have mostly disappeared by today. But, this is very similar to the pattern we still see in many big organisations, including the University of Manchester. There are more men than women in high-paying leadership posiions. (Except for the vice chancellor of course. She is a woman, and she earns more than a quarter million pounds per year. So, if we wanted to plot her earnings, we would have to make the y-axis 4x higher!)

## Slide 22

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

Okay, there is one last idea I want to introduce today. Let’s start by looking at this figure a little more carefully. Look carefully at the bottom left. Almost everyone in this part of the figure is earning less than the prediction. Can you guess why that might be true? I encourage you to pause the lecture here and see if you can come up with a hypothesis.

## Slide 23

### Hourly wage for workers of different ages and sexes

- o men

- o women

**Notes:**

One possibility is that this is related to education. We already know that more educated workers earned higher wages. And, the people in this part of the figure are young. You can’t have 20 years of education if you are only 18 years old. So, we might want to build a model that includes all of the predictors we think might be interesting - at the same time.

We can do this using exactly the same approach we have been using.

## Slide 24

### Multiple regression w/ backwards selection

**Notes:**

Here, I am building a model that includes everything that I think might reasonably affect hourly wage. I am including education, age, sex and native language. I am also including the interaction between sex and age, and the interaction between sex and education, to see if age and education affect one sex more than the other.

## Slide 25

### Multiple regression w/ backwards selection

**Notes:**

We can execute the model and look at the summary just as before.

Now, there are a lot of predictors in this model, which makes it hard to interpret. Also, if a predictor does not affect the response variable, it really doesn’t belong in the model. If it doesn’t affect the response, all it is doing is adding noise. So, before we even try to interpret this model, we might want to get rid of the uninformative predictors.

## Slide 26

### Backwards model selection

- Build a model that includes all of the predictors you are interested in studying.

- Remove predictors one at a time, starting with the highest p-values.

- But, do not remove a predictor if it is part of an interaction that is still in the model.

- When all remaining predictors are significant (or part of significant interactions), stop.

**Notes:**

There are different ways to remove uninformative predictors from a model, but one simple one is called backwards selection. In backwards selection, we remove predictors from a model one at a time, following a set of rules.

First we build the model with all of the potentially interesting predictors. Then, we look at the fitted model, and we identify the predictor with the highest p-value. We remove that predictor from the model.

But, we never remove a predictor if it is involved in an interaction with another predictor.

When we reach a point where all of our predictors either have significant effects or are involved in significant interactions, we stop. That is our final model.

## Slide 27

### Multiple regression w/ backwards selection

**Notes:**

So, let’s try that with the model we just looked at. In this model, native language is the least significant predictor. It is not involved in any interactions. So, let’s remove it from the model.

## Slide 28

### Multiple regression w/ backwards selection

**Notes:**

We remove English from the model, refit, and look at the summary. Now, age is the least significant predictor, but it is involved in an interaction with sex, so we cannot remove it. So, we skip to the next least significant predictor. That is the interaction between education and sex. That is not significant, so we can remove it.

## Slide 29

### Multiple regression w/ backwards selection

**Notes:**

We remove the interaction between age and education from the model, and we refit. Again, age is the least significant predictor, but it is involved in an interaction, so we can’t remove it. Everything else is significant. So, we are finished. This is our final model.

So, what does it mean? Well, the easiest part is education, because school is not involved in an interaction. For every additional year of education, people earn 90 cents more per hour, regardless of sex.

## Slide 30

### Multiple regression w/ backwards selection

**Notes:**

Then, we have an effect of being male. The indicator male is involved in an interaction with mean centered age, so the main effect of male is estimated when mean centered age is zero. That is, the mean effect tells us about people of average age. So, a man of average age in the data set earns $4.94 per hour more than a woman of the same age.

## Slide 31

### Multiple regression w/ backwards selection

**Notes:**

Similarly, mean centered age is involved in an interaction with male. So, the main effect of age is estimated when the indicator male equals zero. That is, it is the effect of age on wage in women. Here, the effect is not significant. So, age does not predict hourly wage for women.

## Slide 32

### Multiple regression w/ backwards selection

**Notes:**

The interaction between age and male is significant. So, for men, age does effect wage. But, how much?

The effect of age on wage in the baseline sex is not significant, which means we are not confident that it is different from zero. But, if we absolutely had to guess what that effect is, our best estimate would be 1.8 cents per hour per year. That is the amount in the blue circle. Men differ from this baseline effect by an additional 35.5 cents per hour per year. So, overall, the average wage for men increases by about 37.4 cents per hour per year.

## Slide 33

### Reporting regressions with multiple predictors.

| predictor | effect size | p-value |
| --- | --- | --- |
| intercept | $12.75 | >0.0001 |
| education | $0.90 y-1 | >0.0001 |
| sex | $4.94 (male) | >0.0001 |
| age | $0.07 y-1 | 0.7894 |
| sex * age | $0.36 y-1 (male) | 0.0003 |

**Notes:**

***Finally, how should we display this result?

It can be very hard to illustrate the results of multiple regressions in figure, so people often report them in tables instead. The table should report effect sizes and p-values. Note though that we cannot simply cut and paste an R output into a manuscript and call it a table! A table should be clearly formatted and labelled for the reader. There is additional guidance on reporting the results of multiple regression in the handbook.

So, that is all I have to say for today. Thanks again everyone for tuning in. You can find your practical in the Blackboard folder for this week of the unit. Good luck, and please feel free to contact me if you have questions!
