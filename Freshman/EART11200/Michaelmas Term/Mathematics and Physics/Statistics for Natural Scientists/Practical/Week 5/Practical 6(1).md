---
title: "Practical 6(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 5/Practical 6(1).docx"
type: document
---

After completing practical 6, you will be able to:

- Use simple and multiple logistic regression to analyse data with numerical predictors and dichotomous categorical responses.

- Report the results of logistic regression models clearly and concisely.

- Use logistic regression models to predict the probabilities of events.

Practical 6

At 11:40pm on April 14, 1912, the ocean liner Titanic struck an iceberg about 600 km south of Newfoundland. Less than three hours later, the ship foundered and sank with more than half of the passengers still on board. The Titanic was carrying some of the world’s wealthiest people, and their story has been told again and again in film and literature. But, most of the people on the Titanic were not wealthy. The majority were working class emigrants leaving Europe for North America. Their stories are less often told.

Today’s data set looks at survivorship from the sinking of the Titanic. You can find the data in “titanic.csv.” Read the data into R as we have in previous weeks. If you name the data set td (for Titanic data) then the starter code supplied with this practical will work with minimal editing. Look at the data you have imported, and make sure you know what each column means. Note that the column survived is an indicator: it has value 1 if the individual survived and value 0 if they did not.

Question 1

It is commonly believed that when the Titanic sank, women and children were allowed to board lifeboats before men. So, let’s see if we can detect this in the data. Specifically, we will ask whether sex and age were significant predictors of survivorship.

Last week, we learned a method for studying whether there are disproportionate associations between two categorical predictors. In our data survivorship is coded as a number, but in reality “survived” and “did not survive” are categories. “Male” and “female” are also categories. Use methods we learned last week to answer:

Q1.1: What proportion of males on the Titanic survived the sinking? What proportion of females survived?

Q1.2: Did males and females have different probabilities of surviving the sinking of the Titanic? Report your results clearly and concisely.

Q1.3: Provide a figure to illustrate your result. (You can reuse code from practical 5!)

This week, we will use logistic regression to study categorical responses to numerical predictors. In previous weeks saw that we can convert dichotomous predictors like self-reported sex into numerical “indicator variables” that describe whether a data point does or does not belong to a particular category. Let’s create an indicator variable to report whether each person in the data set was male. Then, we can use logistic regression to study the relationship between the indicator male and survivorship on the Titanic. You may remember how to create indicator variables or where to look that up, but if you have forgotten, there is code in the starter code to help.

To ask whether sex predicted survivorship on the Titanic, we can fit a logistic regression to our data using the code:

surv.x.male.lr = glm( survived ~ male, data = td, family = binomial )

The syntax here is similar to the syntax we used for linear regression. The command glm() indicates that this is a generalised linear model, and the argument family = binomial tells R that this should be a logistic regression. There are many kinds of generalised linear models, so if you tell your readers only that you have done a generalised linear model, they will not know what you did. You must report in your methods that you conducted a logistic regression! Here, I have named our model surv.x.male.lr to remind me that it regresses survivorship on sex. We can see the results using the summary() command that we have used in previous weeks.

If you fit the model above correctly, your summary should report that the effect of one unit of “maleness” (ie, of being male) is -2.4667. From the handbook, you will know that the effects of predictors in logistic regressions are reported as log odds ratios (LOR). This means that the odds of survival for males were exp(-2.4667) = 0.085x the odds of survival for females. That sounds bad - at least for males! But, unless you spend a lot of time with your bookie, “odds” may not be a completely intuitive concept. It may be easier for readers if you convert your predictions to probabilities of events, which are easier to understand. To obtain probabilities of events from logistic regressions, we first compute the linear predictor for the case we want to study, and then we convert that linear predictor to a probability using the inverse link function. We obtain the linear predictor in the same way we obtained predictions from linear regression models in practical 4. For example, let’s compute the linear predictors for females and males based on the model we just fit. Recall that females are coded as 0 in our column male, and male is the only predictor in the model. The intercept is the predicted value when all predictors are 0. So, the intercept (ie, 1.1124) is the linear predictor for females. The effect of being male (ie, the amount by which male log odds of survival differ from female log odds of survival) is -2.4667. So, the linear predictor for males is 1.1124 - 2.4667 = -1.3543. The inverse link function for logistic regression is 1/(1+exp(-x)), where x is the linear predictor. So, the probability of survival for females on the Titanic was:

1 / (1 + exp( -(1.1124) ) ) = 0.7526

Q1.4: Compute the probability of survival for males on the Titanic. Does this agree with your answer in Q1.1?

How should you report the results from the model above? Readers will certainly need a p-value, but how you report the effect size is up to you. Some authors might report “Females survived with higher probability than males (0.7526 vs xxxx; p < 0.0001).” Others might report “The odds of survival were 11.8x greater for females than males (p < 0.0001),” or “Males were less likely to survive than females (LOR = -2.4667; p > 0.0001).” All of these are equally correct, and you can decide which is best for your readers. If you want to provide a figure, we already made one. This analysis answers the same question as our chi-squared test, so we can illustrate it with the same figure.

Question 2

In question 1, we studied how the numerical predictor male affected survivorship on the Titanic. Age is also a numerical predictor. We can use the logistic regression in the same way to ask whether age predicted survivorship on the Titanic.

Q2.1: Use logistic regression to test whether age predicted survivorship on the Titanic. Report your result clearly and concisely.

Note that the effect size associated with age in the model you created has units, and it is important to report those units when you report your results. The estimate associated with a predictor in logistic regression is the log odds ratio for a one-unit change in the predictor. Here, the predictor age is measured in years. So, I might report the result above by saying “We found marginally significant evidence that survivorship decreased with age (LOR = xxxx yr-1; p = xxxx).”

Q2.2: Based on the model above, what was the probability that a person who was 20 years old would have survived the sinking of the Titanic?

Question 3

Up to this point, the predictors in our linear and logistic regressions have been numerical. When we wanted to study the effects of dichotomous categorical predictors in regression models, we started by recoding them as indicators. It turns out that many regression functions in R (eg, lm() and glm()) can also handle categorical predictors. If we fit a regression with a categorical predictor, R chooses one category to act as the baseline, and compares each of the other categories to that baseline.

For example, consider the categorical variable class in the Titanic data. There are three categories in class: first, second, and third. (The names of these categories make them sound like numbers, but they are not numerical measures, they are qualitative descriptions of groups.) We can study how passenger class affected the probability of survival on the Titanic using the code:

surv.x.class.glm = glm( survived ~ class, data = td, family = binomial )

We can interpret the output in exactly the same way we interpreted the output when we regressed survivorship on male in Question 1.

Q3.1: Report the results of the model above clearly and concisely.

Q3.2: Based on the model above, what was the probability of survival for a first-class passenger on the Titanic? For a third-class passenger?

Question 4

In question 1, we studied the relationship between sex and survivorship on the Titanic first with a chi-squared test and then with a logistic regression, and we found that the results were the same. We could have studied the relationship between class and survivorship in question 3 with a chi-squared test. You may wonder why we would bother learning a new method to study this relationship if we already have one that gives us the same answer. One reason is that chi-squared tests work only when we have one categorical predictor and one categorical response. Logistic regression is more flexible. Like linear regression, we can use it to study the effects of multiple predictors at the same time. When we do this, our result will show the effect of each predictor while controlling for the others.

Just as we did with linear regression, we can include multiple predictors in a logistic regression by adding them to the right-hand side of the formula when we call the model. For example, we can study the effects of sex and class on survivorship on the Titanic using the model:

surv.x.sc.lr = glm( survived ~ sex + class, data = td, family = binomial )

This model studies the effect of sex controlling for class, and of class controlling for sex. As usual, we can see the results using the summary() command. But, we will not spend time analysing this model, because our real interest is in an even more complex model.

Q4.1: Use logistic regression to study the effects of sex, class, and age on survivorship on the Titanic, with each predictor controlled for the others. Report your results clearly and concisely.

When we studied the effect of age in question 2, we found that it was only marginally significant (p = 0.0731). The log odds ratio for survival changed by -0.0079 yr-1. In this model, the effect of age is strongly significant (p < 0.0001) – the log odds ratio for survival changes by -0.0344 yr-1. So, the effect of age is more than four times greater!

Q4.2 (Challenge): Why can we see a strong effect of age in this model when we barely detect one in the simpler model?

The answer is not just that our new model model controls for the other predictors – that is a given. The question is why would controlling for the other predictors reveal an effect that is hidden when we do not control for them? Answering this kind of question often requires thinking carefully about our study system. What do we know, or might we be able to guess, about the people on the Titanic?

Q4.3 (Super-challenge): Your answer to Q4.2 is a hypothesis. That is, it is a possible explanation for a pattern we have observed in our data. Can you test that hypothesis using some method we have learned in this unit?

Question 5

Q5.1: Use logistic regression to study the effects of class, sex, age, and the interaction between sex and age on survivorship on the Titanic. Report your results clearly and concisely.

Q5.2: In the movie Titanic, Rose DeWitt Bukater was 17 years old. She was from a wealthy family, and travelling first class. Use the model above to estimate her probability of survival.

Q5.3: Jack Dawson was 19 years old and travelling third class. What was Jack’s probability of survival?

A Closing Thought

In this practical, we studied several different models for the same predictor and response variables. For example, in question 2 we studied the probability of survivorship as a function of age, and in questions 4 and 5 we studied the probability of survivorship as a function of age and several other predictors, each controlling for the others. But, which is the “right” model to study?

In practice, all of these models have value, but they answer different questions. For example, if we knew nothing about a passenger except their age, then the model in question 2 would be the best predictor of their survival. The effect of age in that model is confounded by other factors. For example, people from some classes were more likely to survive independent of their age, and older people were more likely to be in first class, so part of the effect that we are assigning to age in this model is really due to class. That is fine. It is still true that people of different ages had different survivorships, and we can predict their survivorship based on their age, regardless of the mechanisms that link age to survivorship. In contrast, if our goal is to sort out the mechanisms that link passenger attributes to survivorship, then we need to isolate the effects of each predictor by controlling for the others. So, there is no simple way to choose a “best” model for a particular data set. We just have to think carefully about the questions we are trying to answer!
