---
title: "Statistics for Natural Scientists L4P2(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 9/Statistics for Natural Scientists L4P2(2).pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 4.2: Categorical responses to categorical predictors (chi-squared test)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

Welcome back. In the last section of this lecture, we looked at how we might analyse a data set with a binary response variable using the binomial test. If a test has two possible outcomes, the binomial test can assess the evidence that one outcome is more likely that the other.

## Slide 2

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/E | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

But, in many situations, there are more than two possible outcomes. For example, we might study foraging by bumblebees, and we might want to know what colour flowers the bees prefer. We might do an experiment where each bee can choose one of three flowers with different colours, and we record which flower each bee chooses first. Since there are more than two responses, we cannot do a binomial test here. But, we can do a test called a chi-squared test.

## Slide 3

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/E | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

Like all statistical tests, the chi-squared test works by asking how different an observed result is from the result we would expect by chance alone. To answer than, we start by asking what we would expect by chance alone. In the example I have just given, bees had three flower colours to chose from, and there were 27 bees. So, if they chose completely randomly, we would expect 9 bees to choose each flower colour.

## Slide 4

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/E | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

Now, we need to know how far the observed data is from the expectation. So, we calculate the difference between each observed value and the expected value.

## Slide 5

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

Then, we want to get a single measure for the whole data set. To do that, we square the differences, and we divide each one by the expected value.

## Slide 6

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

For example, 5 squared is 25, and 25 divided by 9 is 2.78.

## Slide 7

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

Then, we sum these values across the whole data set.

## Slide 8

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

The result is what we call a chi-squared statistic.

And, if our null expectation is true, then the values that the chi-squared statistics might take by chance alone follow a known distribution called the chi-squared distribution. So, we can compare our observed chi-squared statistic to the distribution of values we would see by chance, and we can ask, is our chi-squared statistic so large that it is unlikely to have happen by chance alone.

## Slide 9

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

As usual, we will do this in R. The command we will use is chisq.test. The command takes two inputs. The first is a list of our observed values. Here, those values are 4, 15 and 8. The syntax c with parentheses turns these three numbers into a single object. The second input is the expected probabilities. Our null hypothesis is that bees would choose each flower type equally, so we set these equal. In particular, there is a 1 in 3 chance that bees would choose each of the flower colors.

## Slide 10

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

And, here are the results. The chi-squared statistic is 6.89, which is exactly what we calculated by hand. And, there is a p-value. The p-value is small, so we would be unlikely to see a chi-squared statistic this large by chance alone. But, what does that mean? Well, like the ANOVA, the chi-squared test is an omnibus test. That is, it tells us that bees do not choose flowers equally, but it does not tell us which flower types are chosen significantly more often than which others. In other words, we know there are differences, but we do not know where those differences are.

So, can you think of a way to figure that out? I will tell you on the next slide, so pause here if you want a chance to think about it on your own first.

## Slide 11

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

One way to figure out if pairs of outcomes differ is to go back to the binomial test.

For example, our omnibus test told us that bees are not choosing flowers randomly. Now, we might want to follow up by asking if they use yellow flowers differently than red ones. So, we could do a binomial test to find the probability that, in 19 trials (that is, the total number of trials in which bees chose either red or yellow), they would choose the same color 15 or more times. In this case, we can see that the probability is less than 2%.

## Slide 12

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/E | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

- Dunn-Bonferroni correction: α for pairwise comparisons equals [α (for the global test)/(number of pairwise comparisons]

- αpwc = 0.05/3 = 0.0167

**Notes:**

But, we need to be careful of here.
  
There are three different post hoc comparisons we can make: red to yellow, yellow to white, and white to red. Because there are multiple comparisons we can make, the total probability that we find at least one difference that is significant at the level of 0.05 is greater than 0.05 – because we might see that difference in any one of the comparisons.
 
So, typically, we deal with this with what we call a Bonferroni correction. That is, we divide our cut-off for significance by the number of pairwise comparisons we are making. In this analysis, we are making three pairwise comparisons. So, we divide our cut-off for significance by 3. That is, in order to consider a pairwise comparison significant, the p-value would need to be less that 0.0167. The p-value for the difference between red and yellow flowers was 0.019. So, we have only marginal evidence that bees use red and yellow flowers differently.

Because they reduce our threshold for significance, Bonferroni corrections reduce the power of our analyses. And, the more tests we do, the more power we lose. So, researchers often want to minimise the number of post hoc tests they will do. If we are only really interested in a subset of these comparisons, then we might only do a subset of the tests, and we can divide our significance cut-off by a smaller number. But, be careful! We have to choose which comparisons we will make BEFORE we look at the data. If we look at the data first, and only make the comparisons we think are going to be significant, we will bias our results, and our p-values will not be valid. Choosing our analyses after we think we know the results is called HARKing, and it is a big problem in many fields of Science!

## Slide 13

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

There is one more thing I want to notice before we move on. In our previous analysis, our null hypothesis was that bees were equally likely to choose a flower of any color. This is fine if we are doing the experiment in the lab, and every bee has one flower of each color to choose from. But, maybe we are doing the experiment in the field, and maybe there are more red flowers than yellow flowers. Then, our null expectation would be different.

## Slide 14

### Comparing the frequencies of multiple responses

|  | Red | Yellow | White |
| --- | --- | --- | --- |
| visits | 4 | 15 | 8 |
| expectations | 9 | 9 | 9 |
| differences | -5 | 6 | -1 |
| dif2/expect. | 2.78 | 4 | 0.11 |
| Χ2 |  | 6.89 |  |

**Notes:**

We can account for this by changing our null expectation so that it is appropriate for the experiment. For example, if 40% of the flowers were red and 40% were white, and only 20% were yellow, we could set expectation so that bees would visit flowers in proportion to their abundance. This allows us to get an accurate p-value, even if our expectation is not that bees visit each flower color with the same frequency.

## Slide 15

### Comparing response frequencies of different groups

|  | Yellow | Red | proportion red |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 0.351 |
| Species 2 | 71 | 19 | 0.211 |

**Notes:**

Now, in all of the examples we have looked at so far, our goal has been to compare response frequencies to a theoretical expectation. For example, we expected that bees would visit flowers in proportion to their abundance. But, sometimes we are not interested in comparing to theoretical predictions. Sometimes we are simply interested in comparing response frequencies of different groups.
 
For example, we might study two species of bees that visit red and yellow flowers. We might know in advance that both bee species prefer yellow flowers (since most bees cannot see red). So, our question might not be whether bees prefer yellow or red flowers overall, but instead whether the two species of bees have different preference strengths.
 
We can use the same chi-squared approach we just talked about to analyse this data. In this case, we don’t have an a priori expectation for visitation rates. But, we can create an empirical expectation.

## Slide 16

### Comparing response frequencies of different groups

| Observed: | Yellow | Red | observations  in each row |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 37 |
| Species 2 | 71 | 19 | 90 |
| observations in  each column | 95 | 32 | 127 |

**Notes:**

To do this, we can sum up the observations in each row and each column of our table.

## Slide 17

### Comparing response frequencies of different groups

| Observed: | Yellow | Red | observations  in each row |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 37 |
| Species 2 | 71 | 19 | 90 |
| observations in  each column | 95 | 32 | 127 |

| Expected: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 27.7 | 9.3 | 0.291 |
| Species 2 | 67.3 | 22.7 | 0.709 |
| proportion in  each column | 0.748 | 0.252 |  |

**Notes:**

and we can use these to calculate the proportion of each species in the data set, and the proportion of visits to flowers of each colour.

## Slide 18

### Comparing response frequencies of different groups

| Observed: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 37 |
| Species 2 | 71 | 19 | 90 |
| proportion in  each column | 95 | 32 | 127 |

| Expected: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 0.218 | 0.073 | 0.291 |
| Species 2 | 0.530 | 0.179 | 0.709 |
| proportion in  each column | 0.748 | 0.252 |  |

**Notes:**

If the proportions are independent (that is, if each species is equally likely to visit each flower colour), then the expected proportions in each cell are just the products of the row times the column. And, since we know there are 127 observations overall, we can just multiply each proportion by 127 to get the expected number of observations for that cell.

## Slide 19

### Comparing response frequencies of different groups

| Observed: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 37 |
| Species 2 | 71 | 19 | 90 |
| proportion in  each column | 95 | 32 | 127 |

| Expected: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 27.7 | 9.3 | 37 |
| Species 2 | 67.3 | 22.7 | 90 |
| proportion in  each column | 95 | 32 | 127 |

**Notes:**

Then, we can do a chi squared test on this table just like we did a chi squared test on our tables above. That is, we calculate the differences between the expectation and the observations, we square them, we divide by the expectations, and we sum this over the whole table. I am not showing this here because it is messy, and R is going to do it for us.

## Slide 20

### Comparing response frequencies of different groups

| Observed: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | 37 |
| Species 2 | 71 | 19 | 90 |
| proportion in  each column | 95 | 32 | 127 |

| Expected: | Yellow | Red | proportion in each row |
| --- | --- | --- | --- |
| Species 1 | 27.7 | 9.3 | 37 |
| Species 2 | 67.3 | 22.7 | 90 |
| proportion in  each column | 95 | 32 | 127 |

**Notes:**

Now, this thing that we want to analyse is called a contingency table. And, sadly, getting this table into R is a bit ugly. So, I will walk you through the command we will use to do this.

## Slide 21

### Comparing response frequencies of different groups

| Observed: | Yellow | Red |
| --- | --- | --- |
| Species 1 | 24 | 13 |
| Species 2 | 71 | 19 |

**Notes:**

I am going to name my contingency table “choice,” although of course this is just a name, so I could use any name I want to. And, the command I am going to use to make the table is called matrix. Matrix takes several different inputs, and I will explain each one.

## Slide 22

### Comparing response frequencies of different groups

| Observed: | Yellow | Red |
| --- | --- | --- |
| Species 1 | 24 | 13 |
| Species 2 | 71 | 19 |

**Notes:**

First, it takes a list of numbers. The numbers are the entries in the contingency table. This c and parentheses binds these numbers into a single object. The order is important here. The first number is the first number from the first column, and the entries move down the column. When we reach then end of the first column, we start the next column. We continue until we have entered all of the numbers from the table.

## Slide 23

### Comparing response frequencies of different groups

| Observed: | Yellow | Red |
| --- | --- | --- |
| Species 1 | 24 | 13 |
| Species 2 | 71 | 19 |

**Notes:**

Now, this first parameter is just a list of numbers. To turn this into a matrix, R needs to know how many rows it has. Here, there are two rows. If R knows how many rows there are, it can figure out how many columns there will be.

## Slide 24

### Comparing response frequencies of different groups

| Observed: | Yellow | Red |
| --- | --- | --- |
| Species 1 | 24 | 13 |
| Species 2 | 71 | 19 |

**Notes:**

Finally, I am naming the rows and columns. We don’t absolutely have to do this, but it makes it easier to check the table for correctness. Dimnames tells R that the names in the list will be the row and column names. The first list of names is for the rows, and the second list of names is for the columns.

## Slide 25

### Comparing response frequencies of different groups

|  | Yellow | Red |
| --- | --- | --- |
| Species 1 | 24 | 13 |
| Species 2 | 71 | 19 |

**Notes:**

When we enter this command, we create the matrix called choice. And, if you want to see it to make sure it is correct, you can simply enter its name, choice, into the R console.

So, it is correct. And, it is beautiful.

## Slide 26

### Comparing response frequencies of different groups

**Notes:**

From here, it easy. We can simply apply the command chisq.test to the object choice, and we get our result. In this case, the p-value is greater than 0.05, so we do not have evidence that these bee species used red and yellow flowers differently.

## Slide 27

### Comparing response frequencies of different groups

**Notes:**

In the example I just showed, we studied a 2 x 2 contingency table. But, we could do this with a table of any size. For example, here is similar test with three species of bees and three follower colours. If you take a minute to look at the code, you will see it is exactly analogous to the code for the 2 x 2 table.

In this case, the p-value is low. So, we have evidence that these bee species used these flower colours differently. But, because this is still an omnibus test, we don’t know which species used which flower colours differently from which other species.

## Slide 28

### Comparing response frequencies of different groups

**Notes:**

If we wanted to know which pairs of species used which pairs of flowers differently, we could go back to examining the various 2 x 2 tables that this table contains. But, there are a lot of them,

## Slide 29

### Comparing response frequencies of different groups

**Notes:**

and we have to make a Bonferroni correction for every post hoc test we want to do. So, unless we know before we start that there are specific comparisons we want to make, we will not have a lot of power to detect pairwise differences. If we do know that there ae specific comparisons we will want to make, it is best to define those in advance so we can do just that subset of tests, and keep as much power as we can in our study.

So, that is all I have to say for today. Thanks again everyone for tuning in. This week we will do practical 5, and as always you can find on Blackboard. I will monitor the discussion forum, and hold a live drop-in session from 11:00 to 1:00 on Friday!

Good luck, and please feel free to contact me if you have questions!
