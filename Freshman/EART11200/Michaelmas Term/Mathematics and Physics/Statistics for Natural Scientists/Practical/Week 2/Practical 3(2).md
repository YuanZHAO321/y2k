---
title: "Practical 3(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 2/Practical 3(2).docx"
type: document
---

After completing practical 3, you will be able to:

- Conduct and report one-way ANOVA and post hoc Tukey tests

- Conduct and report two-way ANOVA

- Interpret interactions between predictors

- Illustrate the results of ANOVA with figures

Practical 3

In this week’s practical, we will revisit the data from Juarez and colleagues’ (2023) study of sexual dimorphism in anurans. Last week, the datasets we studied were prepared for you. Each dataset included information on just one species. Now that we know how to import and subset data, we can prepare the data ourselves. Let’s begin by importing an abridged version of the original dataset from Jaurez et al. (2023). You can find this in the file “data_from_Juarez_et_al_2023.csv”. I recommend that you name the data “anurans” – if you do that, then the starter code supplied with this practical will work without editing.

After you have imported the data, inspect it to make sure you understand what each column means. If you want to check that the data has imported correctly, you can count the number of rows in the data frame with the command:

nrow(anurans)

There should be 3325 rows.

Question 1

Last week we studied anuran species one at a time. This week we will study entire genera. A genus (plural: genera) is a group of closely related species. Ideally, a genus should be monophyletic. That is, the genus should include all the species, and only those species, descended from some common ancestor. Any species descended from that ancestor belongs in the genus, and any species not descended from that ancestor should belong to some other genus.

We will begin by studying Hyla, a genus of tree frogs found in parts of Europe, Asia, and North Africa. With commands you saw last week, you can create a data frame that includes only frogs in the genus Hyla. If you don’t immediately remember how to do this, don’t worry. This is only the second time you have done it! There is code in starter code to help.

There are 17 species of Hyla in nature, but only three in our dataset: H. arenicolor, H. chinensis, and H. cinerea. One question we might reasonably ask is whether these species are different sizes. Let’s begin by focusing on just males. We can create a dataset of just males by subsetting, just as we created a dataset of just Hyla from the full anuran data. You might want to try writing this line of code yourself, but there is starter code to help if you need it. Then, let’s test the hypothesis that the mean femur length in males differs among the three Hyla species in our data. When we compared the means of two groups last week, we used t-tests. To compare the means of more than two groups, we will use ANOVA. If you have read the unit handbook, you will already understand the logic behind this test. If you named your data set of male Hyla male.hyla as I did, then you can implement ANOVA to test the hypothesis above and see the results using the code:

hyla.femur.aov = aov( femur ~ species, data = male.hyla)

summary(hyla.femur.aov)

Q1.1: Is there a significant difference in the lengths of femurs of males among the three Hyla species in our data set? How do you know?

Our ANOVA tells us that the mean femur length in males differs among our three Hyla species, but it does not tell us which species differ from which others or by how much. Knowing that differences exist is not very useful if we don’t know what those differences are! We can study the differences among groups with a post hoc Tukey test. (This is Tukey, for John Tukey who invented it, not Turkey!) Note that we would not do a Tukey test if our ANOVA had not indicated that there were differences among the species. If we had no evidence that differences exist, then there would be no reason to ask how big they are.

TukeyHSD( hyla.femur.aov )

When you run this command, you should get the following output:

Tukey multiple comparisons of means

95% family-wise confidence level

Fit: aov(formula = femur ~ species, data = male.hyla)

$species

diff       lwr       upr     p adj

chinensis-arenicolor -6.24600 -9.009707 -3.482293 0.0000066

cinerea-arenicolor    1.73019 -1.082435  4.542816 0.3034225

cinerea-chinensis     7.97619  5.163565 10.788816 0.0000001

This table reports pairwise comparisons between the species in our analysis. The first row shows the comparison between H. chinensis and H. arenicolor. The p-value in the column labelled “p adj” tells us whether the difference is significant. Here, the value is less than 0.05, so it is significant. The column labelled “diff” tells us how big the difference is. For me, this is easiest to interpret if I read the dash in “chinensis-arenicolor” as a minus sign: the mean for H. chinensis minus the mean for H. arenicolor is -6.25 mm. So, on average, the femurs of H. arenicolor are longer by 6.25 mm. The second row shows the comparison between H. cinerea and H. arenicolor. In this row, the p-value is greater than 0.05. So, the means of random samples could easily differ this much by chance alone, and we cannot be confident that the femurs of these species really differ.

Q1.2: What is the difference between the femur lengths of male H. cinerea and male H. chinensis? Is that difference statistically significant?

How do we report these results to readers? Readers need to know both how big the differences are and how confident we are that those differences are real attributes of the system. So, they need both the effect sizes and p-values. My personal preference is to report the overall ANOVA result first, and then report the important pairwise comparisons. For the test above, I might write “Mean femur lengths differed among males of the Hyla species we studied (p < 0.0001). Femurs were longer in H. arenicolor than in H. chinensis (6.25 mm, p < 0.0001) and in H. cinerea than in H. chinensis (xxx mm, p < xxx). We found no difference in the mean femur lengths of male H. cinerea and H. arenicolor (p = 0.3034).” Of course, you will need to fill in the xxx’s from the table! Note that I did not report a difference for H. cinerea and H. arenicolor, because we have no evidence that they are different. Also, I have reported “p < 0.0001” for the very small p-values. In most cases, additional decimal places are not very informative to readers.

Q1.3: Report the results of our ANOVA and post hoc Tukey test to readers clearly and concisely. (You can copy the text above and just add in the missing values.)

Finally, how do we illustrate this result for readers? For ANOVA with one predictor (ie, one-way ANOVA), bar charts are often the best way. This is a more complicated than the bar charts we used for t-tests, because there are more bars, and we often want to sort the bars in rank order. This allows us to draw a line over bars that are not significantly different. Then, readers can easily see which values are different from which others, because values that are different do not appear under the same line. The starter code will make a figure for this analysis. With a bit of tinkering, you can modify it to make bar charts for other one-way ANOVAs you might do.

Q1.4: Provide a figure to illustrate your results. Remember that your figure will need a caption that clearly and concisely explains everything the reader needs to know to understand the figure!

Question 2

In question 1, we asked whether femur lengths differed among males of the three Hyla species in our dataset. Now, let’s do the same analysis for females. To do this, you will need to understand how our analyses work, but you can edit or reuse the code from question 1.

Q2.1: Report the results of your analysis clearly and concisely.

Q2.2: Provide a figure to illustrate your results.

Question 3

The Hyla species in our data differ in size. We just have shown this for both males and females. But, what if we now want to ask if the sexes differ in size? That is, we want to know whether the genus, as represented by the species in our study, is sexually dimorphic.

Q3.1 (Challenge): Last week we compared the size of males and females using t-tests. Can we use a t-test here? Why or why not?

Regardless of your answer to Q3.1, we are going to approach the question with a two-way ANOVA. A two-way ANOVA allows us to study the effect of one predictor (here, sex) while controlling for the effect of another (here, species). To do this, we will add two terms to the formula in our ANOVA. We will add sex, which we call the main effect of sex, and we will add species*sex which we call an interaction between species and sex:

hyla.femur.aov = aov( femur ~ species + sex + species*sex, data = hyla)

summary( hyla.femur.aov )

The main effect of sex tells us how the sexes differ in our Hyla species. The interaction whether the effect of sex is different for each Hyla species. For example, perhaps females are much bigger than males in one species and only a little bigger in another.

Q3.2: Inferring from the output of the commands above, do we have evidence that the femurs of one sex are predictably larger than those of the other in Hyla? Do we have evidence that sex affects femur size differently in different Hyla species?

Two-way ANOVA presents two issues that we do not face with t-tests or one-way ANOVA. First, the aov() command is sensitive to the order in which the terms enter the formula. Each term is tested while controlling for the term(s) to its left. So, in the code above, we are asking about the effect of sex while controlling for species. That is, if a male and female belong to the same species, would knowing the sex help us guess the relative length of their femurs? In contrast, the code is asking whether femur length differs among species without controlling for sex. So, we are not asking whether males of each species are different from males of the other species and females of each species are different from females of the other species, but rather whether each species in general (ie, both sexes combined) is different from each other species in general. If we want to know if there is an effect of species controlling for sex, we will need to run the code again with the order of the terms reversed.

hyla.femur.aov = aov( femur ~ sex + species + species*sex, data = hyla)

summary( hyla.femur.aov )

Note that the interaction always appears of the far right – it rarely makes sense to ask about interactions without controlling for the main effects of the terms in the interaction.

The second question we face with two-way ANOVA is what terms belong in the formula at all? We found no effect of the species-by-sex interaction in our ANOVA, so we have no evidence that the effect of sex differs among species. So, should we take it out of the formula? Similarly, we found no significant effect of sex while controlling for species, so we cannot be confident that sex affects femur length. So, if we have no evidence for an effect of sex, should we study species while controlling for sex (ie, with sex in the formula) or without controlling for it? Sadly, the answer is, “it depends.” There is a rule of thumb that says we should remove nonsignificant predictors from our ANOVAs, but that is not always the right thing to do. For example, perhaps we already know that femur length depends on sex in the genus Hyla. The fact that we didn’t find a significant effect in our data does not mean there is no effect – it just means that we did not find strong evidence for an effect. But, if we know there is an effect of sex from previous work, perhaps we want to control for sex anyway by leaving it in the formula. The is called “forcing” a predictor into the model. There is no clear right answer here, and happily that means there is also no clear wrong one. Personally, I would remove the interaction from the formula because we have no evidence that it matters, but I would study sex controlling for species (because we know femur length differs among species) and species controlling for sex (because we know femur length differs by sex in many other anurans). So, for species, I would use the following code:

hyla.femur.species.aov = aov( femur ~ sex + species, data = hyla)

summary(hyla.femur.species.aov)

Q3.3: Following the logic above, what code would I use for studying the main effect of sex in the genus Hyla?

As with one-way ANOVA, we can find the pairwise differences among groups with a post hoc Tukey test using the TukeyHSD() command. But, which pairwise differences do we care about? Well, our ANOVA says we have no evidence for an effect of sex controlling for species. So, there is no reason to look at the pairwise difference between the sexes, because we have no evidence that there is one. But, our ANOVA says there is an effect of species controlling for sex. So, let’s look at those pairwise differences:

TukeyHSD(hyla.femur.species.aov)

The output is more complicated, because this test will report the pairwise differences among sexes and among species. But, we are only interested in the differences among species. And, we can interpret those in the same way we interpreted the Tukey test from our one-way ANOVA.

As for all statistical tests, we will want to report our results clearly and concisely. I have supplied the text I would use in Q3.4. Complete the report by filling in the missing values from the analyses we have conducted.

Q3.4: Complete the report below by filling in the missing values from the analyses we have conducted. “The mean femur length differed among Hyla species when controlling for sex (p < 0.0001), but did not differ among sexes when controlling for species (p = 0.112). We found no evidence for an interaction between sex and species on femur length (p = xxxx). Overall, the mean femur length in H. arenicolor was greater than in H. chinensis by 5.47 mm (p < 0.0001), and the mean femur length in H. cinerea was greater than in H. chinensis by xxx mm (p = xxxx). We found no significant difference in the mean femur length of H. arenicolor and H. cinerea (p = xxxx).”

Finally, how might we illustrate our result? One simple way to do this might be with a box plot.  The starter code for this practical includes code to make figure 3. You could

reproduce the figure without reading the code, but I recommend you read it, because you will need to make a similar figure for question 4.

Q3.5 (Challenge): Do you notice anything about the figure above that might make us worry? If so, what is it?

Q3.6 (Super-challenge): Can you think of something we might do about it?

Question 4

Eleutherodactylus is a genus that includes more than 200 species of frogs and is native to the Neotropics. The most well-known species is the common coqui (Eleutherodactylus coqui), which is native to Puerto Rico but is an invasive pest in Hawai’i. E. coqui is also a common model species for the study of sexual selection. Juarez and colleagues (2023) reported data on three species of Eleutherodactylus. Using tools you learned in question 3, assess whether femur length differs among species and between the sexes in the species of Eleutherodactylus in Juarez and colleagues’ data.

Q4.1: Does the p-value associated with the effect of sex in this analysis depend on whether we control for the effect of species?

Q4.2: When we report the effects of sex and species in this analysis, should the effect sizes come from the same Tukey test of from two different Tukey tests? Why?

Q4.3: Report your results clearly and concisely.

Q4.4: Provide a figure to illustrate your results.

References

Juarez, B. H., Moen, D. S., & Adams, D. C. (2023). Ecology, sexual dimorphism, and jumping evolution in anurans. Journal of Evolutionary Biology, 36(5), 829-841. doi:10.1111/jeb.14171
