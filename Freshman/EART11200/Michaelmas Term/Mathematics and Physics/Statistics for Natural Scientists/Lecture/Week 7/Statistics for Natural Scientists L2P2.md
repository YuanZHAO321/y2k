---
title: "Statistics for Natural Scientists L2P2"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 7/Statistics for Natural Scientists L2P2.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

- Asynchronous Lecture 2 Part 2

**Notes:**

Welcome back! In the first section of this lecture, we considered a new method for comparing the means of two groups. In this method, called ANOVA, we inferred that means were different if they explained more of the variability in the data than we would expect by chance alone.

But, for comparing two means, this test is identical to a t-test. And, we already know how to do a t-test. So, why should we need a new method?

## Slide 2

### Type I error: the false positive rate

- α

- (0.05)

- false positive rate

- p-value

**Notes:**

To explain this, let’s take a step back and think about p-values. The p-value is the probability that we would see a result as extreme as in the observed data by chance alone if our null hypothesis were true - in this case, if the true means of the groups were the same.

Because p-values are probabilities, they can range from zero to one on a continuous scale. In general, smaller p-values mean stronger evidence. Researchers often define an arbitrary cut-off value below which they say that a result is statistically significant. By convention, we signify this with the Greek character alpha. If a p-value is smaller than alpha, we say it provides evidence for the hypothesis. If it is larger than alpha, we say it does not.

We can think of alpha as a false positive rate. That is, if there were really no effect of the treatment in our experiment and we collected data at random, then alpha is the probability that the data would appear to support an effect of the treatment just by chance alone. We call this a “type 1 error.” We want the false positve rate to be small, because this is the probability that we would think that our hypothesis is true when really it isn’t. By convention, people seem to think that 0.05 is an acceptable false positive rate.

## Slide 3

**Notes:**

Now, in the examples we have considered so far, we have been interested in comparing the means of two groups. For example, we compared heights of men and women. But often, we are interested in comparing the means of more than two groups. For example, we might be studying the masses of the subspecies of Asian elephants, and we might want to know if they are different. So, how could we find out?

Well, the naïve way to do it would be to make a series of pairwise comparisons. For example, we could compare Sri Lankan elephants to Sumatran elephants. Then, we could compare Sri Lankan elephants to Bornean elephants, and then to Indian elephants. And then, we could compare Sumatran elephants to Bornean elephants, and so on. In all, there are six pairwise comparisons we could make.

But, there is a problem with this approach, and the problem is the false positive rate.

## Slide 4

**Notes:**

Consider just the comparison between Sri Lankan and Sumatran elephants. If we set alpha to 0.05 and there is really no difference between the species, the false positive rate is 0.05.

## Slide 5

**Notes:**

Now, imagine that we add Bornean elephants. What is our false positive rate now? Well, just by chance, our sample of Bornean elephants might be different from our Sri Lankan elephants, or it might be different from our Sumatran elephants. And, we already had a 5% false positive rate just for the first comparison. So now, our false positive rate for the set of comparisons is higher than 5%.

## Slide 6

**Notes:**

And the problem gets worse if we add another group. In fact, if we keep adding groups, eventually we are almost certain to get at least one that seems different from at least one other group, just by chance alone.

That is, if we make pairwise comparisons and we make a enough of them, we are certain to make a mistake.

## Slide 7

**Notes:**

ANOVA allows us to get around this problem. With ANOVA, we can simply add up the variability explained by all of our groups together (that is, the sum of squares of the red lines) and divide it by the unexplained variability across all groups (that is, sums of the squares of the gray lines). So, we get a single test statistic for the whole data set. Then, we can compare that test statistic to the distribution of values it could take by chance alone, to get a single p-value for the whole system. This p-value is the probability that four groups created at random would explain at least as much of the variability as our real groups explain.

Now of course, we could do this analysis by hand. But, we can also make R do it for us, which is much easier. So, I will walk through how to do that.

## Slide 8

### Conducting ANOVA in R

- elephants=read.csv("elephants.csv",header=TRUE)

**Notes:**

So, just like last week, the first things we will need to do is import our data into R. Again, we will use the read.csv command for that. Here, elephants.csv is the name of the data set, and the statement header=true tells R that the first row of the csv holds the column names. As always, I can name this data set however I want, and I will call it elephants.

## Slide 9

### Conducting ANOVA in R

- elephants.aov=aov(mass~subspec,data=elephants)

**Notes:**

To conduct the ANOVA, I will use the command aov. The command aov will create a model, and I am naming that model elephants.aov.

In the parentheses, there are two statements.

## Slide 10

### Conducting ANOVA in R

- elephants.aov=aov(mass~subspec,data=elephants)

**Notes:**

The first is the formula. To the left of the tilde, that is the squiggly line, we have the response variable, mass. To the right of the tilde, we have the predictor, subspecies of elephant. So, our analysis will ask how the mass of elephants depends on the subspecies. This is a syntax you will see again and again in this module.

## Slide 11

### Conducting ANOVA in R

- elephants.aov=aov(mass~subspec,data=elephants)

**Notes:**

The second statement, data=elephants, tells R where to find the variables that appear in the formula. So, mass and subspec are columns in the data set elephants.

When I execute the command, I do not see an error message, so that means the command has done something. But I cannot see what it has done.

## Slide 12

### Conducting ANOVA in R

- elephants.aov=aov(mass~subspec,data=elephants)

- summary(elephants.aov)

- Df  Sum Sq Mean Sq F value  Pr(>F)

- subspec      3 3524437 1174812   5.138 0.00464 **

- Residuals   36 8231967  228666

- ---

- Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

**Notes:**

To see the results, I will use the command summary(elephants.aov).

When I execute the summary command, I will see the result. Here, the row subspec tells us whether subspecies affects the mass of elephants. The p-value, in the last column, is small. So, subspecies explain more variability than we would expect due to chance alone. Thus, we infer that different subspecies of Asian elephants really have different masses.

But, the ANOVA is an omnibus test. That is, it tells us that different subspecies of Asian elephants have different masses, but it does not tell us which subspecies are different from which other subspecies. Often though, we may be interested not just in whether the groups differ, but in how they differ.

## Slide 13

### Conducting ANOVA in R

- TukeyHSD(elephants.aov)

- Tukey multiple comparisons of means

- 95% family-wise confidence level

- Fit: aov(formula = mass ~ subspec, data = elephants)

- $subspec

- diff         lwr       upr     p adj

- Indian-Bornean      -694.49536 -1270.45034 -118.5404 0.0128704

- Sri Lankan-Bornean    60.73317  -515.22180  636.6881 0.9918725

- Sumatran-Bornean    -190.72152  -766.67650  385.2335 0.8090934

- Sri Lankan-Indian    755.22854   179.27356 1331.1835 0.0060659

- Sumatran-Indian      503.77384   -72.18113 1079.7288 0.1043831

- Sumatran-Sri Lankan -251.45469  -827.40967  324.5003 0.6457027

**Notes:**

If an ANOVA tells us that our groups have different means, we can follow up with a post hoc test called a Tukey test.

The syntax is simple. It is just TukeyHSD, and then the name of the model in parentheses. HSD stands for honest significant differences. The Tukey test tells us which means are different from which other means, controlling for multiple comparisons. Here, the final column is the p-value, the first column tells us how the groups differ. For example, the difference between Indian and Bornean elephants is significant, because the p-value is less that 0.05. Specifically, Bornean elephants are larger by 694 kg. We can tell Borean elephants are larger because the difference when we subtract the Bornean mean from the Indian mean is negative.

Similarly, Sri Lankan elephants are bigger than Indian elephants, because again the p-value is less than 0.05. Sri Lankan elephants are, on average, 755 kg more massive.

None of the other p-values are less than 0.05, so we do not have evidence for differences among any of the other groups.

## Slide 14

### Reporting results of an ANOVA

- In the text: Mean mass differed among elephant subspecies (F = 5.1; df = 3, 36; p = 0.0046). Indian elephants were smaller than Sri Lankan elephants by 755 kg (p = 0.0061) and smaller than Bornean  elephants by 694 kg (p = 0.0128).

- Figure Legend: Mean mass for four Asian elephant subspecies. Error bars show standard error around the mean. Horizontal lines indicate that species means are not significantly different (α = 0.05).

**Notes:**

So, how should we report this? In the text, we should report the key information clearly and concisely. In this case, we should tell the reader that we found differences in mass among the elephant subspecies. We report the p-value, because that tells the reader how confident they should be in our results. By convention, we also report the F-statistic and the degrees of freedom, which you can find in the ANOVA output. If specific differences among the subspecies are of interest, we can report those directly. In this case, the text should report not just the p-values, but also the effect sizes. For a reader trying to understand the empirical system, the effect sizes are the most important part.

It is usually easiest for readers to understand results if they are supported by figures. The simplest and most intuitive figure for reporting an ANOVA is a bar plot. Here, each bar shows the mean mass for one elephant subspecies, and the error bars show the standard errors around the means. This part is very similar to the plot we used to report the results of a t-test.

But, for an ANOVA, if we want to show which means are different from which other means, then we have to take this a step further. If we put the bars in order (for example, greatest to least, or least to greatest), then we can put a horizontal line over bars with means that are not significantly different. So, in this figure, the top horizontal line tells us that we found no significant difference between Sri Lankan, Bornean, and Sumatran elephants. The second line tells us that we found no significant difference between Sumatran and Indian elephants. But, because Indian and Sri Lankan elephants are not under the same line, we know those are significantly different. As always, there is a figure legend that tells the reader everything they need to know to understand the figure, but is as concise as possible.

The figure on this slide was made in R. The code I used to produce the figure is long, so I will not walk you through it. You can find it in the Backboard folder for session 3.

Let’s take a break here, and then in the last part of this lecture I will introduce one more useful idea about ANOVA.
