---
title: "Practical 2(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 1/Practical 2(2).docx"
type: document
---

After completing practical 2, you will be able to:

- Import data into R

- Subset data in vectors and data frames

- Inspect and check data for normality

- Choose between t-tests and Wilcoxon tests for comparing two groups

- Choose between one-sided and two-sided hypothesis tests

- Report results of t-tests and Wilcoxon tests clearly and concisely

- Illustrate the results of t-tests and Wilcoxon tests with figures

Practical 2

In many animal species, males and females differ in size, shape, and behaviour. This is called sexual dimorphism. Understanding how differences between the sexes evolved and how they affect the ecology of species and populations are important goals for ecologists and evolutionary biologists.

Jaurez and colleagues (2023) studied sexual dimorphism in anurans (ie, frogs and toads) in museum collections in the United States. We will study a subset of their data. In particular, we will study the data they collected for three species: Boophis madagascariensis, Pseudis paradoxa, and Dendrobates auratus. For each species, we will import a data set that reports the sex, mass (in g), snout-vent length (in mm), and femur length (in mm) for each of 30 animals. Snout-vent length is the distance from the tip of an animal’s snout to rear of its cloacal slit. Thus, it is a measure of the whole length of the animal except the tail. However, it is sensitive to the body position of the animal. Animals preserved in museums can be in different positions, so it can be difficult to measure snout-vent length consistently across specimens. The femur is a bone in the hind leg. It may not always reflect the size of the whole animal, but because it is a single bone it is not sensitive to the position of the animal, so is easy to measure accurately. In addition, the femur is involved in jumping performance, and so may tell us something about the ecology or the behaviour of the animal.

You will investigate data and conduct statistical analyses to answer the questions below. On the “answer sheet” document for this practical, you will find the questions reproduced without the supporting text. Please write your answers and insert any supporting figures you need on that document. The file “Starter code for Practical 2.R” has some code to help you get started. For question 1, the file has all of the code you will need. For question 2 you will need to add some code yourself, and after that you will do most of the coding on your own. Of course, you can (and should!) modify code from earlier questions to answer later ones. When you have completed the practical, I recommend saving your code. You will not be required to submit your code, but it will be useful to you in the future – including on the final assessment for this unit!

Question 1

B. madagascariensis is a tree frog native to Madagascar. Our first goal is to ask whether there is sexual dimorphism in this species.

Let’s begin by preparing the folder we will work in. Well-organised folders make data analysis easier! Save the data file “Boophis_madagascariensis.csv” and the R file “Starter code for Practical 2.R” to a folder on your computer where you can find them. I like to create a new folder for every project I do, so I can easily find my data and codes later. After saving your data, open RStudio. In the files tab in bottom right panel, navigate to the folder where you saved the code and data. In the dropdown menu under the “More” tab (indicated by a blue gear), select “Set as Working Directory.” This tells R that you will be working with files in this directory. Double-click “Starter code for Practical 2.R” in the files tab. This will open a scripting window with the starter code.

When you set the working directory, R will have printed a line of code starting with setwd(… in console (ie, the bottom left pane). I recommend copying and pasting this line of code at the top of the starter code. Then, the next time you want to work with this code, you can navigate to the code file outside of RStudio and double click on it to open it. This will open in RStudio and the starter code. You can select and run the line the line that starts with setwd(…  and R will set your working directory to this folder without your having to navigate to it in the files pane. This may seem unnecessary now, but in the future when you have R codes and data stored in many different folders you will be glad you did it!

Now, let’s import that data for B. madagascariensis. We can use the command:

boo.mad = read.csv( "Boophis_madagascariensis.csv" )

You can find this line of code in your scripting pane in the section “CODE FOR QUESTION 1.” You can type it into the R console, but it would be easier to just select it in the scripting pane and click on the “Run” tab at the top of the pane. This code will read the data from “Boophis_madagascariensis.csv” and store it in an object called boo.mad. There is nothing special about the name boo.mad – we could have given the data a different name, but I chose this so I can remember what the data is.

When you run the command above, R will create the data object, but it will not display that object. We might want to see the data so we can be sure it is what we think it is. The command:

head( boo.mad, 10 )

will show us the first 10 lines of the data. Each line represents one data point – in this case, one frog. Each column reports one piece of information about the data point. As a rule, this is almost always the best way to set up your data. Let’s check our understanding of the data.

Q1.1:  Is the first frog in the data set a male or a female?

Q1.2:  How long is the femur of the 7th frog in the data set?

Q1.3 (Challenge):  What is the snout-vent length of the 12th frog in the data set?

Note that, instead of using head(), we could ask R to display the full data set by just entering the name of the data (ie, boo.mad) into the console. But, for large data sets R cannot display all of the data, so this approach is not always useful.

To study sexual dimorphism, let’s ask whether the mean femur lengths of male and female B. madagascariensis are different. In the unit handbook, you learned that we can study this with a t-test, if the values are approximately normally distributed within each group. Femur lengths are continuous, and it seems reasonable that they would be approximately normally distributed within groups, but let’s check by looking at histograms. We can create a list of the femur lengths in males with the command:

male.femurs = boo.mad$femur[ which( boo.mad$sex == "M" ) ]

This line of code illustrates two very useful ideas. First, if we want to indicate or collect just one column of information from a data frame, we can use the symbol $. In this line, the text boo.mad$femur tells R that we want only the information in the column femur of the data frame boo.mad. Second, if we want only a subset of that data, we can use the command which(). Here, we are telling R that we want the values of femur from only the rows in which sex equals “M”. This is called subsetting, because it collects a subset of the data. Again, the name male.femurs is arbitrary – we could have called this whatever we want, but I chose a name that would be easy to remember. As usual, R creates the object we have asked for, but it does not show it to us. If we want to be sure we have done it right, we can enter male.femurs into the console and see if the values match the values in boo.mad. Then, we can make a histogram with the command:

hist( male.femurs, xlab = "male femur lengths in B. madagascariensis", main = "" )

This is not a perfect bell curve, but the data set is very small, and we may not be able to see a clear bell curve until the data set is large. But, it does look like there is a peak in the middle, and we do not have any a priori reason to think the values are not normally distributed, so it may not be unreasonable to treat them as if they are.

Q1.4: Make a histogram of the femur lengths of females in B. madagascariensis.

Note that whenever you produce a figure, you should always include a caption that explains what the figure is. The caption should be as concise as possible, but should include enough information for a reader to understand the figure even if they read nothing else in your text (because some lazy readers may try to do that!). For this figure, I might write something like “Figure 1. Femur lengths of 15 female B. madagascariensis sampled from museum collections in the United States.”

To me, the histograms for femur length in both males and females look approximately normal, and we have no theoretical reason to believe they are not. So, let’s charge ahead with a t-test. Recall that our question is, “Are the mean femur lengths of male and female B. madagascariensis different?” So, we will need to conduct a two-tailed t-test. (You can review one- and two-tailed tests in the unit handbook.) Here, we will implement our t-test with the code:

t.test( femur ~ sex, data = boo.mad )

This is a slightly different syntax than the one in the handbook, but it is easier to use. We will use the syntax from the handbook when we do question 2. In this command, the formula femur ~ sex tells R to ask how the data in femur depends on the data in sex. More generally, you can read the character “~” (called a tilde) as “depends on.” The parameter data = boo.mad tells R to look for the columns femur and sex in the data frame boo.mad.

Conducting analyses is of little value until we report the results to readers. If you have read the unit handbook, you will already know how to interpret the output of the t.test() function. But, what should we report? As a rule, we need to report everything readers need to understand our results, but in as clear and concise a format as possible. Here, I might write “The mean femur length in females was greater than that in males (35.1 mm vs xxx mm; Welch’s t-test, t  = 2.56, df = 18.1, p = xxx),” but with the “xxx”s replaced by the appropriate values from the model output. This statement is short, but there is a lot of information packed into it. Readers know which sex was larger and by how much, and our p-value estimates how confident we are that this difference is not due to chance. We have also reminded readers which test we have used to arrive at our p-value. (Welch’s t-test is just an adaptation of Student’s t-test that corrects for unequal variance in the groups being tested.) The t-statistic and the degrees of freedom may be superfluous, but some readers like to see them and some journals require them. Note that where I have reported values, I have not reported all of the decimal places that R provides. There is not an absolute rule about how many decimal places to report, but we really should not expect our estimates to be accurate to four or five decimal places (as R reports them), and those decimal places may be distracting rather than informative to readers.

Q1.5: Report the results of our t-test asking “Are the mean femur lengths of male and female B. madagascariensis different?”

It is often easier for readers to understand our results if we illustrate them with figures. On the surface, making figures in R will probably seem much harder than making similar figures in Excel or some other programmes that you already know. But, there is a trade-off. Once you get good at it, the figures you can make in R are much more flexible than those you can make in Excel. Excel can make simple bar charts like the ones we will make for this analysis, but as you progress in Science you will find that Excel cannot do some things you might want it to do, and R can. So, it is worth learning to make figures in R. But, we will not try to learn this from principles. After all, this is not a coding unit – for us, coding is just a tool. The starter code for this practical includes a block of code that will make a figure for this analysis. It is annotated, so you can modify it to make figures for other analyses later.

Q1.6: Provide a figure to illustrate the results of your analysis.

For this question, the starter code will provide the figure, but you will need to provide a clear and concise figure caption.

Question 2

In question 1, we found that female B. madagascariensis had longer femurs than males. In fact, females are larger than males in many anuran species. Larger females can lay more eggs, so they have higher reproductive rates and higher fitness. Even a small male can produce enough gametes to fertilise all of the eggs of even a very large female. Moreover, in most anurans, males do not fight over females. Instead, they advertise with their calls or their bright body colours. So, there is less reason for males to invest in becoming large, when they could invest in calling or bright colours instead.

Armed with the knowledge above, we might have approached the study of anuran dimorphism differently. Instead of asking whether males and females are different sizes, we might ask specifically whether females are larger. In this case, we would want a one-tailed test. Let’s conduct a one-tailed test to ask whether females of the species P. paradoxa (the South America “shrinking frog”) have longer femurs than males. You can find the data in the csv “Pseudis_paradoxa.csv” and import it as you did for the B. madagascariensis data. We will consider how to implement the test below, but before we do that, modify code from question 1 to answer the following questions about the data.

Q2.1: What is the femur length of the frog in row 2 of the P. paradoxa data set?

Q2.2: Is the most massive specimen in the data for this species a male or a female?

Q2.3 (Challenge): What is the mean mass of frogs in this data set?

Q2.4: Do the femur lengths of males and females appear to be roughly normally distributed within the sexes?

To ask whether femur length differed in male and female B. madagascariensis, we conducted a two-tailed test with the code:

t.test( femur ~ sex, data = boo.mad )

To conduct a one-tailed test, we can add alternative = "greater") to the command. Then, instead of asking whether the groups differ, we are asking whether the first group has a larger mean value than the second. Or, we could add alternative = "less" to the command to ask whether the first group has a smaller mean. But, which is the first group? You can see which group is first in the output from the test and then modify the command accordingly, but if you would rather not do that, you can control which group is first by using a slightly different syntax for the command. You may already have created lists of the male and female femur lengths to answer question Q2.4. If so, you can use the command

t.test(female.femurs, male.femurs, alternative = "greater")

to ask whether the first group (here females) have longer femurs than the second (here males). Of course, if you used different names when you created the lists of femur lengths above, you will need to use those names in this command. Note that in this command, I have not told R where to find the data. In the other syntax, sex and femur were columns in the data frame boo.mad, so we had to tell R to look for them in that data frame. Here, female.femurs and male.femurs are not parts of another data frame. They are separate objects in R's memory. So, R knows where to find them without being told. You can write the code for the command above yourself, but you can also find it in the starter code.

Q2.5: Report the result of your t-test clearly and concisely.

Q2.6: Provide a figure to illustrate your result.

Question 3

After doing Questions 1 and 2, you have all of the skills you need to any t-test you might want to do. For question 3, let’s ask whether female Dendrobates auratus (poison dart frogs) are more massive than males. You can find the data in “Dendrobates_auratus.csv.”

Q3.1: Should this be a one-tailed test or a two-tailed test?

Q3.2: Report the results of your analysis clearly and concisely.

Q3.3: Provide a figure to illustrate your results.

Question 4

The fruit fly Drosophila melanogaster is perhaps the most well-studied of all animals. Its physiology and genetics are especially well-studied, but an increasing amount of work is being done on its behaviour, including its social and mating behaviours. To study the behaviour of live animals, we often need to identify and track individuals. It is hard for researchers to distinguish individual Drosophila, so we often mark them to make that easier. To mark Drosophila, we often need to anaesthetise them. This is typically done either by exposing them to CO2 or chilling them on ice. There is some concern that anaesthetising Drosophila may affect their behaviour later, and if this is true then we may need to think carefully about how we design and interpret experiments.

In 2019, University of Manchester student Eirlys Tysall and her colleagues did a study to understand how different methods of anaesthetising Drosophila affect their mating behaviour. The researchers anaesthetised 3-day old male flies with either ice or CO2 for 10 minutes. They maintained a control group that they did not anaesthetise. Three days after the treatments, they placed each male fly in a 15-ml universal tube with an unmated 6-day old female. They recorded the time until mating occurred – this measure is called “latency to mate.”. The researchers stopped each trial if no mating had occurred after 2 hours. It might be tempting to ignore trials in which flies did not mate, but this would be the wrong thing to do because it would discard information. In these trials we know that males took at least 2 hours to mate. So, the researchers recorded the latency to mate as 2 hours. This underestimates extreme values, but it means we have not discarded information.

Q4.1: Before you look at Tysall and colleague’s data, do you expect the latency to mate to be normally distributed within groups? Why or why not.

You can find Tysall and colleagues’s data in the file “Tysall_et_al_2019.csv.” Using the commands you have already learned, import the data and plot the histograms of latency to mate for flies treated with ice and CO2 and for the control flies. Was your guess about normality correct?

In this case, we have both theoretical and empirical reasons to believe that latency to mate is not normally distributed within groups. If we want to know if latency to mate differs among the groups, we cannot study that with t-tests. Instead, we will use Wilcoxon tests. Note that Wilcoxon tests compare groups, but they ask a different question than t-tests. Instead of comparing means, Wilcoxon tests compare rank orders. You have already read about this in the unit handbook.

Let’s begin by asking if latency to mate differs between flies anaesthetised with ice or CO2. Earlier in this practical, we used subsetting to create lists of femur lengths for only males or only females. Here, we will subset our entire data frame. We can create a data frame that includes only anaesthetised but not control flies with the command:

an.flies = flies[ which( flies$treatment %in% c( "Ice", "CO2" ) ) , ]

Here, flies is the name I gave to the full data set when I imported it. You will need to change this if you gave the data a different name. The which command operates just like the ones we have used before – it tells R to choose only those rows in which treatment is either Ice or CO2. This time, we are not choosing from a column like boo.mad$femur

but rather from the whole data frame flies. The part after the second comma and before the final square bracket tells R which columns of the data to choose. If that is left empty, as it is here, R will choose all of the columns. To test whether you have done this correctly, we can count the rows in an.flies using the command:

nrow( an.flies )

There should be 231 of them. If you are struggling to get this, there is code to help in the starter code for this practical.

Q4.2: What were the latencies to mate for the first and third flies in an.flies?

Now, we can conduct a Wilcoxon test using a command with the same syntax as t.test():

wilcox.test( latency ~ treatment, data = an.flies )

Q4.3: Report the results of your Wilcoxon test clearly and concisely. (Note that there are no degrees of freedom or t-statistic to report, and people rarely report the W-statistic. So, these can be omitted from your answer!)

How can we illustrate the result of a Wilcoxon test? This can depend on a lot of things, including what we are trying to communicate to readers and what the distributions look like. But, one way to do it is to plot histograms that readers can compare. There is code to do this in starter code for this practical, but you will need to fill in some missing bits and add a figure caption!

Q4.4: Provide a figure to illustrate your results.

References

Juarez, B. H., Moen, D. S., & Adams, D. C. (2023). Ecology, sexual dimorphism, and jumping evolution in anurans. Journal of Evolutionary Biology, 36(5), 829-841. doi:10.1111/jeb.14171

Tysall, E. E., Pembury Smith, M. Q. R., & Gilman, R. T. (2020). The effects of marking methodology on mate choice in Drosophila melanogaster. Animal Behaviour and Cognition, 7(4), 492-504. doi:10.26451/abc.07.04.02.2020
