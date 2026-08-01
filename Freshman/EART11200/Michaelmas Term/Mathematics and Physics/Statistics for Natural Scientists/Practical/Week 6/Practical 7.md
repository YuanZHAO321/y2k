---
title: "Practical 7"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 6/Practical 7.docx"
type: document
---

After completing practical 7, you will be able to:

- Fit and interpret linear mixed effects models.

- Report results clearly and concisely.

- Find the proportion of variability in the response variable that can be attributed to differences among groups.

- Test for significant differences among groups in mixed effects models.

Practical 7

A microbiome is the full community of microbes (eg, bacteria, fungi, viruses) that inhabits a particular environment. There are microbiomes in soil, in water, and even in and on plants and animals. There is growing evidence that host-associated microbiomes – for example microbiomes on the skin, in the gut, and in the lungs of animals – are critical to the health of their hosts. In many cases, diverse microbiomes – that is, those with many different microbial species – appear to be healthier for their hosts than more depauperate microbiomes.

In 2022, Calum Bridson and colleagues published a study on gut microbiomes in honeybees in Northeast England. The goal of the research was to understand the factors that control gut microbial diversity in these populations. This is important because rich gut microbiota may help maintain colony health. Bridson and colleagues (2022) collected 3 to 5 individual bees from each of 62 colonies, they sequenced the gut microbiomes of each bee, and they used the sequence data to reconstruct the gut microbiome compositions. Then, they computed the Shannon diversity of each microbiome. Shannon diversity is a common measure of community diversity that captures both the richness and the evenness of the species present. The researchers also measured several attributes of the individual bees or of the colonies. For individual bees, they measured the heterozygosity. Heterozygosity is a measure of the genetic diversity of individuals. In many species individuals with greater heterozygosity are more fit. For colonies, the researchers measured four attributes: i) the colony mean heterozygosity, ii) the proportion of shared alleles, iii) the landcover diversity, and iv) the proportion of urban landcover within 5 kilometres of the colony. Colony heterozygosity is the mean heterozygosity of the individual bees sampled from the colony. So, it is a measure of genetic diversity within individuals. Higher mean heterozygosity means that individuals have more different alleles. The proportion of shared alleles is a measure of genetic diversity among individuals. That is, it tells us how genetically different bees are from one another. A higher proportion of shared alleles means bees in the colony are more genetically similar, so the colony is less diverse. Landcover diversity is a measure of how many different vegetation or land use types exist within 5 kilometres of the colony. The proportion of urban land cover is a measure of how much of the surrounding area has been converted into buildings, roads, and pavement. These measures are all proportions or logs of proportions, so they are unitless.

You can find the data from Bridson and colleagues’ study in the file "data_from_Bridson_et_al_2022.csv". Our goal in this practical is to assess how the Shannon diversity of the gut microbiomes of individual bees (Shannon.index) depends on the heterozygosity of the individuals (het.ind), the mean heterozygosity of the colonies (het), the proportion of alleles shared among colony members (sa), the landcover diversity (l.div.5), and the proportion of urban land cover (urb) surrounding each colony. The column in the data set labelled ID is a unique identifier for each colony. We will use this later in the practical.

The first part of the practical uses methods we have already learned. You should be able to complete it without starter code, but you may want to consult code you have written or used in previous weeks.

Question 1

Q1.1: Conduct separate five linear regressions to assess whether the Shannon diversity of the gut microbiomes of individual bees depends on i) the individual heterozygosity, ii) the colony mean heterozygosity, iii) the proportion of alleles shared among colony members, iv) the landcover diversity surrounding the colony, and v) the proportion of urban landcover surrounding the colony. Report the results clearly and concisely. If any of the measures you study are significant predictors of Shannon diversity, then provide a figure to support that result. (You can omit figures for non-significant predictors.)

Q1.2: In Q1.1, you should have found that one of the measures you studied is a significant predictor of Shannon diversity in the bee gut microbiome. If this predictor explains some of the variability in the observed Shannon diversities, then we might hope that controlling for this predictor could reveal effects of the other predictors. With this in mind, study each of the other four predictors controlling for the effect of the predictor that was significant in Q1.1. Report your results clearly and concisely. (You can omit supporting figures.)

Question 2

The analysis we studied in question 1 is naïve because it ignores an important attribute of the system. The researchers sampled 286 individual bees, but those bees came from just 62 colonies. Bees live together closely and share microbe-rich food sources within their colonies, so bees from the same colony may have similar gut microbiomes. This means that the observations of bees from the same colony (ie, the individual data points in the study) may not be independent.

To understand why this is a problem, let’s consider some extreme examples. Think back to our studies of frogs in previous weeks. Imagine we are studying a new species of frog, and we want to know whether the females are bigger than the males. We measure one female and find she has a mass of 56 g, and we measure one male and find he has a mass of 48 g. We would not draw strong conclusions from this. We have only measured one animal of each sex, and the difference we observed could easily be by chance. But, now, imagine that we measured 100 females and they were all 56 g, and we measured 100 males and they were all 48 g. Now, we would be very sure that females are bigger than males! So, bigger datasets allow us to draw stronger conclusions even when the effect sizes are the same. This is probably intuitive to you, but it illustrates an important idea. If we have a data set, it would be wrong to simply duplicate it and analyse the duplicated data - if we duplicate the data enough times we will certainly get false positives. If we want to increase the size of our data set, we need to collect new, independent samples.

Now, let’s return the considering Bridson and colleagues’ bees. Imagine an extreme case where microbiomes differ among colonies, but within each colony the microbiome of every bee is exactly the same. We could sample one bee from each colony and analyse their microbiome as we did in question 1. If we sampled five bees from each colony and analysed the data as we did in question 1, we would infer more significant patterns in the data. But, our inference would be wrong, because we would not have added any new information. If every bee within a colony is the same, then sampling each colony more than once is really just a way of duplicating our dataset!

In Bridson and colleagues’ data, the bees within colonies are not identical, so the problem is not as extreme as in our thought experiment. But, if bees’ microbiomes are more similar to those of their colonymates than to those of bees from other colonies, then we will experience some part of the problem. If we treat the bees as independent, we will overestimate the amount of information we have, underestimate the p-values, and overestimate our confidence in the patterns we want to study.

The solution to this problem is mixed effects modelling. A regular linear regression assumes that there is an expected value for each sample, and that the observed value of each sample differs from the expectation due to some unexplained variability that describes only that sample. In contrast, mixed effects models divide the unexplained variability in the response variable between individuals and groups. The model assumes that there is an expected value for each sample, and that the members of each group differ from their expectation due to some unexplained variability that describes the group. Then, each individual sample differs from the prediction for its group by a different unexplained variability that belongs only to that sample. If the variability among groups is large and the variability among individuals within groups is small (as when our imaginary bees within colonies were all identical), then the model treats each group almost as if it were a single data point. If the variability among groups is small and the variability among individuals within groups is large (that is, when there is almost no effect of groups), then the model treats each individual as almost independent.

While the concepts behind mixed effects models can be challenging, fitting them easy. However, it requires an extension of R that we call a “package.” A package is simply a block of code written by an R user that enables new tools or functions. To fit and interpret mixed effects models, we will need two packages: lme4 (Bates et al. 2015) and lmerTest (Kunznetsova et al. 2017). You can download these using the code:

install.packages("lme4")

install.packages("lmerTest")

When you run this code, the packages will be downloaded and installed on your computer. You will not need to install them again. However, before you use them, you will need to load them. You can do this with the code:

library(lme4)

library(lmerTest)

After you load the packages, they will remain loaded until you close R. If you close R and reopen it and then want to use the packages again, you will need to reload them using the library() command.

The syntax for fitting linear mixed effects models using the lme4 package is almost identical to the syntax for fitting linear regressions with lm(). Let’s fit a model of Shannon diversity in the gut microbiome as a function of individual heterozygosity, while accounting for a potential effect of each colony. We call this effect of colony a random effect. (This is because, in practice, the model will not attempt to estimate the effect to each colony. Instead, it will instead assume that the effect of each colony is drawn from a normal distribution with a mean of zero and with some variance, and it will estimate that variance. So, the effect of each colony is a random number sampled from a distribution.) To fit the model, we can use the code:

shan.div.lme = lmer( Shannon.index ~ het.ind + (1|ID), data = bees )

This code assumes that you named Bridson and colleagues’ data bees when you imported it. The command lmer() fits a linear mixed effects model. ID is a unique identifier for the colonies in the data set. The term (1|ID) tells R to assign a random effect to each colony (that is, to treat the colonies as a groups). You can view the fitted model with the summary() command, and interpret the output just as we interpreted the output of lm().

Q2.1: Based on the model we just created, do we have reason to believe that the Shannon diversity of the bee gut microbiome changes with the heterozygosity of the individual bee?

Often, we are not very interested in the random effects in our mixed effects models. That is, we may not care how any one colony differs from any other. After all, these are just 62 of possibly many thousand bee colonies in Northeast England, and knowing how any one colony differs from any other would tell us very little about the whole system. However, we might be interested in knowing whether there are differences among colonies at all. There are two ways we can approach this. First, notice the random effects table in the output from your summary() command. It should look like this:

Random effects:

Groups   Name        Variance Std.Dev.

ID       (Intercept) 0.05272  0.2296

Residual             0.13807  0.3716

Number of obs: 286, groups:  ID, 62

The column Variance tells us how unexplained variability is divided between the groups and the individuals in the model. In this case, our grouping factor was ID, so the row labelled ID tells us how much variability was assigned to the groups (here, the colonies). The row labelled Residual tells us how much variability was assigned to the individuals within groups. We can use the reported variances to compute the proportion of the variability in the data that is explained by the groups. Here, the variability explained by the groups is 0.05272. The total variability is the variability explained by the groups plus the variability explained by the individuals (ie. 0.05272 + 0.13807 = 0.19079). So, the proportion of the variability explained by the groups is

0.05272 / ( 0.05272 + 0.13807 ) ~ 0.28

We can also test whether the variance explained by the groups is greater than we would expect due to chance alone – that is, whether we have significant evidence that there are true differences among the groups. To do this, we can fit a model without a random effect, and we can compare the models with and without random effects using a likelihood ratio test. You already know how to fit the linear regression without a random effect – in fact, you did it earlier in this practical. I will refit it here using the code:

shan.div.lm = lm( Shannon.index ~ het.ind, data = bees )

Then, we can conduct a likelihood ratio test using the code:

anova( shan.div.lme, shan.div.lm )

Confusingly, the command here is anova(), but the test being conducted is a likelihood ratio test. Note that I have put the mixed effects model before the linear regression in the anova() command. If you switch the order, you will get an error, and you will be very frustrated. (I was!) The output of your likelihood ratio test will look like this:

refitting model(s) with ML (instead of REML)

Data: bees

Models:

shan.div.lm: Shannon.index ~ het.ind

shan.div.lme: Shannon.index ~ het.ind + (1 | ID)

npar    AIC    BIC  logLik deviance  Chisq Df Pr(>Chisq)

shan.div.lm     3 339.79 350.75 -166.89   333.79

shan.div.lme    4 314.06 328.69 -153.03   306.06 27.722  1  1.401e-07 ***

---

Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

The most important piece of information in the output is the p-value, here 1.401 x 10-7. It is very small, which means the groups would be unlikely to differ this much by chance alone. Taking all the results together, I might report this analysis like this: “Differences among colonies explained 28% of the variability in Shannon diversity in bee gut microbiomes in our data (p < 0.0001). We found no evidence for an effect of individual heterozygosity on Shannon diversity (p = 0.371).”

Q2.2: Fit separate mixed effects models to assess whether the Shannon diversity of bee gut microbiomes depends on colony mean heterozygosity, the proportion of shared alleles, the proportion of urban landcover, and the landcover diversity surrounding the bee’s colony. Report your results clearly and concisely.

Q2.3 (Challenge): We have fit 5 different mixed effects models in Q2. If you compute the proportion of variability explained by the colony, it will be slightly different in each model. Which one would you report to readers? Why?

Q2.4: The proportion of shared alleles was a significant predictor of gut microbiome diversity in our naïve linear regressions in Q1 and in our mixed effects models in question two. Create a scatter plot with the proportion of shared alleles on the x-axis and the Shannon diversity of bee gut microbiomes on the y-axis. Plot the line of best fit for the linear regression in red, and (Challenge) plot the line of best fit for the mixed effects model in blue. Paste your plot below. The p-values for the two models are different by an order of magnitude. Do the lines of best fit surprise you? Why or why not?

We can study multiple predictors and interactions in mixed effects models just as we did in linear regressions. In our linear regressions in Q1, we found a marginally significant effect of the proportion of urban land cover on bee gut microbiome diversity when we controlled for the proportion of shared alleles in the colony.

Q2.5: Use mixed effects models to ask whether there is i) an effect of the proportion of urban land cover on bee gut microbiome diversity when we control for the proportion of shared alleles in the colony, and ii) an interaction between the proportion of urban land cover and the proportion of shared alleles in the colony on bee gut microbiome diversity. Report your results clearly and concisely.

References

Bates, D., M. Maechler, B. Bolker, and S. Walker. 2015. Fitting linear mixed-effects models using lme4. Journal of Statistical Software 67:1-48.

Bridson, C., L. Vellaniparambil, R. E. Antwis, W. E. Müller, R. T. Gilman, and J. K. Rowntree. 2022. Genetic diversity of honeybee colonies predicts gut bacterial diversity of individual colony members. Environmental Microbiology 24:5643-5653.

Kunznetsova, A., P. B. Brockhoff, and R. H. B. Christensen. 2017. lmerTest package: tests in linear mixed effects models. Journal of Statistical Software 82:1-26.
