---
title: "Practical 4 answer key(2)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 3/Practical 4 answer key(2).docx"
type: document
---

Question 1

Q1.1: What is the name of the column that contains the light intensity data? The leaf area data? The fluctuating asymmetry data? The names are “light,” “leaf.area,” and “fa,” respectively.

Q1.2: Can you see a pattern in this data? If so, what direction does it go? Do you think it is statistically significant? To me it looks like there is a weak negative relationship between light intensity and FA. I would guess it probably is statistically significant, or at least very close.

Q1.3: Provide a figure to illustrate the relationship between light intensity and FA in the leaves of A. alliariae.

Q1.4: What is the expected FA for a leaf of A. alliariae if the light intensity at the leaf location is 12 log(lux)? 0.066

Question 2

Q2.1: Use linear regression to test the hypothesis that A. alliariae leaf size changes with light intensity at the leaf location. Report your results clearly and concisely. Leaf area decreases with increasing light intensity (-27.9 cm2 log(lux)-1, p < 0.0001).

Q2.2: Illustrate the results of Q2.1 with a figure.

Q2.3: What is the expected surface area of a leaf found growing at light intensity of 8 log(lux)? Of a leaf found growing at 12 log(lux)? The expected areas of leaves growing at 8 log(lux) and 12 log(lux) are 220 cm2 and 108 cm2, respectively.

Question 3

Q3.1: Does the model above provide evidence that light intensity affects FA controlling for leaf size? Does it provide evidence that leaf size affects FA controlling for light intensity? No, we have no significant evidence for either pattern.

Q3.2: Report the result of the analysis of light intensity controlling for leaf area. We found no effect of light intensity on fluctuating asymmetry when controlling for leaf size (p = 0.1745).

Q3.3 (Challenge): Does your answer to Q3.2 undermine the result we illustrated in Q1.3? Why or why not? No, I don’t think so. We made a guess that FA might depend on leaf area rather than light intensity. But, our model showed no effect of leaf area when controlling for light intensity, so I do not see a good reason to force leaf area into the model. Moreover, the direction and magnitude of effect of light intensity on FA are similar with or without leaf area in the model. We found weak evidence for a relationship between light intensity and FA in our first analysis, and I think we still have weak evidence.

Question 4

Q4.1: Looking at the figure you produced, does it look like the relationship between femur length and snout vent length is different in males than in females? If so, how is it different? To me it looks like maybe the slope of svl on femur length is slightly steeper in females.

Q4.2: Look at the results of the model above. Do we have evidence for an interaction between sex and femur length on svl in I. luetkenii? How do you know? Yes, because the p-value associated with the interaction is less than 0.05.

Q4.3 (Challenge): Controlling for femur length, do males have greater or lesser svl than females? It depends on the femur length.

Q4.4: Report the results of our analysis clearly and concisely. The relationship between femur length and svl differed in male and female I. luetkenii (p = 0.0191). In females, svl increased by 2.85 mm for each 1 mm increase in femur length. In males, svl increased by 1.52 mm for each 1 mm increase in femur length.

Q4.5: What is the predicted svl for a female yellow toad with femur length of 35 mm? 97.8 mm

Q4.6 (Super-challenge): Our model tells us that the slope of svl on femur length in females (ie, 2.8534) is significantly different from zero. This is potentially useful (although in this case not very surprising!). The slope of svl on femur length in males is smaller than in females. Specifically, it is 2.8534 - 1.3317 = 1.5217. Using tools that we have already learned, can you think of a way to test whether this slope is significantly different from zero? Report your result clearly and concisely. The model we are interpreting includes main effects of femur length and sex, where males are coded as 1 and females are coded as 0. When there is an interaction between two predictors in a model, the main effect reported for each predictor tells us the effect of that predictor when the other predictor has a value of 0. So, the effect of femur reported in the output table tells us how svl changes with femur length when sex is 0 – that is, in females. We can see from the p-value (< 0.0001) that this effect is significant. The interaction between sex and femur length tells us how the effect of femur length on svl differs in males relative to females. So, we can compute the effect of femur length on svl in males as 2.8534 - 1.3317 = 1.5217. The p-value associated with the interaction is for the interaction itself. That is, it tells us that the effect of femur length on svl is significantly different in males and females, but not whether the effect femur length on svl in males is significantly different from 0. The easiest way to get the p-value we want is to create a new predictor with females coded as 1 and males coded as 0 – we might call this new predictor “female.” If we replace “male” in the model above with our new predictor “female,” then males will be the sex coded as zero, and the main effect of femur length reported in the output table will be the effect for males. When I do that, I get the following output table:

Coefficients:

Estimate Std. Error t value Pr(>|t|)

(Intercept)   35.8173    12.7057   2.819  0.00909 **

femur          1.5217     0.4293   3.544  0.00151 **

female       -37.9116    16.1065  -2.354  0.02642 *

femur:female   1.3317     0.5328   2.500  0.01907 *

The effect of femur length on svl in males is exactly what we predicted, and the p-value associated with that main effect describes that relationship. I might report that “In male I. luetkenii, svl increased by 1.52 mm for each 1 mm increase in femur length (p = 0.0015).”

Question 5

Q5.1: Test the hypothesis that the relationship between femur length and svl is different in male and female E. planirostris. Report your result clearly and concisely. The relationship between femur length and svl differed in male and female E. planirostris (p = 0.00714). In females, svl increased by 2.81 mm for each 1 mm increase in femur length. In males, svl increased by 1.10 mm for each 1 mm increase in femur length.

Q5.2: Provide a figure to illustrate your result.

Question 6

Q6.1: Using the data with the dubious male data point removed, test the hypothesis that the relationship between femur length and svl is different in male and female E. planirostris. Report your result clearly and concisely. With the dubious data point removed, we found no evidence that the relationship between femur length and svl was different in male and female E. planirostris. (p = 0.216).

Q6.2: Test the hypothesis that males and females with the same femur length will have different expected svl. Report your result clearly and concisely. When controlling for femur length, we found no evidence that male and female E. planirostris had different snout-vent lengths (p = 0.114).

Q6.3: Test the hypothesis that male and female E. planirostris have different mean femur lengths. Report your result clearly and concisely. Female E. planirostris had longer femurs than males (9.57 mm vs 8.14 mm, p < 0.0001).

Q6.4: Provide figures to illustrate any significant results from Q6:1-3.
