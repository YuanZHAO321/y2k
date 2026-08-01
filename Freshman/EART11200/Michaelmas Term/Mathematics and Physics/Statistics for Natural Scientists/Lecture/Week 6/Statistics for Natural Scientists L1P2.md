---
title: "Statistics for Natural Scientists L1P2"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Lecture/Week 6/Statistics for Natural Scientists L1P2.pptx"
type: slides
---

## Slide 1

### Statistics for Natural Scientists(EART11200 Toolkit)

- Tucker Gilman

- tucker.gilman@manchester.ac.uk

- Asynchronous Lecture 1 Part 2

**Notes:**

Hi everyone. Welcome back to asynchronous lecture 2 of Statistics for Natural Scientists.

## Slide 2

### The t-distribution approximates Monte Carlo outcomes.

- William Sealy Gosset

- (Student)

**Notes:**

In the first part of this lecture, we looked at how we might test a hypothesis using the Monte Carlo method.

The Monte Carlo method is a powerful and intuitive way to ask if differences we observe in a data set are larger than we would expect to see by chance alone. But, historically, there was a problem with this method. Until a few years ago, computers were not fast enough to do simulations like this. It could take days to get an answer.

A solution to this was developed by a researcher named William Sealy Gosset, who published under the name “Student.” Gosset noticed that, under certain conditons, the histograms that we get by resampling follow a predictable distribution. If we know the variance in our sample and we know our sample size, then we can calculate this distribution without resampling. Then, we can compare our observed data to the calculated distribution. The distribution is called a t-distribution, and the test is called a t-test.

And, we can do a t-test in R.

## Slide 3

### Arranging your data for analysis

**Notes:**

Now, before we begin working with R, let’s think about our data, and how we should arrange it for analysis. Here, I am showing you an Excel file with the height data that we were just analyzing. In this data, each row represents a data point – in this case, a person. Each column is a description of that person. The first column is the order in which they responded to a poll, the second column is their height, and the third column is their sex. Note that sex is indicated with an “m” for males or an “f” for females. We will use this later. There is more information in the data, but we won’t use that right now.

Notice that the first row in the spreadsheet is headers. That is, the first row tells us what data we can find in the corresponding column.

It is very important here that each row is a data point and each column is a description of the data. If you set your data up like this, it will be very easy to analyze. If you set it up in any other way, it may be very difficult to analyse.

Now, I am showing you this data in Excel, but I have used Excel’s ”Save As...” function to save this as a csv. A csv is simple text file without Microsoft’s fancy field codes, and programmes like R can read it.

## Slide 4

### Importing data into R

**Notes:**

Now, let’s switch to R. This is the screen you will see when you open RStudio for the first time.

Before we can analyse the data, we will need to import it into R. There are several steps in this process, but don’t feel like you need to memorise these now. This week’s practical will walk you through the steps again. And, we will do this again and again over the next few weeks. So, you will learn it by doing it.

## Slide 5

### Importing data into R

**Notes:**

To import data, R needs to know where to find it. So, the first thing we will do is set the folder where we have saved the data as the working directory. We can do this from the file panel in the lower right of the RStudio application.

## Slide 6

### Importing data into R

**Notes:**

When we navigate to the directory with the data, we can see the data file we are looking for. In this case, the file is “height_data.csv.” But, don’t open. Instead, we will set this directory as our working directory so R can find the data itself.

## Slide 7

### Importing data into R

**Notes:**

To do this, first click on the blue gear icon to open a drop-down menu, and then select “set as working directory.”

## Slide 8

### Importing data into R

**Notes:**

When you do this, a command will appear in the R console. This command sets the directory we have just chosen as the working directory. Now, we are ready to import the data.

## Slide 9

### Importing data into R

- hd=read.csv("height_data.csv",header=TRUE)

**Notes:**

We will import the data using a command called “read.csv.” The command is easy to understand if we break it down into its component parts.

## Slide 10

### Importing data into R

- hd=read.csv("height_data.csv",header=TRUE)

**Notes:**

First, the part on the far left underlined in red is the name I am giving to the data. We can call the data anything we want to. I am calling it hd to remind myself that it is height data.

## Slide 11

### Importing data into R

- hd=read.csv("height_data.csv",header=TRUE)

**Notes:**

To the right of the equal sign, we have the command. Here the command is read.csv.

## Slide 12

### Importing data into R

- hd=read.csv("height_data.csv",header=TRUE)

**Notes:**

Next, we have the name of the file to be imported. Our data is saved in a file named “height_data.csv.”

## Slide 13

- Importing data into R

- hd=read.csv("height_data.csv",header=TRUE)

**Notes:**

Finally, we have the statement header = True. This tells R that the first row in the data set contains the name of the data in each column.

Now, pay close attention to syntax of this command, and all other commands in R. If your commas, periods and quotation marks are missing or in the wrong places, your commands will not work!

You can find commands with the correct syntax in the DropBox folders for each practical, and I recommend that you take advantage of these by cutting and pasting whenever you can!

## Slide 14

### Importing data into R

**Notes:**

If you want, you can enter the command we just created directly into the R console, in the bottom left panel of the RStudio app.

## Slide 15

### Importing data into R

**Notes:**

But, I prefer to write my code in the scripting panel in the upper left of the app. The scripting panel contains an R document. If I enter a command here, R will color-code the command, which makes it easier to see the component parts. If I make a mistake writing the command and I need to edit it, I can do that here. And, when I have gotten a command or a set of commands just right, I can save the whole document so I can use the the commands to analyse the same data again later, or I can modify them to analyse new data.

## Slide 16

### Importing data into R

**Notes:**

To execute code we have written in the scripting panel, we can simply select it and then click on run in the menu for the panel.

## Slide 17

### Importing data into R

**Notes:**

When we do this, the command will appear in the R console.

We did not get an error message, so that means the command has run successfully. So, we have created an object called hd. But, we cannot see what that object is. If we want to see it, we can simply type the name of the object into the R console and press return.

## Slide 18

### Importing data into R

- hd

- resp height sex fheight mheight brothers sisters feldcourse degree

- 1     1  1.740   m   1.778   1.524        0       1         ab    zoo

- 2     2  1.700   f   1.880   1.620        1       0         ca    bio

- 3     3  1.640   f   1.820   1.630        2       0         ab    zoo

- 4     4  1.670   f   1.850   1.650        0       1         mb    bio

- 5     5  1.630   f   1.800   1.570        0       1         mb   seas

- 6     6  1.770   f   2.000   1.730        0       1         ab    bio

- 7     7  1.800   m   1.600   1.500        0       1         be    zoo

- 8     8  1.800   m   1.700   1.650        0       0         ab    bio

- 9     9  1.700   f   1.800   1.600        0       1         mb    bio

- 10   10  1.870   f   1.680   1.530        1       1         ca     ls

- 11   11  1.700   m   1.820   1.670        1       0         ca    bio

- 12   12  1.630   f   1.830   1.600        0       3         be    bio

- 13   13  1.650   f   1.580   1.530        1       2         ca    bio

- 14   14  1.600   f   1.700   1.600        1       0         ca    zoo

- 15   15  1.540   f   2.500   1.530        1       3         be    bio

- . . .

**Notes:**

And, the output will look like this. This is exactly the same height data we saw in the csv earlier.

Very often, real data sets will be too large to easily display, and that is the case with our height data. There are more rows than we can see at one time. And, we might not really need to see them all anyway. Often, all we really want to know is that the data imported successfully. Or, maybe we want to remind ourselves of the names of the columns in the data set.

## Slide 19

### Importing data into R

- head(hd)

- resp height sex fheight mheight brothers sisters feldcourse degree

- 1    1   1.74   m   1.778   1.524        0       1         ab    zoo

- 2    2   1.70   f   1.880   1.620        1       0         ca    bio

- 3    3   1.64   f   1.820   1.630        2       0         ab    zoo

- 4    4   1.67   f   1.850   1.650        0       1         mb    bio

- 5    5   1.63   f   1.800   1.570        0       1         mb   seas

- 6    6   1.77   f   2.000   1.730        0       1         ab    bio

**Notes:**

A convenient command for doing this is “head.” If I enter head(hd) into the R console, R will display just the first few rows of the object hd.

## Slide 20

### Implementing a t-test in R

**Notes:**

So, let’s move on to implementing a t-test. As before, we can write our code in the scripting panel, but to make the text big enough to read, from now on I will just put the commands directly on the slides.

Now, recall that t-tests are about comparing means. In our Monte Carlo analysis, we asked whether the mean height of men was different from the mean height of women. So, before we even do the test, we might want to know what the mean heights of men and women are. Let’s find out.

## Slide 21

### Implementing a t-test in R

- hd$height

- [1] 1.740 1.700 1.640 1.670 1.630 1.770

- [7] 1.800 1.800 1.700 1.870 1.700 1.630

- [13] 1.650 1.600 1.540 1.720 1.540 1.420

- [19] 1.630 1.600 1.702 1.670 1.600 1.700

- [25] 1.800 1.760 1.700 1.830 1.800 1.780

- [31] 1.800 1.680 1.600 1.700 1.500 1.930

- [37] 1.570 1.640

**Notes:**

We saw earlier that we can see our full data set by entering its name into the R console. If we want to see just people's heights without the rest of the data, then we can instead enter hd$height. This tells R to choose just the column height from the data set hd. So, these are all the heights in the data, in the same order they appear in the data frame hd.

## Slide 22

### Implementing a t-test in R

- hd$height[which(hd$sex=="m")]

- [1] 1.74 1.80 1.80 1.70 1.72 1.63 1.80

- [8] 1.76 1.83 1.80 1.78 1.50 1.93

**Notes:**

We can take this a step further using a command called “which.” In the command you see here, the hd$height part tells R to choose only the column height from the data frame hd. Then, the part in the square brackets tells R to choose only the entries in rows where sex equals “m”. So, R chooses the heights of all people in the data sex who have "m" in the sex column – that is, the heights of all the males.

Pay careful attention to the double equals sign in the which command. This double equals tells R to compare things, in this case the sex data and the letter “m.” If instead we had used a single equals, R would think we were telling it that all sexes in the data are m, and it would change everyone in the data set to a male!

## Slide 23

### Implementing a t-test in R

- male_height=hd$height[which(hd$sex=="m")]

**Notes:**

If, instead of displaying the male heights, we want to store them so we can use them later, we can just give them a name. Here, I have called them “male_height,” because it is easy to remember.

## Slide 24

### Implementing a t-test in R

- male_height=hd$height[which(hd$sex=="m")]

- mean(male_height)

- [1] 1.753077

**Notes:**

Then, I can calculate the mean height of men in the data set using the command “mean.”

## Slide 25

### Implementing a t-test in R

- male_height=hd$height[which(hd$sex=="m")]

- mean(male_height)

- [1] 1.753077

- female_height=hd$height[which(hd$sex=="f")]

- mean(female_height)

- [1] 1.65288

**Notes:**

And, I can do exactly the same thing for female height. So, we can see that men in our data set were about 10 cm taller than women. To find out if that difference is larger than we would expect to see by chance, we can do a t-test.

I will show the t-test next, but before I do that, I want to pause for a second. If you have been trying to memorize these commands as we go along, you are probably thinking that this is really painful. But, remember, you do not have to memorise this. All of the code is in the handbook and in the Dropbox folder, and I will never ask you to do any of this without consulting those. My goal here is just to show you how these commands work. When you actually use them, you can look them up. There is no reason to learn by memorization. You will learn what you need by using these commands when you analyse data!

## Slide 26

### Implementing a t-test in R

- > t.test(male_height,female_height)

**Notes:**

Okay, so let’s move on to asking whether the observed difference between male and female heights is large enough that it is unlikely to be due to chance. That is, let’s do the t-test.

This is the command we will use. It has three parts.

## Slide 27

### Implementing a t-test in R

- > t.test(male_height,female_height)

**Notes:**

The first part is the command itself, t.test.

## Slide 28

### Implementing a t-test in R

- > t.test(male_height,female_height)

**Notes:**

The next two parts are the arguments. These are the two sets of values that we want to compare. In this case, our test will compare the heights of men to the heights of women.

## Slide 29

### Implementing a t-test in R

- > t.test(male_height,female_height)

- Welch Two Sample t-test

- data:  male_height and female_height

- t = 2.9402, df = 21.611, p-value = 0.007665

- alternative hypothesis: true difference in means is not equal to 0

- 95 percent confidence interval:

- 0.02944923 0.17094461

- sample estimates:

- mean of x mean of y

- 1.753077  1.652880

**Notes:**

When we execute the command, this is the result. There are several important pieces of information here.

## Slide 30

### Implementing a t-test in R

- > t.test(male_height,female_height)

- Welch Two Sample t-test

- data:  male_height and female_height

- t = 2.9402, df = 21.611, p-value = 0.007665

- alternative hypothesis: true difference in means is not equal to 0

- 95 percent confidence interval:

- 0.02944923 0.17094461

- sample estimates:

- mean of x mean of y

- 1.753077  1.652880

**Notes:**

First, these are the means of the two groups we analysed. They appear in the same order that we put them in the t.test function. So, the first number is the average height of men, and the second number is the average height of women in our data. The difference is about 0.1 meters. That should make sense, because that is what we found before.

## Slide 31

### Implementing a t-test in R

- > t.test(male_height,female_height)

- Welch Two Sample t-test

- data:  male_height and female_height

- t = 2.9402, df = 21.611, p-value = 0.007665

- alternative hypothesis: true difference in means is not equal to 0

- 95 percent confidence interval:

- 0.02944923 0.17094461

- sample estimates:

- mean of x mean of y

- 1.753077  1.652880

**Notes:**

The next important piece of information is the p-value. It is not exactly what we calculated with our simulations, but it is pretty close. It is much smaller than 0.05, so we have evidence that men and women have different heights in the population we are studying.

## Slide 32

### Implementing a t-test in R

- > t.test(male_height,female_height)

- Welch Two Sample t-test

- data:  male_height and female_height

- t = 2.9402, df = 21.611, p-value = 0.007665

- alternative hypothesis: true difference in means is not equal to 0

- 95 percent confidence interval:

- 0.02944923 0.17094461

- sample estimates:

- mean of x mean of y

- 1.753077  1.652880

**Notes:**

Finally, we have the t-statistic and degrees of freedom. Back before we had computers, we calculated these numbers by hand, and used them to find p-values in tables. We do not really need them any more, but some readers expect to see them, so it is usually a good idea to report them.

## Slide 33

### Reporting the results of a comparison between means.

- Figure legend:

- Figure 1. Mean self-reported heights of men and women in the field course prep unit. Error bars indicate standard error.

- In the text:

- Men were 0.10 m taller than women in our study (t-test with Welch correction, t = 2.94, df = 21.61, p = 0.0077).

**Notes:**

So, how should we report our results? It is usually a good idea to report a result with a figure, and the most intuitive figure for comparing the means of two groups is bar chart. There is code in the handbook for how to create bar charts, so I will not walk you through it here. But, there are a few important things to notice. First, the axes are labelled. On the x-axis we have the names of the groups, and on the y-axis we have the value that is being reported, with its units. The text is large enough to read. Second, there are error bars. These help readers get an intuitive sense for how different the groups really are. Finally, there is a figure legend. So, if a reader goes through your paper and does nothing but look at the pictures, as many readers do, they will be able to figure out what your figures mean.

Finally, even if we report the results in a figure, we still have to report them in the text. The goal here is to be concise, but to give the reader all of the information they need to understand your result. Here, men were taller than women. By how much? 0.1 meters. How do we know? We did a t-test. How sure are we? The p-value was 0.0077. All of this information can be conveyed in a single short sentence.

## Slide 34

### The t-distribution approximates Monte Carlo outcomes.

- William Sealy Gosset

- (Student)

**Notes:**

Okay, there is one more idea I want to cover today.

The reason that t-tests work is that the t-distribution is similar to the distribution that we would get using the Monte Carlo method that we described earlier.

When I introduced the t-test, I said that the t-distribution is similar to Monte Carlo results under certain conditions, but I did not describe what those conditions are. One of them is that the data within each group should be roughly normally distributed. That means it should follow a bell curve.

## Slide 35

### Self-reported heights of students in the field course prep unit.

**Notes:**

For height data, that is usually true. These are histograms for the male and female heights in our data set, and they seem to be at least roughly bell-shaped. There is a peak in the middle, and the distributions taper off at the edges.

## Slide 36

### Arranging your data for analysis

**Notes:**

But, not all data follows a normal distribution. You may remember that the first column of our data set was the order in which people responded to a poll about their height. So, the person with a 1 in the response column responded first, the person with a 2 responded second, and so on.

## Slide 37

### Response order for students in the field course prep unit.

**Notes:**

Here, I have plotted histograms of the response order for men and for women. You can see immediately that these are not normally distributed. There is no bell curve here. But, there may be a pattern. It looks to me like maybe there are more women clustered at the beginning of the response order, and more men clustered at the end.

So, let’s imagine that we entered this study with the a priori hypothesis that women respond to polls faster than men. How could we test this? We cannot use a t-test, because the data within groups are not normally distributed. But, we can use a test called a Wilcoxon. The Wilcoxon test relies on the idea that any data, normally distributed or otherwise, can be put in rank order. Then, we can ask, is the mean rank of one group different from the mean rank of the other. The mechanics of the test are explained in the handbook. In lecture, I will focus on how to implement it.

## Slide 38

### Implementing a Wilcoxon test in R

- > mro=hd$resp[which(hd$sex=="m")]

- > fro=hd$resp[which(hd$sex=="f")]

- > wilcox.test(fro,mro,alternative="less")

- Wilcoxon rank sum test

- data:  fro and mro

- W = 145, p-value = 0.3027

- alternative hypothesis: true location shift is less than 0

**Notes:**

Implementing a Wilcoxon test is exactly analogous to implementing the t-test. I have created lists of the female and male response orders in the same way that I created lists of heights earlier in the lecture. I have called these fro and mro, for female response order and male response order. The command to conduct the test is wilcox.test.

However, there is an important difference between this test and our t-test. Here, our question is not, ”Do women and men respond at different times?” We hypothesized that women might respond to the survey faster than men. So, we want to know specifically, is women’s response order lower than men’s response order, because lower orders indicate earlier responses.

We entered the data for women into the Wilcoxon test before the data for men. So, the text 'alternative = “less"' tells R to do a one-tailed test asking if women had lower response orders than men.

In the output, we can see that the p-value is greater than 0.05. So we have no evidence that women responded to the poll faster than men.

## Slide 39

### Reporting the results of a comparison between response times.

- In the text:

- We found no evidence that women responded to the survey earlier than men (Wilcox rank sum test, p = 0.3027).

**Notes:**

Of course, we still need to report the result. For negative results, people often omit figures. But, in the text, we need to tell readers that there was no evidence for a difference, what test we used measure the evidence, and what p-value we found. Again, we want to do this as concisely as possible. I have done it in a single short sentence.

Notice that I have not said anything about means! Wilcoxons study mean ranks rather than means. There is more information on this in the handbook.

## Slide 40

### Which test should we use?

| We want to know about: | Is the normality assumption met? | Use: |
| --- | --- | --- |
| mean rank | yes or no | Wilcoxon |
| mean value | yes | t-test |
| either will do | no | Wilcoxon |
| mean value | no | Monte Carlo |

**Notes:**

So, which test should we use?

Well, if we are interested in the mean rank, the Wilcoxon is always the right test to use. It asks about mean rank, and we can use it for any kind of data.

If we are interested in the mean value and the data is normally distributed within groups, we can use the t-test, because its assumptions are met.

If the data is not normally distributed and either mean rank or mean value will do, we can use a Wilcoxon. This is sometimes the case if all we care about is whether the groups are different, but we do not really care how they are different.

But, if we really need the mean value, and the data is really not normally distributed, we may need to fall back on the Monte Carlo approach. And, in that case, you may have to code it yourself.

**************

Okay, so that is all I have to say for today. You will find the practical that goes with this lecture on Blackboard. If you have questions, please post them to the discussion board, or we can talk about them in the live practical session. Ganbare! Thanks again for tuning in, and I look forward to your questions!
