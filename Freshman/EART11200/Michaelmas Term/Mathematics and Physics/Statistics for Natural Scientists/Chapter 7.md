---
title: "Chapter 7"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Chapter 7.pdf"
type: pdf
---

# **Chapter 7. Dealing with non-independent data points**

Up to this point, the analyses that we have considered in this handbook have shared a common assumption: they have all assumed that the observations we are studying are _independent_ . Independence means that knowing the value of any one observation does not tell us anything about the values of the other observations. This is important because, when this is true, each observation is a completely new piece of information. If observations are not independent, then a new observation might be telling us something we could already infer from the others. That is, information can be redundant. When that happens, we have less information to work with, and so less power to detect patterns, than we might think if we just counted our data points. However, while many statistical tests assume that the observations in a data set are independent, except in very well controlled lab experiments this is seldom completely true. In this chapter, we will learn a powerful approach for dealing with nonindependence among observations: _mixed effects modelling_ .

## **Why do we need mixed effects models: a motivating example**

It is easiest to think about non-independence if we have a motivating example. Imagine that we are interested in the mass of seed pods produced by a particular species of grassland plant. Seed pod mass is interesting because it may be a surrogate for how much energy the plant invests in reproduction. We conduct a study to assess whether the seed pod mass of plants in our focal species depends on the altitude at which the plant is growing. Conveniently, our plant grows on ski slopes – we can think of ski slopes as a type of anthropogenic grassland with an altitudinal gradient. We go out on a particular day in July and we collect all of the seed pods from a set of plants sampled from three different ski slopes. Then, we compute the total mass of the seed pods we found on each plant. I have saved the (simulated!) data in a csv called “seed_pods_from_slopes.csv” in the Dropbox folder with this handbook. In the data set, the column alt tells us the altitude in metres at which the plant was growing, slope tells us which ski slope the plant was collected from (they are labelled A, B, and C), and seed.mass tells us the total mass in grams of the seed pods we found on each plant.

Let’s approach our data with a simple linear regression, as we have done many times before. We will import the data and call it spm.s for s eed p od m ass from s lopes. Then, we will plot the seed pod mass as a function of the altitude at which the plant was growing.

> spm.s=read.csv("seed_pods_from_slopes.csv") (7.1) plot(spm.s$alt,spm.s$seed.mass,xlab="altitude (m)", ylab="seed pod mass (g)",ylim=c(9,18.5))

**Figure 7.1. Seed pod mass as a function of altitude in a hypothetical species of grassland plant.** The regression line is the line of best fit from code 7.2.

The result is figure 7.1. Based on this scatter plot, it looks like there might be a relationship between altitude and seed pod mass in this species. But, let’s test this formally. Again, we can do this using code we already know well.

spm.lm=lm(seed.mass~alt,data=spm.s) summary(spm.lm)

Call: lm(formula = seed.mass ~ alt)

Residuals: Min      1Q  Median      3Q     Max -3.8044 -0.7381  0.0711  0.7362  4.0298 Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept) 16.3054075  0.7100756  22.963  < 2e-16 *** alt         -0.0023405  0.0005377  -4.352 5.54e-05 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Residual standard error: 1.58 on 58 degrees of freedom Multiple R-squared:  0.2462, Adjusted R-squared:  0.2332 F-statistic: 18.94 on 1 and 58 DF,  p-value: 5.537e-05

This analysis suggests that there is a significant relationship between altitude and total seed pod mass in this species. For each additional meter of altitude, the total mass of seed pods on the plant decreases by 0.002 g. The p-value is less than 0.0001, so the evidence appears to be strong.

Now, let’s plot our data again, this time with the data points colour-coded to show which ski slope each plant was collected from:

(7.3)

plot(spm.s$alt,spm.s$seed.mass,xlab="altitude (m)", ylab="seed pod mass (g)",ylim=c(9,18.5), col=as.factor(spm.s$slope)) legend(1580,18.65,legend=c("slope A","slope B", "slope C"),pch=c(1,1,1),col=c(1,2,3),y.intersp=1)

In the plot command in code 7.3, the

argument col=as.factor(spm.s$slope) tells R to assign different colours to the data points from each ski slope. The command legend() adds the legend box in the top right of the figure. The first two arguments of legend() tell R where on the coordinate system to place the top left corner of the legend box, pch tells R what markers to use in the legend, col tells R what colours to use for those markers, and y.intersp tells R how far apart to space the lines. The result is figure 7.2. Here we can see that the three ski slopes cover different altitude ranges, and the plants growing on each slope have different seed pod masses. But, on any given slope, there is no clear relationship between altitude and seed pod mass.

**Figure 7.2. Seed pod mass as a function of altitude in a hypothetical species of grassland plant.** Colours show which plants were found growing on each of the three ski slopes.

This presents us with a problem. The ski slopes in our study differ in altitude, but they may also differ in many other ways. They may differ in aspect, or latitude, or annual rainfall. We could measure these differences if we wanted to. The ski slopes might also differ in countless ways we cannot measure, for example historical pesticide use, or in ways that we could measure but might never think to measure. If these factors affect the mass of seed pods on the plants that we are studying, then the seed pod masses on each slope may be more similar to other seed pod masses from the same slope than they are to the seed pod masses from other slopes. If this is true, then the data points in our study will not be independent. If we measure the mass of seed pods on one plant on one slope, then the answer will tell us something about the masses of seed pods on other plants on that slope, because we know they will be similar.

To see why this is a problem, we can do a thought experiment. Imagine that our null hypothesis is true – that is, imagine that there is no relationship between altitude and the total mass of seed pods on a plant. Nonetheless, the mass of seed pods per plant differs on the three ski slopes in our study for reasons we cannot explain. _What is the probability that we would see a relationship between altitude and seed pod mass at least as strong as the one in the observed data by chance alone?_ The answer to this question is the correct p-value for the hypothesis that seed pod mass varies with altitude. We can find this p-value easily. If there were no relationship between altitude and seed pod mass, then we could study the mean seed pod mass and the mean altitude for the plants on each ski slope. After all, if there is no relationship between seed pod mass and altitude on each slope, then we would not lose any information by averaging within slopes. If we do this, then we will have only three data points to think about. Each data point is the mean altitude and mean seed pod mass on one ski slope. In our observed

data, the lowest altitude was associated with the greatest seed pod mass ( _ie_ , on slope A), and the highest altitude was associated with the smallest seed pod mass ( _ie_ , on slope C). Thinking back to the Monte Carlo approach from chapter 2, if there is no relationship between altitude and seed pod mass in the population, then there is no reason we should expect this particular set of associations in a random sample. Any other set of associations would be just as likely. So, we can create a null distribution by permuting the observed seed pod masses among the three ski slopes. There are six possible permutations: ranking the ski slopes from lowest to highest by mean seed pod mass, we might see ABC, ACB, BAC, BCA, CAB, or CBA. Recall that ski slope B has the intermediate altitude. So, any permutation where ski slope B is in the middle will have a relationship just as strong as the one in the observed data. When the order is ABC the relationship will be the same as in the observed data, and when it is CBA the relationship will be opposite to the one in the observed data, but the magnitude of the relationship will be the same. So, in two out of six possible permutations, we will see a relationship as strong as the one in the observed data, and the correct p-value for our hypothesis is 0.33. Our simple linear regression model suggested a p-value of <0.0001. So, we thought we had strong evidence for a relationship between altitude and seed pod mass, but if we had computed it correctly, we should have found no evidence for a relationship at all!

So, how can we deal with this problem? Well, we have already learned one approach that we might try. In chapter 6, we learned an approach called ANCOVA. ANCOVA is simply a linear regression with a categorical predictor included in the model. In this case, we can regress seed pod mass on both altitude and the categorical predictor ski slope. This ANCOVA asks whether there is a relationship between seed pod mass and altitude _when controlling for_ the effect of ski slope. We can do this using code we have already seen:

> spm.lm.2=lm(seed.mass~alt+slope,data=spm.s) (7.4) summary(spm.lm.2) Call: lm(formula = seed.mass ~ alt + slope) Residuals: Min      1Q  Median      3Q     Max -1.8907 -0.6044  0.1338  0.6180  2.2424 Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept) 14.8904916  0.4494392  33.131  < 2e-16 *** alt          0.0004512  0.0004075   1.107    0.273 slopeB      -2.2927437  0.3053828  -7.508 5.01e-10 *** slopeC      -4.0567471  0.3777918 -10.738 3.25e-15 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Residual standard error: 0.912 on 56 degrees of freedom Multiple R-squared:  0.7575, Adjusted R-squared:  0.7445 F-statistic: 58.32 on 3 and 56 DF,  p-value: < 2.2e-16 In these results, ski slope A is the baseline. It is the one that does not appear in the output, and it is the one against which the other slopes are compared. The intercept tells us that the expected seed mass for plants on ski slope A is 14.89 g. On slope B, the expected seed mass is 2.29 g less than on slope A ( _ie_ , 12.60 g), and on slope C the

expected seed mass is 4.06 g less than on slope A ( _ie_ , 10.83 g). The p-values for each of these differences are less than 0.0001, so we are confident that the seed pod masses differ by ski slope. But, we have no evidence that seed pod mass varies with altitude on individual slopes (p = 0.273). This matches our intuition from looking at figure 7.2!

But, there is a problem with using ANCOVA to study this kind of data. To see this, consider a slightly different data set. Imagine that instead of studying plants on ski slopes, we had studied plants in forest clearings. Any given clearing might cover only a small altitudinal range. Furthermore, each clearing is small, and contains only a few plants of the study species. Figure 7.3 illustrates a data set we might collect from such a study. The data points from different clearings are shown in different colours.

Just like our ski slopes, our clearings may differ in many ways, and these differences might affect the seed

<!-- Start of picture text -->
Figure 7.3. Seed pod mass as a function of altitude in a<br><!-- End of picture text -->

**Figure 7.3. Seed pod mass as a function of altitude in a hypothetical species of grassland plant.** Colours show which plants were found growing on each of 15 forest clearings. Data are simulated.

pod mass of the plants that grow there. Indeed, that seems to be the case in our data: plants from the same clearing have similar seed pod masses. Nonetheless, it looks like there is a trend across clearings. Clearings at higher altitudes have lower seed pod masses. Within clearings, the trend is less clear. This is not surprising. There is little difference in altitudes within clearings, so the effects of altitude within clearings would be difficult to detect. Let’s conduct an ANCOVA on this data. The data is saved in a file called “seed_pods_from_clearings.csv” in the Dropbox folder with this handbook.

spm.c=read.csv("seed_pods_from_clearings.csv") spm.lm.3=lm(seed.mass~alt+clearing,data=spm.c) summary(spm.lm.3)

(omitting some output to save space)

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)  8.2898321  3.6430391   2.276 0.027798 * alt         -0.0004472  0.0018076  -0.247 0.805738 clearingB    5.6132111  0.2583584  21.726  < 2e-16 *** clearingC    7.9561769  2.2516398   3.534 0.000978 *** clearingD    3.6482711  0.2749602  13.268  < 2e-16 *** clearingE    3.6556416  0.3078719  11.874 2.59e-15 *** clearingF    5.2155200  0.3029063  17.218  < 2e-16 *** clearingG    3.9503980  0.5654596   6.986 1.20e-08 ***

… In this ANCOVA, we see strong evidence for differences in seed pod mass among clearings. But, we see no evidence for a change in seed pod mass with altitude, even though it looks like there should be one in figure 7.3. We do not see this pattern in our analysis because, when we control for the differences _among_ clearings, there is very

little difference _within_ clearings to detect. Our ANCOVA is blind to the trend among clearings!

If ANCOVA will not answer our question, then we might ask if we could instead study the average altitudes and seed pod masses for the clearings, and ignore the variability within clearings. That is, could we just compute the average altitude and average seed pod mass for each of our 15 clearings, and the treat each clearing as a single data point? We could, but this approach comes with its own problems. First, if there are trends within clearings, then those trends contain information. If we average the data for each clearing, then we lose that information. Second, even if there were no trends within clearings, each clearing has a different number of plants, so the averages will be based on different numbers of observations. The averages we observe are just estimates of the true values for each clearing, and estimates based on more data points are more accurate than estimates based on fewer observations. So, some clearings should have a greater influence on our regression than others. If we work with just the averages for each clearing, then this weighting of clearings will be lost. So, none of the approaches we have learned so far is appropriate for this kind of data.

## **Introducing mixed effects models**

The solution to this problem is an approach called mixed effects modelling. To understand how mixed effects models work, it helps to start by formalising the simple linear regression model.

Consider a simple linear regression with one predictor and one response. To make this more tangible, we can consider the same system we have been studying. So, our predictor will be altitude, which we will represent with the symbol _a_ , and the response will be seed pod mass, which we will represent with the symbol _s_ . Our linear model is

_si_ =  0 +  _a ai_ +  _i_

This equation says that the seed pod mass in observation _i_ (that is, _si_ ) is equal to some intercept (  0), plus some coefficient (  _a_ ) times the altitude of observation _i_ ( _ai_ ), plus some unexplained error that will be different for each observation (  _i_ ). The coefficient  _a_ is the effect of altitude and therefore the slope of the regression line. To “fit” this model, we solve for the values of  0 and  _a_ that minimise the sum of the  2𝑖 over all of the observations in the data set. This is the process for finding the line of best fit that we encountered in chapter 4.

But, there is another way we could fit this model to our data. Let’s assume that the values of  _i_ are drawn from a normal distribution with a mean of 0 and some standard deviation that we will call  . This just means that unexplained variability in the response variable is normally distributed, which is a standard assumption of linear regression. If we draw numbers at random from a normal distribution, most of the values will be close to 0, and we are less likely to see numbers that are farther away from 0. Drawing a result of  is about 60% as likely as drawing a result of 0; drawing a result of 2  is about 13.5% as likely as drawing a result of 0; and drawing a result of 3  is about 1% as likely as drawing a result of 0. If we chose values for  0 and  _a_ , then

we have determined a line to describe our data. By determining a line, we have also determined all of the  _i_ s, because the  _i_ s are just the distances from the line to each data point. If the  _i_ s are drawn from a normal distribution with a standard deviation of  , then we can compute the likelihood of seeing exactly our observed data set given the parameter values that we chose. We can look for the combination of parameter values (that is, the values of  0,  _a_ , and  ) that maximises the likelihood of the observed data. This is called maximum likelihood fitting. It turns out that maximum likelihood fitting 2 will give us exactly the same parameter values as minimising the sum of the  𝑖 s.

Now, let’s consider the more complicated model in our ANCOVA. We can write that model as

Here, _si_ ,  0,  _a_ , _ai_ , and  _i_ keep the same meanings as in the previous equation. _Bi_ is an indicator that is 1 when data point _i_ comes from clearing _B_ and is 0 otherwise, _Ci_ is an indicator that is 1 when data point _i_ comes from clearing _C_ and is 0 otherwise, and so on. Then,  _B_ is the effect of clearing B relative to the baseline clearing A,  _C_ is effect of clearing C relative to the baseline clearing A, and so on. In the second to last term, the subscript in  _O_ is the letter O, because there are 15 clearings and O is the 15<sup>th</sup> letter of the alphabet. The “…” is called an ellipsis, and it indicates that some terms have been omitted, but these terms follow the same form as the terms before and after the ellipsis. This model is more complicated than the simple linear regression, but we can fit it using least squares in exactly the same way. That is, we can look for the values of  0,  _a_ ,  _B_ ,  _C_ , _…,_  _N_ , and  _O_ that minimise sum of the  2𝑖 s. Or, we can fit it using the maximum likelihood approach. That is, we can look for the values of  0,  _a_ ,  _B_ ,  _C_ , _…,_  _O_ , and  that maximise the likelihood of the observed data. Again, these two approaches will give us exactly the same fitted values.

But, if we use the maximum likelihood approach, we can fit a slightly different model. Consider the model

where the values  _A_ ,  _B_ , …,  _N_ , and  _O_ are drawn from a normal distribution with a standard deviation  _clearing_ . Here, the  _A_ ,  _B_ , and so on tell us how each clearing deviates from the prediction for that clearing based on its altitude (that is, from  0 +  _a ai_ ). But, we do not have to find those values to fit the model. Instead, we can fit the model by finding the values of  0,  _a_ ,  , and  _clearing_ that maximise the likelihood of the observed data. Here, the parameters  0 and  _a_ are called fixed effects, because we will estimate fixed values for them. The parameters  _A_ ,  _B_ and so on are called random effects. We will not estimate values for these, but rather assume that they are drawn randomly from a distribution. The combination of fixed and random effects in the same model is why we call this a _mixed effects model_ . In practice, to fit the model, we have to integrate across all the values that  _A_ ,  _B_ , and so on might take, and the maths can get a little ugly. But, we do not have to worry about that, because we have computers to do the maths for us!

If you have followed this explanation this far, you may have noticed that there is a disadvantage to this model fitting. Since we will not find the values of  _A_ ,  _B_ , and so on, this fitted model will not tell us the effect of each clearing individually. But, in practice, we may not care. After all, these are just 15 clearings out of potentially thousands we might have observed. As far as we know, there is nothing special about them. So, knowing how each clearing individually differs from each other clearing might not be very useful. And, in return for this small disadvantage, the model offers us a big reward. Because we have not assigned effects to clearings, we have not assumed that the variability in the data is due to clearings rather than altitude. So, in practice, if a large fixed effect of altitude would be more likely than a large random effect of clearings to produce the observed data, then that is what our model will find!

## **Fitting mixed effects models in R**

Mixed effects models are conceptually more difficult than simple linear regression, but implementing them is no more difficult than implementing the multiple regression models that we learned in chapter 4. The tools that implement mixed effects models are not part of base R, so we will to install two new packages. The first package, lme4 , fits mixed effects models. The second package, lmerTest , computes the p-values associated with the fixed predictors. We can install these packages using the install.packages command described in Appendix 2, and load them using the library() command we have encountered in previous chapters.

install.packages("lme4","lmerTest") library(lme4) library(lmerTest)

After we have installed and loaded the packages we will use, let’s fit a mixed effects model to the simulated seed mass data illustrated in figure 7.3. Recall that the data is stored in a data frame called spm.c , the response variable is seed pod mass ( seed.mass ), the predictor of interest is altitude ( alt ), and the factor we want to control for is clearing ( clearing ). To fit the model, we will use the command lmer() :

sm.lmer=lmer(seed.mass~alt+(1|clearing),data=spm.c)

Much of the syntax in code 7.7 is already familiar to you. As in simple linear regression, the term to the left of the tilde is the response variable, and the terms to the right are the predictors. The fixed predictors, here just alt , enter the model exactly as they did for linear regression. The argument data=spm.c tells R to look for the names of the response and predictor variables in the data frame spm.c , and sm.lmer is the name of the model we will create. The only new piece of syntax is (1|clearing) . This term tells R to add a random effect of clearing to the model. The 1 to right of the vertical line tells R that the random effect we are adding is a _random intercept_ . In practice, this simply means that the plants in each clearing have different expected seed pod masses independent of their altitudes. As usual, we can use the command summary() to see the fitted model:

(7.8)

summary(sm.lmer)

Linear mixed model fit by REML. t-tests use Satterthwaite's method ['lmerModLmerTest'] Formula: seed.mass ~ alt + (1 | clearing)

REML criterion at convergence: 85.5

Scaled residuals: Min       1Q   Median       3Q      Max -1.91273 -0.48110 -0.05222  0.47533  2.04563 Random effects: Groups   Name        Variance Std.Dev. clearing (Intercept) 5.7021   2.3879 Residual             0.0454   0.2131 Number of obs: 60, groups:  clearing, 15

Fixed effects: Estimate Std. Error         df t value Pr(>|t|) (Intercept) 16.8169527  1.5138151 20.2094830  11.109 4.65e-10 *** alt         -0.0027887  0.0009319 22.4121911  -2.992  0.00662 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Correlation of Fixed Effects: (Intr) alt -0.913

We already know how to interpret the fixed effects table in this output. In the row labelled alt , the Estimate is the effect size of altitude on seed pod mass. Our data set reports seed pod mass in grams and altitude in metres. So, for every additional metre of altitude, we expect the total seed pod mass per plant to decrease by 0.0028 grams. The p-value associated with this effect is 0.00662. So, we would be unlikely to see an effect this large by chance alone, and we have strong evidence that the relationship between altitude and seed pod mass we see in our data is really an attribute of the population, and not just a pattern that arose by chance in our random sampling. As always, the intercept is the expected value of the response when all of the predictors are zero. Here, it would be the expected seed pod mass at sea level. But, what is the lowest altitude in our observed data set? We can check this using the command min() , which finds the minimum value in a set of numbers.

min(seed.mass$alt)

[1] 513

The lowest altitude in our observed data is 513 metres. This means that 0 is outside the range of altitudes we observed. We cannot be confident that the pattern we have identified will hold outside of the range of values we observed, so we should be cautious about predicting the seed pod mass of plants at sea level!

Often we are not very interested in the random effects in our models. Clearings might differ in ways that affect seed pod mass. Our mixed effects model controls for that difference, but we may not really care which clearings differ from which others or how. After all, these are just a small subset of the clearings we might have observed, and anything we learn about specific clearings in this study might tell us very little about any other clearings. Nonetheless, it is sometimes useful to know _how much_ of the

variability in our data is due to the random effects. In this example, we could ask how much of the variability that is not explained by the fixed effects ( _ie_ , altitude) is explained by differences among the clearings, and how much is explained by differences within clearings. We can get this information from the random effects table in the model summary. In the row labelled clearing , the value in the Variance column (5.7021 g<sup>2</sup> ) is the part of the variability in the data that is due to differences among clearings. That is, it is 2 𝜎𝑐𝑙𝑒𝑎𝑟𝑖𝑛𝑔. It has units g<sup>2</sup> (grams squared) because the response variable, and thus deviations from the expected response, are measured in grams, and because variability is computed by squaring deviations. The value in the Variance column of the row labelled Residual (0.0454 g<sup>2</sup> ) is the unexplained variability. So, the total variability that is not explained by the fixed effects is 5.7021 g<sup>2</sup> + 0.0454 g<sup>2</sup> , and the proportion of variability explained by clearings is 5.7021 g<sup>2</sup> /(5.7021 g<sup>2</sup> + 0.0454 g<sup>2</sup> ), or 99.2%. So, the differences among clearings are much greater than the differences within them! This matches our intuition from looking at figure 7.3.

## **More complex random effects structures**

In chapters 4 and 6, we saw that linear and logistic regression models can have more than one fixed predictor. For example, in chapter 4 we used linear regression to ask how the hourly wage in Ontario, Canada in 1994 depended on workers’ age, their years of formal education, their self-reported sex, and their native language. In chapter 6, we used logistic regression to ask how the probability that people in Chile voted for Augusto Pinochet depended on their age, education, income, gender, and the size of the city or town they lived in. Just as regression models can have multiple fixed effects, they can also have multiple random effects.

To illustrate this idea, let’s continue with the example of seed pod mass. Figure 7.3 shows the masses of seed pods collected from plants in different clearings. But, these plants might differ in other ways as well. For example, perhaps the plants have different genotypes, and perhaps we can identify those genotypes based on the plants’ phenotypes, or on some simple genetic assay. Perhaps plants with different genotypes have different expected seed pod masses. We might not care what those differences are – after all, the genotypes in our study are just some of a potentially large number of genotypes in the whole population, and knowing the expected seed pod mass for a small set of genotypes might not be useful. Nonetheless, we might wish to control for differences due to genotype when we investigate the effect of altitude.

The data frame spm.c includes a column called genotype , and the entries in this column report the genotypes for the plants in the data set. To include a random effect of genotype in our model, we can simply add +(1|genotype) to the model formula:

(7.10)

sm.lmer.2=lmer(seed.mass~alt+(1|clearing)+(1|genotype),data=spm.c) summary(sm.lmer.2)

Linear mixed model fit by REML. t-tests use Satterthwaite's method ['lmerModLmerTest'] Formula: seed.mass ~ alt + (1 | clearing) + (1 | genotype)

REML criterion at convergence: 85.3

Scaled residuals: Min      1Q  Median      3Q     Max -1.9407 -0.4002 -0.0533  0.5025  2.1397 Random effects: Groups   Name        Variance Std.Dev. clearing (Intercept) 5.667277 2.38060 genotype (Intercept) 0.002484 0.04984 Residual             0.043382 0.20828 Number of obs: 60, groups:  clearing, 15; genotype, 6

Fixed effects: Estimate Std. Error         df t value Pr(>|t|) (Intercept) 16.8821755  1.5047628 20.4688014  11.219 3.37e-10 *** alt         -0.0028304  0.0009256 22.7055448  -3.058  0.00563 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Correlation of Fixed Effects: (Intr) alt -0.912

In the output, the row of the random effects table labelled genotype shows us that genotype explains only a tiny proportion of the variability in seed pod mass. And, since the random factor that we have added to the model has very little effect, it is perhaps not surprising that the effect size and p-value associated with altitude are almost the same as in the model without a random effect of genotype.

We can take this idea a step further by including a random effect of the interaction between clearing and genotype in the model. That is, it might be true that genotype affects the seed pod mass, but the effect of each genotype differs among clearings. Perhaps some genotypes produce larger seed pods in some clearings, and other genotypes produce larger seed pods in other clearings. To add a random effect of the interaction to the model, we can add a term +(1|clearing:genotype) to the model formula. The colon in this term indicates an interaction.

(7.11)

sm.lmer.3=lmer(seed.mass~alt+(1|clearing)+(1|genotype) +(1|clearing:genotype),data=spm.c) boundary (singular) fit: see ?isSingular summary(sm.lmer.3)

Linear mixed model fit by REML. t-tests use Satterthwaite's method ['lmerModLmerTest'] Formula: seed.mass ~ alt + (1 | clearing) + (1 | genotype) + (1 | clearing:genotype)

REML criterion at convergence: 85.3

Scaled residuals: Min      1Q  Median      3Q     Max -1.9407 -0.4002 -0.0533  0.5025  2.1397 Random effects: Groups            Name        Variance Std.Dev. clearing:genotype (Intercept) 0.000000 0.00000 clearing          (Intercept) 5.667293 2.38061 genotype          (Intercept) 0.002484 0.04984 Residual                      0.043382 0.20828 Number of obs: 60, groups:  clearing:genotype, 47; clearing, 15; genotype, 6

Fixed effects: Estimate Std. Error         df t value Pr(>|t|) (Intercept) 16.8821724  1.5047643 20.4687466  11.219 3.37e-10 *** alt         -0.0028304  0.0009256 22.7054954  -3.058  0.00563 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Correlation of Fixed Effects: (Intr) alt -0.912 optimizer (nloptwrap) convergence code: 0 (OK) boundary (singular) fit: see ?isSingular

The row labelled clearing:genotype in output 7.11 shows us that the interaction between clearing and genotype explains absolutely none of the variability seed pod mass. So, the variability in this model has exactly the same sources as in code 7.10, and fixed effects are absolutely unchanged.

When we executed code 7.11, we got the following warning message:

boundary (singular) fit: see ?isSingular

Singularity in model fittings can be important! I will come back to this in the section on common warnings below.

## **Random slopes**

The random effects that we have studied up to this point have been random intercepts. Our models have allowed for the possibility that seed pod mass might differ by clearing or by genotype, or even among combinations of genotypes and clearings. However, they have assumed that the effect of altitude is the same within each clearing and for each genotype. In real systems, this might not be true. For example, perhaps altitude affects each genotype differently. Maybe some genotypes are adapted to high altitudes. For these genotypes, the slope of seed pod mass on altitude might be less negative than for other genotypes. If the adaptation is sufficiently strong, the slope of

seed mass on altitude might even be positive for some genotypes. If we were directly interested in the characteristics of the individual genotypes, then we could study this by testing for an interaction between altitude and genotype as fixed effects in the model. If we are not interested in the characteristics of individual genotypes, then we can control possible differences in the effect of altitude among genotypes by adding a “random slope” to the model. That is, we assume that the effect of altitude for each genotype is drawn from a normal distribution with a mean of  _a_ and a standard deviation  _a_ . Then,  _a_ is the expected effect of altitude for any unspecified genotype we might study, and  _a_ measures the variability in the effect of altitude among genotypes.

To add a random slope to our model, we simply add the name of the predictor to the appropriate random effect term. So, to add a random slope of altitude for each genotype to the model in 7.10, we would use

sm.lmer.4=lmer(seed.mass~alt+(1|clearing)+(1+alt|genotype),data=spm.c) boundary (singular) fit: see ?isSingular summary(sm.lmer.4) Linear mixed model fit by REML. t-tests use Satterthwaite's method [ lmerModLmerTest] Formula: seed.mass ~ alt + (1 | clearing) + (1 + alt | genotype)

REML criterion at convergence: 125.5 Scaled residuals: Min       1Q   Median       3Q      Max -1.08006 -0.29056  0.01174  0.27627  1.11789 Random effects: Groups   Name        Variance  Std.Dev.  Corr clearing (Intercept) 1.551e+00 1.246e+00 genotype (Intercept) 3.483e-08 1.866e-04 alt         3.372e-11 5.807e-06 -1.00 Residual             1.602e-01 4.003e-01 Number of obs: 60, groups:  clearing, 15; genotype, 6 Fixed effects: Estimate Std. Error         df t value Pr(>|t|) (Intercept) 17.9067713  0.8975993 52.4583985  19.950   <2e-16 *** alt         -0.0035167  0.0005648 52.7838121  -6.226    8e-08 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Correlation of Fixed Effects: (Intr) alt -0.931 optimizer (nloptwrap) convergence code: 0 (OK) boundary (singular) fit: see ?isSingular

Notice that once again, we have gotten a warning message telling us that our model fitting may be singular. This time, let’s stop and think about what that means.

## **Two common warnings**

In the section introducing mixed effects models, we learned that mixed effects models are fit using maximum likelihood. The set of parameter values that maximises

the likelihood of the observed data (that is, the combination of fixed effects we represented with  s and the random effects we represented with  s) cannot be calculated exactly. Instead, R has to search for these values out of all of the possible values the parameters might take. There are several different algorithms that can search for these values, but if our models are complex, then these algorithms can struggle. The linear regression models in chapter 4 could be fitted in fractions of seconds, but fitting a complex mixed effects model can take your computer several minutes. And, sometimes the fitting fails altogether.

One way a model fitting can fail is if the fitting is _singular_ . When this happens, R will return the following warning:

boundary (singular) fit: see ?isSingular

A singular fitting means that there is not enough data to estimate some of the variances in the random effects table. This is most likely when one of the variances is very close to zero. If the random effects are estimated incorrectly, then the fixed effects may also be estimated incorrectly. So, singular fits can be a problem.

Sometimes we can correct singularity by rescaling the predictors in the model. This is because the algorithms that fit mixed effects models work best when the magnitudes of the predictors are neither too large nor too small. In our example, altitude is measured in metres, and values in our data set range from 513 to 2100. But, we could just as easily measure altitude in kilometres – this is perhaps a less common way to think about altitude, but there is nothing wrong with it. If we do this, then the values in our data set would range from 0.513 to 2.1, and we _might_ be able to fit our models without encountering singularities. However, sometimes rescaling our predictors does not solve the problem with singularity. In those case, we may have to simplify our model by removing random effects until we get a model that we can fit accurately.

A second class of warnings we might get includes the words:

Model failed to converge…

When we see these words in a warning message, we know that R is not confident that it has found the set of parameters that maximise the likelihood of the observed data, and the model fitting should not be trusted. Sometimes we can solve this problem by rescaling our predictors. Sometimes we can solve it by trying a different fitting algorithm, or by letting our fitting algorithm run for a longer time. Tuning our fitting algorithms is beyond the scope of this handbook, but you can read about it in the documentation for the lmerControl() function by entering ?lmerControl into the R console. If none of these approaches work, we may have to settle for fitting a simpler model.

## **Fitting random effects models – a second attempt**

Let’s revisit the model with random slope that we fit in code 7.12. In our first attempt, the model fit was singular. Let’s try rescaling altitude so the range of the predictor is on the scale of ones rather than thousands. That is, we will measure altitude

in kilometres instead of metres. We can create a new predictor that measures altitude in kilometres using

alt.in.km=spm.c$alt/1000

So, alt.in.km includes all of the entries of spm.c$alt , but each one is divided by 1000. Then, we can refit the model:

> sm.lmer.5=lmer(seed.mass~alt.in.km+(1|clearing)+(1+alt.in.km|genotype), (7.14) data=spm.c) summary(sm.lmer.5) Linear mixed model fit by REML. t-tests use Satterthwaite's method [ lmerModLmerTest] Formula: seed.mass ~ alt.in.km + (1 | clearing) + (1 + alt.in.km | genotype)

REML criterion at convergence: 71.4

Scaled residuals: Min       1Q   Median       3Q      Max -1.93660 -0.40254 -0.05127  0.50190  2.14034 Random effects: Groups   Name        Variance  Std.Dev. Corr clearing (Intercept) 5.666e+00 2.380397 genotype (Intercept) 1.965e-03 0.044329 alt.in.km   1.742e-05 0.004173 1.00 Residual             4.336e-02 0.208224 Number of obs: 60, groups:  clearing, 15; genotype, 6 Fixed effects: Estimate Std. Error      df t value Pr(>|t|) (Intercept)  16.8804     1.5045 20.4639  11.220 3.38e-10 *** alt1000      -2.8290     0.9254 22.7028  -3.057  0.00564 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Correlation of Fixed Effects: (Intr) alt1000 -0.912

This time, our model fitting is not singular and we do not get a warning. So, we can interpret this model. The effect of altitude is significant – the expected seed pod mass per plant decreases by 2.83 grams per kilometre of altitude. If we want to convert this back to grams per metre for our readers, we can simply divide by 1000. In the random effects table, we can now see that there is a row labelled alt.in.km for the group genotype . This tells us how much the effect of altitude varies among genotypes. The standard deviation in the effect of altitude among genotypes is 0.004173 g km<sup>-1</sup> . This is very small compared to the expected effect of altitude among all genotypes (ie, -2.83 g km<sup>-1</sup> ), so we might expect the random slope to have very little effect on the model fitting. Indeed, it does. In code 7.10 we fit the same model without a random slope and found the effect of altitude was -0.00283 g m<sup>-1</sup> with a p-value of 0.00563. In this model, we find the effect of altitude was -0.00283 g m<sup>-1</sup> with a p-value of 0.00564. But, if we had interpreted the model with a singular fit, we would have inferred an effect of altitude of -0.00352 g m<sup>-1</sup> with a p-value <10<sup>-7</sup> . That would have been a poor estimate for the real pattern in the data!

Sadly, if we refit the model in code 7.11 with the rescaled predictor, the new fitting is still singular. (You can try this yourself to see that it is true.) So, it looks like we simply do not have enough data to fit a model with a random interaction between genotype and clearing.

## **Choosing the random effects structure**

The choice of which random effects we should include in a mixed effects model should be based on our scientific understanding of the system that we are modelling. If we believe that a categorical predictor is likely to affect our response variable, then we should include a random effect of that predictor in the model. If we believe that the effect of one or more of our fixed predictors is likely to depend on the category to which the observation belongs, then we should include a random slope for that fixed predictor with the appropriate categorical predictor.

Often, we will not be sure whether a categorical predictor will affect or response, or whether it will affect the slopes of the fixed predictors. In such cases, it is best to include the appropriate random effects. If we include a random effect when the category does not truly affect the predictor, our model will assign a small value to that random effect. There will little or no effect on the estimates for the fixed effects in the model, and we can still rely on our results. However, if we fail to include a random effect when we need one, our model will not accurately account for non-independence of the observations, and our inferences may be very wrong!

There is however an important caveat to this rule - we must be able to fit our models or we cannot interpret them, and models with very large numbers of random effects can be difficult for R to fit. If we cannot fit a model with all of the random effects we want to include, we may have to settle for a simpler model. Or, better yet, we may have to collect more data!
