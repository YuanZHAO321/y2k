---
title: "Statisitcs for Natural Scientists L2P3"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 7/Statisitcs for Natural Scientists L2P3.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

- Asynchronous Lecture 2 Part 3

**Notes:**

Welcome back. There is one last idea I want to cover in today’s lecture.

## Slide 2

**Notes:**

ANOVA works by comparing the variability explained by our treatments to the unexplained variability in our data. High ratios indicate an effect of the treatment.

This means that we can think of unexplained variability as the enemy, because unexplained variability obscures the effects of treatments. One way to limit unexplained variability is to do carefully controlled experiments. But, outside of the lab, this is not always possible. If you do your work in the field, there will be factors you can’t control.

If we cannot control unexplained variability, there is another way to get rid of it. We can explain it. Because, if we can explain variability, then it is no longer unexplained.

So, let’s look at the elephant data again. One source of variability in body size for most mammals is sex.

## Slide 3

**Notes:**

In this figure, I have colored the elephant bulls in blue and the cows in red. At a glance, it looks like the females are smaller than the males. So, some of the variability in this data set may be explained by sex.

## Slide 4

**Notes:**

If there is an effect of sex on elephant mass, then instead of having just one mean for each subspecies, we should have two: one for males and one for females. The error is just the difference between each point and its respective mean, and you can see that these have gotten smaller. So, by including sex in the model, we have reduced the unexplained variability, and increased our power to detect the effects of groups.

Because there are two predictors in this model, we call this a two-way ANOVA.

## Slide 5

### Conducting two-way ANOVA in R

- elephants.aov=aov(mass~sex+subspec,data=elephants)

**Notes:**

Implementing the two-way ANOVA is almost exactly the same as implementing the simple, one-way ANOVA. For the one-way ANOVA, we used the formula mass~subspec. For the two-way ANOVA, we will use the formula mass~sex+subspec. That is, we are asking how mass depends on subspecies, controlling for sex.

## Slide 6

### Conducting two-way ANOVA in R

- elephants.aov=aov(mass~sex+subspec,data=elephants)

- summary(elephants.aov)

- Df  Sum Sq Mean Sq F value   Pr(>F)

- sex          1 4727088 4727088   47.39 5.39e-08 ***

- subspec      3 3538357 1179452   11.82 1.68e-05 ***

- Residuals   35 3490959   99742

- ---

- Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

**Notes:**

Now, when we look at the summary, there are two rows. The first row tells us something about sex, but I will ignore that for now and come back to it later.

The second row tells us whether subspecies predicts mass, while controlling for sex. The p-value is small – in fact, it is even smaller than it was when we did not control for sex. So, controlling for sex has increased the power or our analysis.

## Slide 7

### Conducting two-way ANOVA in R

- TukeyHSD(elephants.aov)

- Tukey multiple comparisons of means

- 95% family-wise confidence level

- Fit: aov(formula = mass ~ sex + subspec, data = elephants)

- $sex

- diff      lwr     upr p adj

- m-f 701.7157 494.7865 908.645 1e-07

- $subspec

- diff        lwr       upr     p adj

- Indian-Bornean      -764.66694 -1145.5736 -383.7602 0.0000263

- Sri Lankan-Bornean   -79.60997  -460.5167  301.2967 0.9421499

- Sumatran-Bornean    -260.89309  -641.7998  120.0136 0.2691397

- Sri Lankan-Indian    685.05697   304.1503 1065.9637 0.0001428

- Sumatran-Indian      503.77384   122.8671  884.6806 0.0056385

- Sumatran-Sri Lankan -181.28312  -562.1898  199.6236 0.5792692

**Notes:**

If we want to know which subspecies differ from which other subspecies, we can do a post hoc Tukey test, just like we did for the one-way ANOVA.

The output reports something about sex, but I will ignore that for now.

Instead, look at the output in the red circle. This compares the subspecies. Just as before, we find that Sri Lankan elephants and Bornean elephants are bigger than Indian elephants. The p-values in those rows are less than 0.05. But now, we also find that Sumatran elephants are bigger than Indian elephants. We did not find that in our one-way ANOVA. Controlling for the variability due to sex allows us to detect this new effect in our data.

## Slide 8

### Conducting two-way ANOVA in R

- TukeyHSD(elephants.aov)

- Tukey multiple comparisons of means

- 95% family-wise confidence level

- Fit: aov(formula = mass ~ sex + subspec, data = elephants)

- $sex

- diff      lwr     upr p adj

- m-f 701.7157 494.7865 908.645 1e-07

- $subspec

- diff        lwr       upr     p adj

- Indian-Bornean      -764.66694 -1145.5736 -383.7602 0.0000263

- Sri Lankan-Bornean   -79.60997  -460.5167  301.2967 0.9421499

- Sumatran-Bornean    -260.89309  -641.7998  120.0136 0.2691397

- Sri Lankan-Indian    685.05697   304.1503 1065.9637 0.0001428

- Sumatran-Indian      503.77384   122.8671  884.6806 0.0056385

- Sumatran-Sri Lankan -181.28312  -562.1898  199.6236 0.5792692

**Notes:**

Now, the syntax for two-way ANOVA is easy, but there is an important detail to pay attention to. Look again at the formula for our model, which R has helpfully reported here. We asked how mass depends on sex plus subspecies. The order in which we list these terms matters. Here, we are asking how mass depends on subspecies while controlling for sex. In general, we want to put the predictor we are interested in studying last.

## Slide 9

### The order of predictors in ANOVA matters

**Notes:**

To understand why order matters, consider this data on two imaginary elephant subspecies. Here, the subspecies are identical. Males of each subspecies have the same average mass, and females of each subspecies have the same average mass. But, in our sample, we have more males of one subspecies, and more females of the other.

## Slide 10

### The order of predictors in ANOVA matters

**Notes:**

If we put subspecies into the model first, then we start by finding the average mass for each subspecies. So, we will infer that the subspecies are different. After we do this, we will also infer an effect of sex, because within each subspecies the males have above average mass, and the females have below average mass. Our inference about sex will be correct, but we know that our inference about subspecies is wrong, because we designed this example to have no effect of subspecies.

## Slide 11

### The order of predictors in ANOVA matters

**Notes:**

However, if we put sex into the model first, our inferences are different. We find an effect of sex. However, within each sex, each subspecies has the same average mass. We infer that there is no effect of subspecies on mass, and this inference is correct.

So, when we are interested in studying the effect of one predictor controlling for the others, the predictor we want to study should enter the model last. This is why I did not try to interpret the effect of sex in the model we just looked at.

************
Okay. That is all I have to say for today. You can find the practical assignment in the Blackboard folder for this session. If you have questions, please post them to the discussion forum on BlackBoard and I will do my best to help!
