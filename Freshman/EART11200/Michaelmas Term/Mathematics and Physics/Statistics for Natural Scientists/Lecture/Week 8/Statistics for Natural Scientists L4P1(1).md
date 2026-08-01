---
title: "Statistics for Natural Scientists L4P1(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 8/Statistics for Natural Scientists L4P1(1).pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)Lecture 3.1: Understanding the effects of quantitative predictors

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

**Notes:**

Hi all! Welcome back to Statistics for Natural Scientists.

In the previous two sessions, we have considered data in which the predictors were categorical – things like self-reported sex, or subspecies of elephant– and the responses were numerical – things like height or mass. However, in many studies, the predictors are also numerical. For example, we might want to know how body mass depends on height. The approaches we have studied so far can’t answer this kind of question. Today, we will look at one that can.

As we go through today's lecture, remember that all the code I will use can be found in the Blackboard folder with this week’s practical.

## Slide 2

### 1994 Canadian Survey of Income and Labour Dynamics for Ontario

**Notes:**

The data we will work with today was collected as part of the Canadian Survey of Income and Labour Dynamics for the province of Ontario in 1994. I have imported the data into R using the same read.csv command we have used in previous weeks. To display the data, I am using the command “head.” ”Head” shows us just the first few rows of the data, which is enough to see what the data looks like, without filling the whole R console.

The data here is from a random survey of workers in Ontario in 1994. As always, each row is a data point, and each column is description of that data point. The first column is each worker’s hourly wage. The second column is their age, and the third is their sex. The 4th column is their native language. You may know that Ontario borders Quebec, so there are a lot of native French speakers in Ontario. However, all non-English languages are grouped into “other.” The last column, “school,” tells us how many years of formal education each worker has had. We will ignore the column apt for today.

Now, you are putting a lot of money and a lot of effort into getting an education right now, so one question you might be interested in answering is whether that will ultimately pay off. That is, do people with more education earn more money?

## Slide 3

**Notes:**

To get some intuition about whether this might be true, we can make a scatter plot of the Canadian income data. Here I am showing hourly wage for workers with different amounts of education. Each circle represents one person. The x-axis is that person’s number of years of education, and the y-axis is their hourly wage. At a glance, it looks like there might be a pattern. Certainly no one without at least some university experience is making more than about $30 per hour, and no one with a degree is making less than $10.

## Slide 4

**Notes:**

The pattern becomes even a little clearer if we put a line through the data.

We can think of this red line as a prediction of hourly wage based on education. Every point in the figure has some deviance from the line: that deviance is the error in our prediction. For example, the blue bar towards the right side of the panel shows the error for one of the data points.

There are a lot of different way we could put a line through the data – we could move this line up or down, or change its slope. But, there is exactly one line that minimises the sum of the squared error across all of the points in the data set. We call this the line of best fit. That is the line I am showing in here.
 
Now, every cloud of data points has a line of best fit, even if those data points are generated completely at random. What we want to know is, does our line of best fit explain more of the variability in the data than we would expect for a data set where the points were generated completely at random. That is, does it explain more of the variability than we would expect it to explain by chance alone?

## Slide 5

**Notes:**

We can answer this question using the same approach we used for ANOVA in the last lesson before Easter break.
 
In this figure, the black dotted line shows the mean wage for all individuals in the data set. The vertical green line is the part of the deviation from the mean in this one point that is explained by the line of best fit. The vertical blue line is that part that is not explained by the line of best fit. That is, it is the unexplained error. We can take the sum of the squared deviance that is explained, compare that to the sum of the squared deviance that is not explained, and ask if the ratio of explained to unexplained variability is larger than we would expect by chance. If the answer is yes, then we have reason to believe that there is some real relationship between the predictor and the response variable. In this case, we would have reason to believe that education really explains something about wage.

## Slide 6

**Notes:**

To illustrate what I mean when I say “ratios we might see by chance,” here is one example. In this figure, I have kept all of the wages from the previous figure, but I have reassigned them to people at random, regardless of their education. So, there is no relationship between education and wage in this data. As we would expect, the mean wage has not changed, because the data set includes all the same wages. And, there is still a line of best fit, but now it is much flatter. The proportion of the variability that is explained by the line of best fit is smaller, and the proportion that is unexplained is larger. If education almost always explains less of the variability in randomisations than it does in the real data, then the pattern in the real data is probably not just chance, and there is probably a real relationship between education and hourly wage.

This is the idea behind an analysis we call linear regression.

## Slide 7

### Conducting linear regression in R

**Notes:**

Now of course, we could conduct lots of randomisations like the one I just showed, ask how often education explains as much or more of the variance in wage as in real data, and use this to infer a p-value. But, it is easier to make R do the analysis for us.

The code for this is exactly analogous to the code we used for ANOVA. Here, the command lm() tells R to make a linear model, and w.lm is the name I am giving to the model we create. The variable before the tilde is the response variable, and the variable after the tilde is the predictor. This data=ci tells R to find these variables in the data set called ci.

This code creates the model.

## Slide 8

### Conducting linear regression in R

**Notes:**

And, just as with ANOVA, the command summary shows us the results.

There are several important pieces of information produced here. The first one is the p-value associated with your predictor. I have circled this in red. As you can see, ours is very small. That means that we would be unlikely to see a relationship this strong by chance alone, so we infer that the relationship is real. That is, education really predicts the hourly wage.

## Slide 9

### Conducting linear regression in R

**Notes:**

But, by itself that is not very useful. We would also like to know how education affects hourly wage. The answer to that is here in the estimate column. We can think of this estimate as a slope. For every additional year of formal education, workers earned an additional 91 cents per hour.

## Slide 10

### Conducting linear regression in R

**Notes:**

Sometimes you might also be interested in this R2 value. The R2 value tells you what proportion of the variability in the data set is explained by your predictors. Here, it is about 13.5%. So, earnings vary with education, but there is still a lot of variability that is not explained by education.

We might ask whether this value of R2 is “good.” Well, that depends on the purpose of the study. If your goal is just to show that wage varies with education, then a low R2 doesn’t matter. The p-value is enough to make your argument. But, if your goal is to use education to predict wage, the low R2 means you probably cannot do that accurately. There is too much variability in the data that is not explained by education to make an accurate prediction using education alone.

## Slide 11

### Reporting the results of a simple linear regression.

- Legend: Hourly wage in C$ as a function of years of formal education for 100 workers in Ontario, Canada in 1994.

- In text: We found that hourly wage increased by C$0.91 for every additional year of formal education (t = 3.92, df = 98, p = 0.0002).

**Notes:**

So, how do we report this?
 
I would report it with a simple scatter plot like this, with the best-fit line plotted through the data. This looks more complicated than bar charts we made for ANOVA, but it is actually much easier to produce, as you will see in the practical today. As always, the figure is accompanied by a legend that tells readers what they are looking at.
 
In the text, I would report both the p-value and the slope of the line. If you have reported your sample size in your methods, the t-statistic and degrees of freedom are redundant, but some people like to see them anyway, and some journals require you  to report them.

## Slide 12

### Conducting linear regression in R

**Notes:**

Now, there is another piece of information in our model output that might be useful to us, if it were reported in a slightly different form. That is the intercept. The intercept tells us where the line of best fit crosses the y-axis. In other words, it is the predicted value of the response variable when the value of the predictor is zero.

## Slide 13

### Mean-centering can make the intercept more useful.

- C$3.03 ->

**Notes:**

We can see that graphically in this figure. This is the same plot of hourly wage as a function of education that we looked at before, but zoomed out so we can see more of the x-axis. The y-axis is the dashed vertical line. The y-axis appears where the predictor is zero. The intercept is the point where the red line of best fit crosses the y-axis. This occurs at an hourly wage of C$3.03. So, if a person had no education, we would expect them to earn C$3.03 per hour.

Now, as presented here, this intercept is not very useful. It claims to tell us what a worker would earn if they had no formal education at all. But, there is no one in our data set with no education. In Canada, it is the law that you must go to school for 8 years. And, it is bad practice to use a model to predict responses outside the range of those that we observed, because we have no evidence that our results hold out there. In fact, in this case, they can’t hold, because Canada has a minimum wage.

## Slide 14

### Mean-centering can make the intercept more useful.

**Notes:**

But, we can make the intercept useful with a procedure called mean centering. When we mean center a predictor, we simply subtract the mean from each measured value. In R, we can create a new mean centered predictor using this command. Here we are telling R to start with the data in the column “school” of the data set “ci,” and then subtract the population mean from each person's education. We are telling R to call this new variable we have created “mc_school.”

## Slide 15

### Mean-centering can make the intercept more useful.

**Notes:**

To see what this has done, we can use the command data.frame to display the original variable school and the transformed variable mc_school side-by-side. The mean education in the population was about 13.65 years. So, mc_school is simply the original value minus 13.65.

Now, we can use mc_school just like we would any other predictor.

## Slide 16

### Mean-centering can make the intercept more useful.

**Notes:**

So, let’s do that. Here, I am refitting exactly the same model we built before, but replacing school with mean centered school.

The first thing to notice is that the p-value, the effect of school, and the R^2 value have not changed at all.

## Slide 17

### Reporting the results of a simple linear regression.

- mean-centered data

- raw data

**Notes:**

In fact, if we pot the new model, we will see that the only thing that has changed are the numbers on the x-axis. They are reduced by the mean, which is what we should expect, because we subtracted the mean from each person’s years of education.

## Slide 18

### Mean-centering can make the intercept more useful.

**Notes:**

But, there is something that has changed in our model, and that is the intercept. The intercept means something different now. I will tell you what that is in the next section of the lecture. But as a test of your understanding, I encourage you to take a minute or two and see if you can figure it out on your own before moving on.
