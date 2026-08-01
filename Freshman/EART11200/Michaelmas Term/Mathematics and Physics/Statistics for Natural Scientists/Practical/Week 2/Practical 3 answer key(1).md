---
title: "Practical 3 answer key(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 2/Practical 3 answer key(1).docx"
type: document
---

Practical 3

Question 1

Q1.1: Is there a significant difference in the lengths of femurs of males among the three Hyla species in our data set? How do you know? Yes. We know this because the p-value associated with species (ie, the categories in our analysis) is less than 0.05.

Q1.2: What is the difference between the femur lengths of male H. cinerea and male H. chinensis? Is that difference statistically significant? The average femur length in H. cinerea is 7.98 mm longer than in H. chinensis. This is statistically significant (p < 0.0001).

Q1.3: Report the results of our ANOVA and post hoc Tukey test to readers clearly and concisely. Mean femur lengths differed among males of the Hyla species we studied (p < 0.0001). Femurs were longer in H. arenicolor than in H. chinensis (6.25 mm, p < 0.0001) and in H. cinerea than in H. chinensis (7.98 mm, p < 0.0001). We found no significant difference in the mean femur lengths of male H. cinerea and H. arenicolor (p = 0.3034).

Q1.4: Provide a figure to illustrate your results. Remember that your figure will need a caption that clearly and concisely explains everything the reader needs to know to understand the figure!

Question 2

Q2.1: Report the results of your analysis clearly and concisely. Mean femur lengths differed among females of the Hyla species we studied (p = 0.0022). Femurs were longer in H. arenicolor than in H. chinensis (4.70 mm, p < 0.0132) and in H. cinerea than in H. chinensis (5.52 mm, p < 0.0032). We found no significant difference in the mean femur lengths of male H. cinerea and H. arenicolor (p = 0.8621).

Q2.2: Provide a figure to illustrate your results.

Question 3

Q3.1 (Challenge): Last week we compared the size of males and females using t-tests. Can we use a t-test here? Why or why not? No, we cannot. T-tests assume that the data within the two groups to be compared (here, the sexes) is normally distributed. Ours is not. We have three species with different mean sizes, and if we pool the three species then there are multiple modes in the size data for each sex.

Q3.2: Inferring from the output of the commands above, do we have evidence that the femurs of one sex are predictably larger than those of the other in Hyla? No. Do we have evidence that sex affects femur size differently in different Hyla species? No.

Q3.3: Following the logic above, what code would I use for studying the main effect of sex in the genus Hyla?

hyla.femur.species.aov = aov( femur ~ species + sex, data = hyla)

summary(hyla.femur.species.aov)

Q3.4: Complete the report below by filling in the missing values from the analyses we have conducted. “The mean femur length differed among Hyla species when controlling for sex (p < 0.0001), but did not differ among sexes when controlling for species (p = 0.112). We found no evidence for an interaction between sex and species on femur length (p = 0.452). Overall, the mean femur length in H. arenicolor was greater than in H. chinensis by 5.47 mm (p < 0.0001), and the mean femur length in H. cinerea was greater than in H. chinensis by 6.73 mm (p < 0.0001). We found no significant difference in the mean femur length of H. arenicolor and H. cinerea (p = 0.4107).”

Q3.5 (Challenge): Do you notice anything about the figure above that might make us worry? If so, what is it? ANOVA assumes that the variances within each group are approximately equal, but here they look different.

Q3.6 (Super-challenge): Can you think of something we might do about it? As a first step, we might consider logging femur length before we study it.

Question 4

Q4.1: Does the p-value associated with the effect of sex in this analysis depend on whether we control for the effect of species? Yes.

Q4.2: When we report the effects of sex and species in this analysis, should the effect sizes come from the same Tukey test of from two different Tukey tests? Why? I would use two different Tukey tests – one to assess the differences between the sexes controlling for species, and one to assess the differences among species controlling for sex.

Q4.3: Report your results clearly and concisely. In the genus Eleutherodactylus, femur length differed among species when controlling for sex (p < 0.0001), and between sexes when controlling for species (p = 0.0001). The mean femur length in E. coqui was greater than that in E. marnockii by 2.57 mm and that in E. planirostris by 5.90 mm. All pairwise differences among species were strongly significant (p < 0.0001). Controlling for species, femur length in females was greater than that in males by 1.41 mm (p = 0.0001). We found no evidence that the effect of sex differed among species (p = 0.5167).

Q4.4: Provide a figure to illustrate your results.
