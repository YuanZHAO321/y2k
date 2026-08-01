---
title: "Practical 7 answer key"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 6/Practical 7 answer key.docx"
type: document
---

Question 1

Q1.1: Conduct separate five linear regressions to assess whether the Shannon diversity of the gut microbiomes of individual bees depends on i) the individual heterozygosity, ii) the colony mean heterozygosity, iii) the proportion of alleles shared among colony members, iv) the landcover diversity surrounding the colony, and v) the proportion of urban landcover surrounding the colony. Report the results clearly and concisely. If any of the measures you study are significant predictors of Shannon diversity, then provide a figure to support that result. (You can omit figures for non-significant predictors.)

The Shannon diversity of bee gut microbiomes decreased as the proportion of shared alleles in the colony increased ( = -0.78, p = 0.0056). We found no evidence for relationships between gut microbiome diversity and individual heterozygosity (p = 0.299), colony mean heterozygosity (p = 0.268), urban land cover (p = 0.169), or landcover diversity (p = 0.793).

Notes: These results can be obtained from simple linear regressions like those we studied in practical 4. For example, to study the relationship between shared alleles in the colony and Shannon diversity of individual bee gut microbiomes in Figure 1.1, we could use:

bees = read.csv( "data_from_Bridson_et_al_2022.csv" )

shan.div.lm = lm( Shannon.index ~ sa, data = bees )

summary( shan.div.lm )

To illustrate the result, we could use:

plot( bees$sa,bees$Shannon.index, xlab = "proportion of shared alleles in the colony", ylab = "Shannod diversity of the gut microbome" )

abline( shan.div.lm,col="red" )

Q1.2: In Q1.1, you should have found that one of the measures you studied is a significant predictor of Shannon diversity in the bee gut microbiome. If this predictor explains some of the variability in the observed Shannon diversities, then we might hope that controlling for this predictor could reveal effects of the other predictors. With this in mind, study each of the other four predictors controlling for the effect of the predictor that was significant in Q1.1. Report your results clearly and concisely. (You can omit supporting figures.)

When controlling for the proportion of shared alleles in the colony, we found a marginally significant negative relationship between bee gut microbiome diversity and the proportion of urban landcover within 5 km of the colony ( = -0.38, p = 0.0775). We found no relationship between bee gut microbiome diversity and individual heterozygosity (p = 0.3443), colony mean heterozygosity (p = 0.3523), or landcover diversity (p = 0.5194).

Notes: These results can be obtained by extending the analyses in Q1.2 to include shared alleles and each of the other predictors. For example, to study the relationship between urban land cover and the Shannon diversity of bee gut microbiomes controlling or shared alleles, we could use:

shan.div.lm = lm( Shannon.index ~ sa + urb, data = bees )

summary( shan.div.lm )

Question 2

Q2.1: Based on the model we just created, do we have reason to believe that the Shannon diversity of the bee gut microbiome changes with the heterozygosity of the individual bee?

No.

Note: We can answer this using the starter code for the practical:

shan.div.lme = lmer( Shannon.index ~ het.ind + (1|ID), data = bees )

summary( shan.div.lme )

The p-value associated with het.ind is 0.371, so we have no evidence that the Shannon index of the bee gut microbiome is related to individual heterozygosity.

Q2.2: Fit separate mixed effects models to assess whether the Shannon diversity of bee gut microbiomes depends on colony mean heterozygosity, the proportion of shared alleles, the proportion of urban landcover, and the landcover diversity surrounding the bee’s colony. Report your results clearly and concisely.

The Shannon diversity of bee gut microbiomes decreased as the proportion of shared alleles in the colony increased ( = -0.81, p = 0.0449). We found no evidence for relationships between gut microbiome diversity and individual heterozygosity (p = 0.371), colony mean heterozygosity (p = 0.367), urban land cover (p = 0.422), or landcover diversity (p = 0.999).

Note: We can answer Q2.2 by modifying the code we used for Q2.1 to study different predictors.

Q2.3 (Challenge): We have fit 5 different mixed effects models in Q2. If you compute the proportion of variability explained by the colony, it will be slightly different in each model. Which one would you report to readers? Why? Is there evidence for differences in the Shannon diversity of gut microbiomes among the colonies? Report your results clearly and concisely.

Our results suggest that the proportion of shared alleles in colonies explains some of the variability in the gut microbiome diversity, but we found no evidence for effects of any other predictor. Therefore, I would report the variability explained by colonies in the model of Shannon diversity as a function of proportion of shared alleles.

Differences among the colonies explained 26.3% of the variability in bee gut microbiome diversity (p < 0.0001).

Note: To understand whether there are differences in the Shannon diversity of gut microbiomes among the colonies, we can conduct a likelihood ratio test of the models that include or do not include random effects of colony.

shan.div.lme = lmer( Shannon.index ~ het.ind + (1|ID), data = bees )

shan.div.lm = lm( Shannon.index ~ het.ind, data = bees )

anova( shan.div.lme, shan.div.lm )

A p-value less than 0.05 indicates that the model with the random effects is a significantly better fit, and thus that the amount of variability in Shannon diversity explained by colony in the data is more than we would expect to see by chance alone. The proportion of the variance explained by colony is equal to the variance explained by colony divided by the total variance (the variance explained by colonies plus the variance not explained by colonies):

0.04924 / ( 0.04924 + 0.13767 )

Q2.4: The proportion of shared alleles was a significant predictor of gut microbiome diversity in our naïve linear regressions in Q1 and in our mixed effects models in question two. Create a scatter plot with the proportion of shared alleles on the x-axis and the Shannon diversity of bee gut microbiomes on the y-axis. Plot the line of best fit for the linear regression in red, and (Challenge) plot the line of best fit for the mixed effects model in blue. Paste your plot below. The p-values for the two models are different by an order of magnitude. Do the lines of best fit surprise you? Why or why not?

The lines of best fit for the linear regression and mixed effects models are remarkably similar. To me, this is not very surprising. The samples from each colony are close to the same size, so all bees have approximately the same weight in the mixed effects model, just as they do in the linear regression. So, I would expect the lines to be similar. The most important difference between the models is that the mixed effects model does not overestimate the strength of evidence in the data.

Note: We can plot the simple linear regression by reusing the code from Q1.1. The abline() function cannot use the output from a mixed effects model directly, so we need to add the line manually. We can use the abline() command, with the syntax abline( intercept, slope ):

abline( 2.1111, -0.113, col="blue" )

Q2.5: Use mixed effects models to ask whether there is i) an effect of the proportion of urban land cover on bee gut microbiome diversity when we control for the proportion of shared alleles in the colony, and ii) an interaction between the proportion of urban land cover and the proportion of shared alleles in the colony on bee gut microbiome diversity. Report your results clearly and concisely.

Controlling for the effect of shared alleles, I found no evidence for a relationship between gut microbiome diversity and the proportion of urban land cover surrounding the colony (p = 0.2671), and no evidence for an interaction between the proportion of urban land cover and the proportion of shared alleles in the colony on gut microbiome diversity (p = 0.929).

Note: To ask whether there is a relationship between bee gut microbiome diversity and urban land cover when controlling for the proportion of shared alleles in the colony, we can use:

shan.div.lme = lmer( Shannon.index ~ sa + urb + (1|ID), data = bees )

summary( shan.div.lme )

To ask whether there is bee gut microbiome diversity depends on the interactions between urban land cover and the proportion of shared alleles in the colony, we can use:

shan.div.lme = lmer( Shannon.index ~ sa + urb + urb * sa + (1|ID), data = bees )

summary( shan.div.lme )
