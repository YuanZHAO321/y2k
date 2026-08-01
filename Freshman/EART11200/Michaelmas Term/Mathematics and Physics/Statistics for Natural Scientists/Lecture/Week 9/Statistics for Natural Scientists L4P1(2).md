---
title: "Statistics for Natural Scientists L4P1(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 9/Statistics for Natural Scientists L4P1(2).pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 4.1: Categorical responses to categorical predictors (binomial test)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

***Hi all! Welcome back to Statistics for Natural Scientists.

Before I start today’s lecture, I want to step back and think about the process of learning to analyse data. When you learn any new skill, it is easy to focus on how much you have left to learn. And, while this is true for any skill, I think it is especially true for statistics. Every time you learn a new method, you will find that there are additional methods you don’t know, or data types you don’t know how to handle, or details about the methods you have learned that you still don’t fully understand. And, no matter how long you stay in Science, and how much you learn about analyzing data, that process will never stop. The more you learn, the more you will realise that you have a lot left to learn.

Because of that, I think it is really important to step back from time to time and think about everything you have learned. Four weeks ago, most of you had never opened R or written a single line of R code. Now, you can open R, read and manipulate data, and conduct a set of fundamental statistical analyses. You can make figures to represent your results. It is not always easy, and maybe it takes a few tries to get it right, but you can do it. You can start with codes that do one thing, and you can modify them to do something different that is useful to you. And, when you think about it, this is kind of amazing. You haven’t just memorized some facts – you have learned to use a new and powerful tool, and to think about data in a new way. You can do something that most people, and even many early career scientists, cannot do. So, take a minute to commend yourself for everything you have achieved so far. I am really impressed with how well people are progressing, and you should be too!

Today, we will add a new test to your analytical tool kit. We will walk through the ideas, and then we will look at how to implement those in R. As we go through today's lecture, remember that all the code I will use can be found in the Blackboard folder with this week’s practical.

## Slide 2

### Statistical tests we have studied so far:

| Test | Predictor | Response |
| --- | --- | --- |
| t-test, or Wilcoxon | Categorial (2 groups) | Numerical |
| ANOVA, or Kruskal-Wallace | Categorial (>2 groups) | Numerical |
| Linear regression, or Spearman’s rank correlation test | Numerical (or dichotomous categorical) | Numerical |
| ? | ? | Categorical |

**Notes:**

Up to this point, we have looked at t-tests, ANOVA, and linear regression. In each of these tests, we have asked whether there is a relationship between a predictor and a response variable. In t-tests and ANOVA, our predictors were categorical (for example, sexes, or breeds, or species). In linear regression, our predictors were numerical (for example, parent’s heights). However, in every case, our response variable has been numerical. That is, we have measured each independent response as a number (for example, students’ heights, or masses of elephants, or mortality rates in flocks of sheep).

However, sometimes, we may study systems in which our responses are categorical. For example, the very first example I gave in this unit was about flipping coins. Each flip was an independent trial, and the response was a category. It was either heads or tails. So, it was not a number.

Or, we might imagine an experiment where we are looking at bees’ preferences for flowers of different colours. If we let bees choose flowers and we look at the choices they make, the responses are colours, not numbers. How can deal with this kind of data? Today, we will look at some approaches for doing that.

## Slide 3

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

**Notes:**

If you think way back to the first example I talked about in this unit, you will remember it was about flipping coins. We wanted to know if a particular coin was fair. So, we flipped the coin 100 times, and we got 62 heads. Then, we asked, if the coin were fair, what is the probability we would see the same result at least 62 times just by chance alone. And, we obtained this probability, that is our p-value, using a simulation.

But, some of you may have noticed that we could have found our p-value exactly by math instead of by simulation. We can look at how to do that with a simple example. Let’s ask, if we flip a coin 7 times, what is the probability of getting 2 or fewer tails?

## Slide 4

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

**Notes:**

To start, we will not assume that the coin is fair. Instead, consider a coin that has some probability p of coming up heads. So, the probability of coming up tails is just (1 - p).

## Slide 5

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 7 heads and 0 tails:

**Notes:**

So, what is the probability that we get heads all seven times?

## Slide 6

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 7 heads and 0 tails:

- p

**Notes:**

Well, the probability of getting heads on the first flip is just p.

## Slide 7

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 7 heads and 0 tails:

- p p = p2

**Notes:**

The probability of getting heads on the second flip is p again. So, the probability of getting heads on the first two flips is p times p, or p^2.

## Slide 8

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 7 heads and 0 tails:

- p p p p p p p = p7

**Notes:**

And the probability of getting heads on each of the first 7 flips is p x p x p x p x p x p x p, or p^7.

## Slide 9

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

**Notes:**

So, that’s easy. But, what is the probability that we get 6 heads and 1 tail?

## Slide 10

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

- H H H H H H T

**Notes:**

Well, one way that could happen would be if we got 6 heads in row, and then a tail.

## Slide 11

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

- H H H H H H T

- p p p p p p (1 – p) = p6 (1 – p)

**Notes:**

The probability of getting heads is p each time, and then the probability of getting tails is (1-p). So, the probability of getting this series of results is p^6 time (1-p).

## Slide 12

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

- p p p p p p (1 – p) = p6 (1 – p)

- p p p p p (1 – p) p = p6 (1 – p)

- H H H H H T H

**Notes:**

But, that is not the only way to get 6 heads and a tail. We might also get heads 5 times, then a tail, then another head. There are still 6 ps, and one (1-p), so the probability of getting exactly this outcome is also p^6 times (1-p)

## Slide 13

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

- p p p p p p (1 – p) = p6 (1 – p)

- p p p p p (1 – p) p = p6 (1 – p)

- p p p p (1 – p) p p = p6 (1 – p)

- H H H H T H H

**Notes:**

Or, we could get 4 heads, a tail, and 2 more heads. Again, the probability of getting this outcome is p^6 times (1-p)

## Slide 14

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 6 heads and 1 tail:

- p p p p p p (1 – p) = p6 (1 – p)

- p p p p p (1 – p) p = p6 (1 – p)

- p p p p (1 – p) p p = p6 (1 – p)

- …

- 7 p6 (1 – p)

**Notes:**

In all, there are seven different places where the tail could appear in our series of flips. So, there are seven different ways we could get 6 heads and a tail, and the probability of each one is p^6 times (1-p). So, in total, the probability of getting 6 heads and a tail is 7 times p^6 times (1-p).

## Slide 15

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 5 heads and 2 tails:

**Notes:**

Now, what about 5 heads and two tails?

## Slide 16

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 5 heads and 2 tails:

- p p p p p (1 – p) (1 – p) = p5 (1 – p)2

- H H H H H T T

**Notes:**

Well, one possibility is that we could get 5 heads and then two tails. The probability of getting exactly this result is p^5 time (1-p)^2. There are other ways to get 5 heads and 2 tails, but if there are five heads and 2 tails in the sequence, then the probability of getting that sequence will always be p^5 times(1-p)^2. But, how many different ways are there to get 5 heads and a tail?

## Slide 17

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 5 heads and 2 tails:

- p p p p p (1 – p)  (1 – p) = p5 (1 – p)2

- n	      n!

- k	  k!(n-k)!

- =

**Notes:**

Well, there is a formula for this, and it is called “n choose k.” We write it like this, with an n over a k, but without the bar that indicates division. To calculate n choose k, we use factorials. The factorial of a number is just the product of the integers from 1 to that number. So, for example, 7 factorial is just 7 time 6 times 5 times 4 times 3 times 2 times 1.

N choose k is equal to n factorial divided by the product of k factorial and n – k factorial.

## Slide 18

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 5 heads and 2 tails:

- p p p p p (1 – p)  (1 – p) = p5 (1 – p)2

- n	      n!

- k	  k!(n-k)!

- =

- 7

- 2

- p5 (1 – p)2

**Notes:**

So, putting these two ideas together, the probability of getting 5 heads and 2  tails in a given order is p^5 time (1-p)^2, and there are 7 choose 2 ways to do that, so the probability of getting 5 heads and 2 tails in any way is 7 choose 2 times p^5 times (1-p)^2.

## Slide 19

### What is the probability of getting 2 or fewer tails in 7 flips of a coin?

- P(heads) = p

- P(tails) = (1 – p)

- Probability of 5 heads and 2 tails:

- p p p p p (1 – p)  (1 – p) = p5 (1 – p)2

- n	      n!

- k	  k!(n-k)!

- =

- 7

- 2

- p5 (1 – p)2

**Notes:**

Finally, remember that we are the probability of getting 2 or fewer tails. So, we want to add up the probability of getting 0 tails, the probability of getting 1 tail, and the probability of getting 2 tails. We can do that with the summation here.

## Slide 20

### What is the probability of getting x or fewer tails in n flips of a coin?

- binomial test

**Notes:**

More generally, we can compute the exact probability of getting x or fewer tails in n flips of a coin using this expression here. This called a binomial test.

So, thinking back to our original question, we flipped a coin 100 times and got 62 heads. We wanted to know the probability we would get the same result at least that many times by chance alone, if the coin were fair. If the coin were fair, then p would = 0.5. We can set n to 100, x to 62, and plug these into the test. This is a one-tailed test, so we would have to multiply by 2, because we want the probability of getting at least 62 heads or at least 62 tails.

## Slide 21

### What is the probability of getting x or fewer tails in n flips of a coin?

**Notes:**

Happily, R can do this test for us. The command is binom.test. The first parameter for the test is our x, and the second parameter is our n. I am setting p=0.5, because the null hypothesis we are testing is that the coin is fair. I have specified alternative=“two.sided” to make sure that R does a two-tailed test.

## Slide 22

### What is the probability of getting x or fewer tails in n flips of a coin?

**Notes:**

And here is our p-value.

Now that you have the p-value, you may wonder if you really need to know the formula for the binomial test at all. You probably don’t. At the very least, you certainly shouldn’t feel like you have to memorise it. But, having a general understanding of what statistical tests are doing is important. There is no magic in statistics. Tests work in particular ways, and for particular reasons. If we understand those, then it is easier to apply them correctly, and easier to recognize when something has gone wrong.

So, I set this example up by talking about coin-flipping. But, we could use this test for any situation where a trial can have two possible outcomes. For example, is the sex ratio in a population biased? In this case, each individual is a trail, and the outcome is whether that individual is male or female. Or, we could ask if a football team wins more often than we would expect by chance.

But, sometimes we might study a system where there are more than two possible outcomes. For example, a bee might have three flower colors to choose from, and we might want to know if it has a preference for one color over another. Or, and animal might have many behaviours it can perform, and we might want to know if it performs some more than others. In the next section of this lecture, we will look at methods for dealing with this kind of data.
