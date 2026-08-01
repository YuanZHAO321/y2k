---
title: "Practical 4(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 3/Practical 4(2).docx"
type: document
---

After completing practical 4, you will be able to:

- Conduct and report simple and multiple linear regressions

- Predict response variables from raw data using fitted models

- Analyse and report interactions among predictors

- Illustrate the results of linear regressions with figures

Practical 4

Many plants and animals are bilaterally symmetric. That is, they have two sides that are nearly mirror images of one another. However, in any given individual, there are often small differences between the two sides. Fluctuating asymmetry, or FA, is a measure of how different those two sides are. Researchers are interested in FA because it can be a signal of developmental stress. A plant or animal that is more symmetrical is likely to have experienced less stress during its development, and so may be healthier or more biologically fit.

In 2018, a Manchester student named Bailey Francis studied FA on a field course in the Italian Alps. You can read about his work in the journal Italian Botanist here. Francis was interested in whether low light conditions promote FA in plant leaves. He studied this in Adenostyles alliariae, an alpine plant in the daisy family. He collected leaves from 100 plants growing in shaded and unshaded locations. At the site where each leaf was collected, he measured the light intensity in log(lx) – lx is the abbreviation for lux, a measure of light intensity equal to one lumen per metre squared. He photographed each leaf and measured its total surface area (in mm2) using a software package called ImageJ. Then, he measured the distance from the midrib of the leaf the widest points on the left side and on the right side of the leaf. He computed FA using the formula

where R and L are the distances from the midrib to the widest point on the right side and left side of the leaf, respectively. This is a common measure of asymmetry that is independent of the size of the leaf. You can find Francis’s data set in the file “data from Francis and Gilman 2018.csv”.

If you read Francis’s paper, you will see that he analysed his data in a more sophisticated way than we will attempt here. As you continue in Science, you will find no matter what analysis you do, there is almost always a more sophisticated one available. As a researcher, your goal will often be to find an analysis that is good enough to answer your question, but doesn’t require you to spend your whole life on one data set! Today, we will see what we can do with Francis’s data using a simple set of tools that are well-known to almost all scientists. At the end, you might want to check to see if our simple approach produces the same results that Francis published.

Question 1

Let’s begin by importing the data from Francis and Gilman (2019). You have imported data many times now, so you may remember how to do it, or at least where to look it up. If you name the imported data fa.data, then you will be able to use code in the starter code without extensive editing. After you import the dataset, look at the data to make sure you understand what the rows and columns mean.

Q1.1: What is the name of the column that contains the light intensity data? The leaf area data? The fluctuating asymmetry data?

Francis’s main question, and the first question we will ask today, is “Does light intensity predict fluctuating asymmetry?” More specifically, we will ask if there is a linear relationship between these two variables. Before we start a formal analysis, it can be useful to plot the data to see if there is a pattern that is visible by eye. We can do that with the command:

plot( fa.data$light, fa.data$fa, xlab = "light intensity in log(lx)",

ylab = "fluctuating asymmetry" )

Here, the first two arguments of the plot() command are the x- and y-coordinates of the points to be plotted. So, we are telling R to plot light intensity on the x-axis and fluctuating asymmetry on the y-axis. The next two arguments are the familiar axis label arguments that we have seen used in other plots.

Q1.2: Can you see a pattern in this data? If so, what direction does it go? Do you think it is statistically significant? (That is, is the pattern strong enough that it would be unlikely to arise by chance alone?)

Don’t worry if you have to guess at Q1.2. You will develop an intuition for patterns like these as you work with more of them.

Now, let’s test your intuition with a formal analysis – specifically with a linear regression. We can ask whether there is a linear relationship between fluctuating asymmetry and light intensity using the code:

fa.lm = lm( fa ~ light, data = fa.data )

summary( fa.lm )

You will notice that the code above follows the same syntax we used for ANOVA. The only difference is that now the command is lm() instead of aov().

Using the plot() and lm()  commands together sometimes confuses new users. Look carefully at the syntax of these two commands. The plot() command uses the syntax plot(x,y,…), where x is the predictor and y is the response. This is because we want to put our predictor on the x-axis and our response on the y-axis, and (x,y) is the standard algebraic notation for a point in Cartesian space. In contrast, the lm() command uses the syntax lm(y~x,…). This is because the formula y~x describes how y depends on x. The important thing to notice is that the order of the predictor and response is reversed in the two commands. If you get the orders wrong, your results will be wrong.

When you run the summary() command, R will show you the results of your linear model. The most important part of the output is table below

Coefficients:

Estimate Std. Error t value Pr(>|t|)

(Intercept)  0.106949   0.017505   6.109 2.03e-08 ***

light       -0.003446   0.001777  -1.939   0.0554 .

In this table, the row labelled light tells us about the relationship between light and FA. The column labelled Pr(>|t|) reports the p-value associated with that relationship. It is not below 0.05, but it is close. We might call this “weak evidence” for a relationship. The column labelled Estimate tells us what the relationship is. Here, for every one unit increase in light intensity, there is a decrease of 0.0034 units in FA. To report this result, I might say “We found weak evidence that fluctuating asymmetry decreases with light intensity (-3.4 x 10-3 log(lx)-1, p = 0.0554).” Note that I have included the effect size and the units in the result. The units of the effect size will always be the units of the response per unit of the predictor. Here, the response is FA, which is a unitless measure, and the predictor is light intensity measured in log(lux). The superscript “-1” indicates that log(lux) is in the denominator of the units – that is, the change in FA is 0.0034 per log(lux).

So, how can we illustrate this result? Happily, this is the easiest figure you will ever make in R! You already made a scatter plot. If you closed it, you can make it again by rerunning the same command. Our linear model describes the line of best fit through that scatter plot. You can add that line to the data with the command

abline( fa.lm, col = "red" )

where fa.lm  is just the name of the linear model you created. As always, you will need a caption to explain your figure. I might write “Fluctuating asymmetry in the leaves of 100 Adenostyles alliariae plants plotted as a function of light intensity measured at the leaf location.”

Q1.3: Provide a figure to illustrate the relationship between light intensity and FA in the leaves of Adenostyles alliariae.

We can get more out of this result if we think about how the line of best fit in the figure we just produced relates to the model. The line of best fit is a prediction. That is, if we know the light intensity at the location of a leaf, we can use the line of best fit to predict the FA. We could do this graphically. For example, if we wanted to predict the FA for a leaf growing at 10 log(lux), we could draw a vertical line from 10 on the log(lux) axis of our figure to the line of best fit, draw a horizontal line from the line of best fit to the FA axis, and read the predicted FA from the FA axis (see figure 1 below). But, it would be easier and more accurate to compute the prediction. You may remember from algebra that we can describe a straight line in the form

y = m x + c

where m is the slope and c is the intercept. Our fitted model estimates and reports m and c: m is the effect size of the predictor and c is the estimate of the intercept. So, if we want to predict the FA (ie, the response) when the light intensity (ie, the predictor) equals 10, we can take the values of m and c from our model and use:

y = -0.003446 log(lux)-1 x 10 log(lux) + 0.106949 = ~0.072

Q1.4: What is the expected FA for a leaf of A. alliariae if the light intensity at the leaf location is 12 log(lux)?

Question 2

In many plants, the size of leaves also depends on the conditions under which the plant grows. The data set we used for question 1 includes data on leaf size. Use that data to answer the following questions.

Q2.1: Use linear regression to test the hypothesis that A. alliariae leaf size changes with light intensity at the leaf location. Report your results clearly and concisely.

Q2.2: Illustrate the results of Q2.1 with a figure.

Q2.3: What is the expected surface area of a leaf found growing at light intensity of 8 log(lux)? Of a leaf found growing at 12 log(lux)?

Question 3

In question 1, we found weak evidence that A. alliariae leaves are less symmetrical when they grow at lower light intensity. In Q2.1, you found strong evidence that leaves of A. alliariae are larger in locations with lower light intensity. Is it possible that differences in FA in A. alliariae leaves are not caused by low light but rather by rapid growth? That is, is it possible that when leaves grow faster and larger, they tend to be less symmetrical, and that this fully explains the relationship between light intensity and FA? If this were true, then we would expect that i) bigger leaves would have greater FA even if they were grown at the same light intensity, and ii) among leaves of the same size there would be no relationship between light intensity and FA. Or, put another way, i) there would be a relationship between leaf size and FA controlling for light intensity, but ii) no relationship between light intensity and FA controlling for leaf size.

We could control light intensity in well-designed experiments, but we probably cannot control leaf size. However, we can control for either predictor, or both, in linear models. The model below will find the relationship between FA and leaf size controlling for light intensity, and the relationship between FA and light intensity controlling for leaf size:

fa2.lm = lm( fa ~ light + leaf.area, data = fa.data )

We can use the summary() command to see the results, just as we did in questions 1 and 2.

Q3.1: Does the model above provide evidence that light intensity affects FA controlling for leaf size? Does it provide evidence that leaf size affects FA controlling for light intensity?

If I were reporting the result for leaf area, I might write “We found no evidence that leaf area affects FA when controlling for light intensity (p = 0.7908).”

Q3.2: Report the result of the analysis of light intensity controlling for leaf area.

Q3.3 (Challenge): Does your answer to Q3.2 undermine the result we illustrated in Q1.3? Why or why not?

Question 4

Let’s return to the anuran dataset collected by Juarez and colleagues (2023). You can find that data in “data_from_Juarez_et_al_2023.csv”.

In practicals 1 and 2, we used Jaurez and colleagues’ data to ask whether male and female anurans have different body sizes. But, size is not the only way that individuals of the same species can differ. They can also differ in their proportions – that is, in how some element of size relates to some other. In this practical, we will focus on how femur length relates to snout-vent length (svl). In particular, we will ask if the relationship between svl and femur length differs between males and females. Recall that snout-vent length is a measure of the total length of the animal, and the femur is a leg bone involved in movement. So, if femurs are relatively larger in one sex than in the other, this may suggest differences in how the animals move, and possibly differences in their ecology.

Let’s begin by studying the yellow toad, Incilius luetkenii. This is a common lowland toad in Mesoamerica. Unlike many anuran species, male yellow toads compete physically for mating opportunities, and selection for success in these contests might contribute to sexual dimorphism. Let’s create a data frame that includes only I. luetkenii. You may remember how to do this from practical 3, but there is starter code to help if you get stuck.

Before we attempt an analysis, let’s plot svl as a function of femur length in this species. Again, there is starter code to help if you need it. If you plot the figure correctly, you should see a clear relationship between femur length and svl: not surprisingly, toads with longer femurs tend to have greater svl.

Q4.1: Looking at the figure you produced, does it look like the relationship between femur length and snout vent length is different in males than in females? If so, how is it different?

Let’s formally test the hypothesis that the relationship between femur length and svl differs between the sexes in I. luetkenii. To begin, let’s convert the categorical variable “sex” into a numerical variable so we can use it as a predictor in our linear regression. We can do this by creating what we call an “indicator.” An indicator is a vector that contains only 0s and 1s, and that has value 1 when the condition it indicates is true and 0 when the condition it indicates is not true. Here, we will create an indicator to tell us whether each individual in the dataset inc.lue is male. We can do this with the code:

inc.lue$male = as.numeric( inc.lue$sex == "M" )

Here, the operator “==” tells R to return TRUE for each entry of inc.lue$sex that equals "M" and FALSE for each entry that does not equal "M". The command as.numeric() coverts these TRUEs and  FALSE s to 1s and 0s, respectively. By assigning these values to inc.lue$male instead of just male, we are telling R to add this new vector to the data frame inc.lue. Look at the data in inc.lue after you run this command to make sure it did what we expect.

Now, let’s build our model. In question 3, we built a model of the form

lm ( svl ~ femur + male, data = inc.lue)

This model would tell us two things:

- Does svl change with femur length controlling for (ie, within) sexes, and

- Does svl differ between the sexes controlling for femur length (that is, if a male and a female have the same femur length, would we expect one sex to have greater svl)?

But, neither of these is the question we want to answer. We want to know if the relationship between femur length and svl is different in the two sexes. That is, does the effect of femur length on svl depend on sex? When the effect of one predictor depends on the value of another, we call this an interaction. (Be careful with this word: interactions are among predictors. The relationship between a predictor and response variables is not an interaction!) We can add an interaction between femur length and sex to our model by adding a multiplicative term to the right hand side of the model formula:

inc.lue.lm = lm ( svl ~ femur + male + femur * male, data = inc.lue)

Q4.2: Look at the results of the model above. Do we have evidence for an interaction between sex and femur length on svl in I. luetkenii? How do you know?

Usually we would decide how to report our results before we try to illustrate them. It is easier to make good figures if we know what those figures should show! But, this is the first time we have encountered and interaction, and having a figure might help us develop an intuition for what our results mean. So, let’s use our fitted model to add lines of best fit to the scatter plot we created above. If you have closed the scatterplot, you can run your code again to recreate it.

We added lines of best fit to scatterplots in questions 1 and 2. In those examples, there was only one predictor and thus only one line of best fit. We plotted that line by putting the name of the model directly into the abline() command. In this analysis, the relationship between femur length and svl is different for males and females, so there are two lines of best fit – one for each sex. The abline() command cannot plot these lines directly from the fitted model, so we will have to tell abline() where to draw lines. The syntax abline( c, m ) plots the line y = m x + c. So, if we know c (the intercept) and m (the slope) for the lines we want to plot, we can plot them. The Estimate column in the coefficients table of our model output contains the information we need.

The coefficients table from our fitted model looks like this:

Coefficients:

Estimate Std. Error t value Pr(>|t|)

(Intercept)  -2.0943     9.8987  -0.212   0.8341

femur         2.8534     0.3154   9.046 1.64e-09 ***

male         37.9116    16.1065   2.354   0.0264 *

femur:male   -1.3317     0.5328  -2.500   0.0191 *

The estimate in the row labelled (Intercept) is the easiest to interpret. The intercept is the predicted value of the response (here, svl) when all the predictors in the model equal 0. In the column male, 0 indicates a female. So, the entry in the row labelled (Intercept) is the predicted svl of a female with a femur of length 0. Obviously this is nonsense – there are no toads with femurs of length 0 – and we will come back to this below. But, the entry still useful, because the predicted svl of a female with femur length 0 is the intercept of the line of best fit for females.

In a model without interactions, the estimate in the row labelled femur would tell us how svl changes with femur length controlling for any other predictors in the model. But, because there is an interaction between femur and male, how svl changes with femur length depends on the sex of the toad. So, the reported effect of femur cannot be for all sexes, but has to be for some specific sex. By convention, it will be for the sex of toad coded as 0 (here, females). So, the estimate in the row labelled femur is the slope of the line of best fit for females. Together with the value in the row labelled (Intercept), this gives us all the information we need to plot the line of best fit for females:

abline( -2.0943, 2.8534, col = "red" )

I plotted the line in red to match the points that represent females.

The estimate in the row labelled male follows the same logic. It is the effect of one unit of “maleness” on svl when femur length is 0. Males are coded as 1 and females are coded as zero in our data, so “one unit of maleness” is just the difference between males and females. So, when femur length is 0 (ie, at the intercept), the predicted svl of males is 37.9116 mm greater than the predicted svl of females. Thus, the intercept for the line of best fit for males is -2.0943 + 37.9116.

Finally, the row labelled femur:male reports how the effect (ie, slope) of femur changes for each unit of maleness. We know that in females, svl increases by 2.8534 mm for every 1 mm increase in femur length: this is the value in the row labelled femur. So, for males, the slope is 2.8534 + (-1.3317). This gives us all the information we need to plot the line of best fit for males:

abline( -2.0943 + 37.9116, 2.8534 + (-1.3317), col = "blue" )

Q4.3 (Challenge): Controlling for femur length, do males have greater or lesser svl than females? (Or, put another way, if a male and a female have the same femur length, which one should we expect to have the larger svl?)

Your answer to Q4.3 illustrates an important idea. If there is an interaction in a model, it can be very difficult to make general statements about the main effects of the predictors that are involved in that interaction. This is not a quirk of the model, it is an attribute of the system. If the interaction is real, then the main effect of each predictor in the interaction changes with the value of the other, and there may not be general patterns. Because interactions make it hard to interpret main effects, if we test for an interaction and do not find evidence for one, then we may need to study models without the interaction to make correct inferences about the predictors.

Now that we have seen a picture of our results, how should we report the result of our hypothesis test? Recall that our question was “is the relationship between femur length and svl different between males and females in I. luetkenii?” I might write, “The relationship between femur length and svl differed in male and female I. luetkenii (p = xxxx). In females, svl increased by xxxx mm for each 1 mm increase in femur length. In males, svl increased by xxxx mm for each 1 mm increase in femur length.”

Q4.4: Report the results of our analysis clearly and concisely. You can borrow from the text above, but replace the xxxxs with the correct values.

In questions 1 and 2, we used our fitted models to make predictions. We can do the same thing here. Let’s predict the svl for a male yellow toad with a femur of length 32 mm. Our fitted model tells us that:

E(svl) =  + femur +  male +  (femur) (male)

where the E(svl) is the expected (ie, predicted) svl,  is the intercept, and , , and  are the estimated effects of femur, male, and femur:male, respectively. So, for a male yellow toad (ie, male = 1) with femur length 32 mm,

E(svl) = -2.0943 + 2.8534 (femur) + 37.9116 (male) + (-1.3317) (femur) (male)

= -2.0943 + 2.8534 (32) + 37.9116 (1) + (-1.3317) (32) (1)

≈ 84.5

Q4.5: What is the predicted svl for a female yellow toad with femur length of 35 mm?

Q4.6 (Super-challenge): Our model tells us that the slope of svl on femur length in females (ie, 2.8534) is significantly different from zero. This is potentially useful (although in this case not very surprising!). The slope of svl on femur length in males is smaller than in females. Specifically, it is 2.8534 - 1.3317 = 1.5217. Using tools that we have already learned, can you think of a way to test whether this slope is significantly different from zero? Report your result clearly and concisely.

Question 5

Eleutherodactylus planirostris, the greenhouse frog, is a small frog that lives mostly in leaf litter on Caribbean islands including Cuba, the Caymans, and the Bahamas. Unlike most frogs, the greenhouse frog does not have a free-living tadpole stage. The tadpoles develop into small frogs while still in the egg case, so the eggs hatch directly into frogs. This is thought to be an adaptation to life in the leaf litter, where there is plenty of moisture but little standing water.

Q5.1: Test the hypothesis that the relationship between femur length and svl is different in male and female E. planirostris. Report your result clearly and concisely.

Q5.2: Provide a figure to illustrate your result.

Question 6

The figure you produced for Q5.2 should show one male greenhouse frog with an unusually long femur and a relatively small svl compared to other individuals with similar femur length. At a glance, it looks like the pattern you found in Q5.1 might be due mostly to this one individual. It is possible that this point is an error of some sort – perhaps one of the measurements was recorded incorrectly. We cannot exclude data points simply because they look strange to us. If we did that, our analyses would only ever show what we expect them to show, so we would never learn anything new from them. However, if there are data points that we do not completely trust for some reason, it can be good practice to analyse the dataset both with those data points included and with them excluded. If we get similar results both ways, then we can be more confident in the story. If we don’t, then we may want to report our results to readers with caution.

We can create a new version of our data set with the dubious data point removed. If the full data set is named ele.pla, then we could use the code:

ele.pla.1 = ele.pla[ -which( ele.pla$sex == "M" & ele.pla$femur > 10 ), ]

In this command, the -which(…) tells R to remove the data points that meet the criteria in the which() command. Those criteria are that the individual is male and has a femur length greater than 10 mm.

Q6.1: Using the data with the dubious male data point removed, test the hypothesis that the relationship between femur length and svl is different in male and female E. planirostris. Report your result clearly and concisely.

Q6.2: Test the hypothesis that males and females with the same femur length will have different expected svl. Report your result clearly and concisely.

Q6.3: Test the hypothesis that male and female E. planirostris have different mean femur lengths. Report your result clearly and concisely.

Q6.4: Provide figures to illustrate any significant results from Q6:1-3.

References

Francis, B., & Gilman, R. T. (2019). Light intensity affects leaf morphology in a wild population of Adenostyles alliariae (Asteraceae). Italian Botanist, 8, 35-45.

Juarez, B. H., Moen, D. S., & Adams, D. C. (2023). Ecology, sexual dimorphism, and jumping evolution in anurans. Journal of Evolutionary Biology, 36(5), 829-841. doi:10.1111/jeb.14171
