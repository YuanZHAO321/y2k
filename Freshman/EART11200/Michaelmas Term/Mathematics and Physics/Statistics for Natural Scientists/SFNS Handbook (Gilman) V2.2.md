---
title: "SFNS Handbook (Gilman) V2.2"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.pdf"
type: pdf
---

# **Basic Statistical Approaches for the Natural Sciences**

## **Version 2.2**

**R. Tucker Gilman 2 November 2022**

### **Table of Contents**

|Chapter 1: Introduction......................................................................................................................... 2|
|---|
|What is Science? .................................................................................................................................. 2|
|Testing hypotheses: manipulations and observations ........................................................ 2|
|Some important concepts in experimental design ................................................................ 3|
|Types of data ........................................................................................................................................ 9|
|Some useful sampling methods .................................................................................................. 10|
|Chapter 2. Comparing the means of two groups ....................................................................... 13<br>|
|Preparing data for analysis ........................................................................................................... 13|
|Visualising the data .......................................................................................................................... 14|
|Approach 1. The Monte Carlo method ..................................................................................... 17|
|One-tailed and two-tailed hypothesis tests............................................................................ 22|
|Approach 2. The t-test .................................................................................................................... 24|
|Reporting results .............................................................................................................................. 27|
|The normality assumption ............................................................................................................ 29|
|Chapter 3. Comparing the means of more than two groups................................................. 33|
|Working through an ANOVA ........................................................................................................ 34|
|Conducting an ANOVA in R ........................................................................................................... 38|
|The_post hoc_Tukey test .................................................................................................................. 38|
|<br>Assumptions and alternatives ..................................................................................................... 40|
|Two-way ANOVA .............................................................................................................................. 43|
|Chapter 4. Understanding the effects of numerical predictors ........................................... 47|
|Simple linear regression ................................................................................................................ 48|
|Mean centring predictors .............................................................................................................. 51|
|<br>Dichotomous predictors ................................................................................................................ 52|
|Multiple linear regression ............................................................................................................. 54|
|Interactions ......................................................................................................................................... 57|
|Selecting and reporting best models ........................................................................................ 60|
|Collinearity .......................................................................................................................................... 62|
|Assumptions of linear regression .............................................................................................. 64|
|Rank correlation tests ..................................................................................................................... 69|
|Chapter 5. Categorical responses to categorical predictors ................................................. 71|
|Testing for deviations from_a priori_expectations ............................................................... 71|
|_Post hoc_testing for differences among responses............................................................... 75|
|Reporting differences among responses ................................................................................. 76|
|Testing for differences in response frequencies among groups .................................... 78|
|Chapter 6. Categorical responses to numerical predictors ................................................... 85<br>|
|Conducting logistic regression in R ........................................................................................... 87|
|Studying quantitative and qualitative predictors in the same model ......................... 91|
|Reporting the results of logistic regression ........................................................................... 93|
|Using logistic regression to predict probabilities ................................................................ 97|
|An important assumption of logistic regression .................................................................. 99|
|Appendix 1: Choosing a statistical test ...................................................................................... 100|
|Appendix 2: Installing and navigating R .................................................................................... 101|
|R:_the_tool for statistical analysis in ecology and evolution .......................................... 101|
|<br>Installing and navigating R ........................................................................................................ 101|
|An overview of the RStudio interface .................................................................................... 102|
|Some notes on using the native R interface ........................................................................ 107|
|Finding help with R ....................................................................................................................... 108|
|Downloading and installing R packages ............................................................................... 109|
|<br>Index ........................................................................................................................................................ 110|

1

### **Chapter 1: Introduction**

#### **What is Science?**

When you complete your study at the University of Manchester, you will have earned a degree that says you are a scientist. But, what _is_ Science? What makes Science different from other academic pursuits?

Many people think that Science is simply a way of organising information about the world around us. But, by itself, that is not enough to make something Science. Philosophy and religion are also ways of organising information about the world, but they are not sciences.

What differentiates Science from other academic pursuits is that in Science, we compare our beliefs about the world around us to empirical evidence. This means that Science is not something we can just read in a book. It is something we _do_ . We do not have to go to the lab or the field to do Science. We might use empirical evidence that someone else has collected. Perhaps we might find that evidence in a book or in a paper. What is critical is that we use that evidence to test our ideas. If our ideas are not consistent with the evidence, we modify our ideas. It is not enough to read a statement or a description of a process and believe it simply because we have faith in the source. In some cases, faith may be a useful and reasonable thing. But, it is the antithesis of Science.

#### **Testing hypotheses: manipulations and observations**

In Science, an idea that we compare to evidence is called a _hypothesis_ . A hypothesis is simply a statement that we think _might_ be true. Scientists justify hypotheses by arguing that they are consistent with evidence that we already have. This argument is called a _rationale_ .

Most empirical tests of hypotheses can be placed into one of two categories. They are either _manipulative_ or _observational_ .

When people think of experiments, they usually think of manipulative tests. In a manipulative test, a scientist creates a study group that is exposed to some treatment, and another group (a _control_ ) that is not exposed to the treatment. Imposing or withholding treatments is the manipulation. The scientist measures a trait of interest (the _response_ ) in the treatment and control groups, and compares this between the groups.

For example, a scientist might want to know if mice exposed to a particular chemical are more likely to develop cancer. She creates two study groups that are as close to identical as possible. She randomly selects one group to be exposed to the chemical. The other group is not exposed. At some predetermined time after the treatment, she assesses the frequency of cancer in both groups, and she compares the frequency in the treatment group to that in the control group.

2

One advantage of a well-designed manipulative study is that we can sometimes infer causality. If two groups are identical before a treatment and are not identical afterward, it may be reasonable to believe that the treatment _caused_ the difference.

In some fields, and particularly in ecology and evolution, manipulative studies are not always possible. For example, we may want to know if bigger animals are more successful competitors. We cannot simply change an animal’s body size, so we cannot study this with a manipulation. Instead, we must perform an observational study. To do this, we take advantage of the fact that there are different sized animals in natural populations. We measure the sizes and the competitive abilities of many different animals. (One might ask _how_ we measure competitive ability, but we will leave that question for another time!) Then, we analyse the results to ask whether larger animals are better competitors.

Usually, observational studies cannot determine causality. For example, we might find that larger animals are better competitors, but this does not tell us whether being larger makes them better competitors or whether being better competitors allowed them to become larger. To answer this, we would need to perform additional studies.

An observational study does not mean that we simply go out and look at something, and then tell a story about it. Data from observational studies must be rigorously analysed and compared to hypotheses. What makes them observational is simply that we observe naturally occurring variation in the systems we wish to study rather than creating that variation ourselves.

#### **Some important concepts in experimental design**

There is no single, correct way to design an experiment. Usually there are good ways, less good ways, and many bad ways. The most important thing that makes an experimental design “good” is that it is practical. That is, the scientist can do it. A less good design might provide less evidence, or it might take more time or money to achieve. A bad design will not provide the right kind of evidence at all. It is possible to design an experiment that will tell us absolutely nothing, even if we collect all of the data that we plan to collect!

Designing good experiments requires a combination of background research, careful planning, and experience. Even professional scientists often design experiments that are not as good or as efficient as they might be. This is why professional scientists always have colleagues look over their experimental designs before they start work. Throughout your career, you will find it is useful to discuss your experimental designs with your peers.

While there is no clear set of rules to ensure that your experimental designs are flawless, there are some important concepts that are worth considering each time you plan an experiment.

3

#### _The control_

The control is a study group that does not receive the experimental treatment. Researchers use the control as a baseline against which they can compare the treated group.

It is a common misconception that every experiment must have a control. It is enough that an experiment will allow us to study the effect of a factor of interest when it is applied at different levels. In a manipulative experiment, the treatment is the factor of interest. If one level of treatment is a logical baseline, that level is often called the control. In the example in the last section, the scientist wanted to know whether a particular chemical causes cancer. The absence of that chemical might reasonably be called a control.

Sometimes, it is less clear whether a particular study group is a control. For example, imagine that we wanted to know whether mosquito flight speed depends on air temperature. We might measure flight speed at 10 °C and 20 °C. But, which of these is the control? Or, is there a better control to use? Certainly it does not make sense to measure flight speed at 0 °C. This temperature means something special for water, but it might not mean anything special for mosquitos. In this experiment, there is really no need to define a control at all. It is enough to compare flight speed at the two temperatures and ask how it differs.

Observational studies are particularly unlikely to have controls. These studies take advantage of natural variability in a factor of interest. In the example about body size and competitive ability above, body size is the factor of interest, and every animal might have a different body size. There is no “control.” Rather, when we analyse the data, every animal in the study will be compared to every other animal. We will consider how such comparisons are made in the chapter on linear regression later in this handbook.

#### _Randomness_

In the early 1900s, _The Literary Digest_ was one of the most important news magazines in the United States. On 31 October 1936, the magazine published the results of what was at the time the largest presidential preelection poll in US history. The magazine predicted that Republican Alf Landon would defeat Democrat Franklin Roosevelt by a landslide of 57% to 43%. Three days later, the election was held. The magazine was right in one respect – the election was a landslide. But, Roosevelt won by 61% to 37%. The magazine’s loss of credibility was so great that it went out of business two years later.

What went wrong? _The Literary Digest_ ’s poll was extensive. They selected likely voters from magazine subscription lists, automobile registration records, and telephone directories. But, 1936 was in the depth of the Great Depression, and only people with disposable income could afford magazines and automobiles. Many lower income households did not have telephones. So, the magazine’s poll disproportionately sampled wealthy voters. Then as now, wealthy voters were more likely to vote for Republicans.

4

The results of _The Literary Digest_ poll highlight one of the most important rules of experimental design: if we want to draw conclusions about a study group, sampling from that group must be random. _The Literary Digest_ poll failed because the pollsters tried to draw conclusions about the voting patterns of all Americans based on a sample that was composed disproportionately of wealthy Americans.

In practice, most samples are not truly random. For example, if you will study salamanders in the lab, your sample will include only salamanders that you can catch. These salamanders might be slower, less cryptic, or less cautious than the salamanders you cannot catch. So, when designing experiments, the question we must ask is not whether the sample is random, but whether it is _random enough_ . That is, is it random with respect to the variables that we want to study? Often there is no absolute answer to this question. But, if you cannot make a convincing argument that the answer is “yes,” then your results are unlikely to satisfy scientifically-minded readers.

#### _Confounding factors_

In manipulative experiments, researchers often create (or try to create) study groups that differ in only one factor. For example, in the mouse cancer study we considered above, the treatment and control groups were identical except in their exposure to the chemical of interest. In field studies, we usually cannot control every factor that might affect the study subjects. For example, competitive ability might depend on size, but it might also depend on age, sex, and a number of other factors. Individuals in the study might differ in several of all of these ways. We call these confounding factors, because they have the potential to confound the study results.

A particular problem arises if confounding factors are not independent of the factors we wish to study. For example, imagine again that we are studying how competitive ability depends on body size, but we are conducting our study in a population where males are larger than females. Now, imagine that body size does not affect competitive ability, but sex does. For example, imagine that males are more competitive than females. If we study only body size and competitive ability, we will infer that larger animals are more competitive, even though the pattern is really driven by sex and not size (see figure 1.1 on the next page).

One way to deal with the confounding effect of sex in this example would be to study the effect of body size on competitive ability within each sex separately. We will think about other ways to deal with confounding factors when we study linear regression later. In every case though, the first step in dealing with confounding factors is to recognise that they might exist. This is an important part of experimental design.

5

<!-- Start of picture text -->
8 10 12 14 16 18<br>body size<br>30<br>25<br>20<br>competitive ability<br>15<br><!-- End of picture text -->

**Figure 1.1 Competitive ability as a function of body size in a population with sexual size dimorphism.** Open circles represent females, and filled circles represent males. Within each sex, body size does not affect competitive ability. However, males are both larger and more competitive than females. So, if we plot a best-fit line for competitive ability on body size without considering the confounding effect of sex, we will incorrectly infer an effect of body size.

_Power_

Power refers to the ability of an experiment to detect the effect that the researcher wants to study. Power depends on 1) the effect size, 2) the amount of unexplained variability in the data set, and 3) the sample size.

For example, imagine that you are studying how skull length in yellowpine chipmunks ( _Tamais amoenus_ ) depends on sex (see Schulte-Hostedde and Millar 2000). Imagine that the _true_ average length of adult female skulls is 36.95 mm and the true average length of adult male skulls is 36.49 mm. The _effect size_ is then 36.95 mm – 36.49 mm = 0.46 mm. So, in yellow-pine chipmunks, one effect of being a female is that the skull is longer by an average of 0.46 mm. As a researcher, you will not have this information when you start your experiment. Rather, this is the information your experiment will attempt to discover.

In most animals, skull length can vary due to factors other than sex. For example, adult skull length might depend on an individual’s genes, or on its diet as a juvenile. If we do not have data on individuals’ genes or juvenile diets, then we will see this variability in skull length in our data, but we will not be able to explain it. Unexplained variability in our data is sometimes called _noise_ .

Most data sets also include measurement error. For example, two skulls might have the same length, but a researcher may measure one as being slightly longer than the other. We cannot explain measurement error – if we knew there was an error in a measurement, we would simply fix the error! Therefore, measurement error is always unexplained.

The histograms in figure 1.2 on the next page show the distributions of male and female skull lengths in a simulated chipmunk population. What determines whether we will be able to detect a difference between female and male skull lengths? Not surprisingly, the effect is easiest to detect when the effect size is large relative to unexplained variability. Usually, there is little we can do about the effect size – we have to work with the effect size we have in our study system – but we can often do something about noise. Sometimes we can reduce noise by designing experiments that minimise measurement error. Or,

6

<!-- Start of picture text -->
male<br>female<br>35 36 37 38 39<br>skull length<br>30000<br>frequency<br>0<br>30000<br>frequency<br>0<br><!-- End of picture text -->

**Figure 1.2 Skull length in male and female yellow-pine chipmunks** (simulated data) **.** Females have larger skulls, and thus the histogram for females is shifted to the right relative to that of males.

someti ~~m~~ es we can reduce noise by explaining variability rather than removing it. We wil ~~l consider~~ <u>ways to explain</u> ~~<u>variabili</u>~~ ty when we study linear regression later.

Finally, we can often increase the power of our studies by increasing the sample size. If we know (or can guess) how large our effect size is, and if we know (or can guess) how much unexplained variability we will have in our data, then we can calculate how large a sample we will need to have a reasonable chance of detecting the effect ( _e.g_ ., figure 1.3). This is called _power analysis_ . Power analysis is a large subject in its own right, and we will not cover it in detail in this unit.

In the absence of a formal power analysis, a useful shortcut is to look at what other researchers have done. If researchers studying questions and systems similar to yours have found strong results with samples sizes of 20 or 50, then a similar sample size may work for you. If researchers have needed sample sizes in the 1000s to get even weak results, then you may need a very large sample size as well.

#### _Repeatability_

Measurements that you make as part of your experiment should be repeatable. That is, if you make the same measurement twice, or if someone else makes the same measurement using your experimental protocol, the result should be the same each time. Measurements with low repeatability have more measurement error and generate data with more noise.

<!-- Start of picture text -->
0 20 40 60 80 100<br>samples per sex<br>0.8<br>0.4<br>prob. of detecting effect<br>0.0<br><!-- End of picture text -->

**Figure 1.3 Probability of detecting a significant difference (** **_α_ = 0.05) in skull length between female and male yellow-pine chipmunks, as a function of the number of individuals sampled per sex.** The analysis assumes that the effect size is 0.46 mm, the standard deviation in skull length within sexes is 0.50 mm, and the researcher will approach the analysis with a two-sample t-test.

7

Some kinds of measurements are very repeatable. For example, you might be interested in the number of eggs in house sparrow ( _Passer domesticus_ ) nests. Measuring the number of eggs in a given nest is simply a matter of counting. If you count the eggs in a nest 100 times, you will always get the same answer.

Other kinds of measurements are less repeatable. For example, the condition of a moth or butterfly wing can indicate the age of the insect and whether it has migrated. Older insects and insects that have migrated show more wing wear ( _e.g_ ., Deinert 2003). But, how do we measure wing wear? Moth and butterfly wings loose scales over time, so one way to measure wing wear is to assess the number of scales that remain on the wing. Counting individual scales is difficult even under a microscope, so researchers often quantify scale loss visually on a simple 1-7 scale. Even if the criteria for each of the seven classes are precisely defined, different observers are likely to rate the same wing differently, and even the same observer might rate the same wing differently on different days. One solution to this problem is have the same observer take all of the measurements, preferably over a short period of time. Another is to take the measurement multiple times, and then to take the average. Averages are more repeatable than individual measurements.

If we absolutely must use data collected by different observers, we can sometimes correct for differences between observers in our analysis. We will consider ways to do this when we study ANOVA later in this handbook.

Repeatability is sometimes confused with _reproducibility_ . If another researcher wants to test your results, they may wish to reproduce them. That is, they may wish to repeat your experiment exactly and see if their results are the same. If a researcher wants to reproduce your measurements, they need to know exactly how you made those measurements. If they want to reproduce your study they need to know exactly what your methods were, and if they want to repeat your analysis they need to know exactly how you did it. As you design your experiments, and later as you report your results, it is important to record your methods with precision and detail. If another researcher could not repeat your experiment exactly by following your methods, then your work is not reproducible. Sometimes you may need to modify your methods during an experiment, but if you do that you must be extremely clear about how and when you did it!

#### _Sampling units_

In order to understand sample size, we must correctly identify the sampling unit. Sampling units are members of the population in which we hope to detect a pattern with our experiment. For example, our goal might be to compare the metabolic rates of male and female rainbow trout ( _Oncorhynchus mykiss_ ). In this case, we are looking for a pattern among trout – we want to know if trout with one characteristic ( _i.e_ ., being male) have a different metabolic rate than trout with another characteristic ( _i.e_ ., being female). The population is rainbow trout, the members of the population are fish, and the sampling unit is the individual fish. In another study, our goal might be to compare the metabolic

8

rate of rainbow trout in warm lakes to that of rainbow trout in cold lakes. In this case, we are looking for a pattern among lakes – do warm lakes have trout with different metabolic rates than cold lakes. The metabolic rate of its trout is simply a characteristic of a lake. Here, the population is lakes, and so the sampling units are individual lakes.

Ecological studies often require multi-level sampling. In the case above, the sampling unit is the lake, but the information we have about each lake is estimated from a sample of fish taken from that lake. We _could_ estimate the metabolic rate of the fish in a lake by sampling just one fish from each lake. But, if the metabolic rate varies widely among fish within lakes, then this estimate will have high uncertainty and thus low repeatability. Increasing the number of fish we sample from each lake increases the accuracy of our estimate, reduces measurement error, and so reduces noise in our data. However, sampling more fish from each lake does not increase our sample size for the purpose of drawing conclusions about lakes. If we sample only two lakes, our sample size is two, regardless of how many fish we sample. With a sample size of two, we will not be able to draw conclusions about warm and cold lakes. Misidentifying sampling units, and therefore trying to draw conclusions based on unreasonably small samples, is a common design flaw for early-career researchers.

#### **Types of data**

How we analyse data depends in part on the type of data that we have. We will consider the analyses later, but it will be useful first to define the types of data that we will encounter. There are two broad classes of data: _numerical data_ and _categorical data_ .

#### _Numerical data_

Numerical data are data that can be represented by numbers. There are two important sub-types of numerical data. _Discrete data_ can take only some values within a particular range. Often, these values are integers. For example, the numbers of eggs in each of a set of bird nests would be discrete data. The number of eggs in each nest must be an integer. A nest cannot contain 3.5 eggs. In contrast, _continuous data_ can take any value within a specified range. Body mass is an example of continuous data. Body mass can take any positive value. The number of decimal places to which we can measure an individual’s body mass is limited only by the accuracy of our equipment.

#### _Categorical data_

Categorical data consists of names or categories rather than numbers. For example, the species names of a set of individual trees would be categorical data. There are many types of categorical data, but there are two special cases that we will encounter in this unit. _Dichotomous data_ are categorial data with only two categories. For example, in some animal species, individuals can be classified as either male or female (although this is not true in other species!). Or, an individual tree can be classified as either dead or alive. _Ordinal data_ consists of

9

names or classes, but the classes can be logically ranked. One example of ordinal data is data that can be the measured on the Likert scale. The Likert scale is named for the organisational psychologist Rensis Likert who pioneered it. It is widely used in psychology and social science to assess people’s attitudes toward particular subjects. Typically, the Likert scale consists of five classes – strongly disagree, disagree, neither agree nor disagree, agree, and strongly agree. The data are ordinal because there is a logical order in which the classes can be placed. For example, “disagree” falls between “strongly disagree” and “neither agree nor disagree.” Researchers sometimes attach numbers to the categories of ordinal data. For example, a researcher might ask people to rate their agreement on a scale of 1 to 5, where 1 means strongly disagree and 5 means strongly agree. However, the answers are still classes and not numbers. To see why this is true, try doing maths with it. We cannot simply add up five “strongly disagrees” and say that is equal to a “strongly agree!”

Sometimes, one class of data can be converted into another. We will consider ways of doing this when we study linear regression later in this handbook.

#### **Some useful sampling methods**

For some kinds of experiments, sampling is relatively straight-forward. For example, we might be interested in how the circumference of English oak trees ( _Quercus robur_ ) depends on their age. We could define the population we want to study ( _e.g_ ., oaks in Lyme Park) and randomly select the trees to be sampled. Then, we could measure the tree circumferences, and take core samples to determine tree ages. Even in this simple experiment, sampling protocols would need to be precisely defined. For example, how will we select which trees to measure? At what height above the ground will we measure circumference? What will we do if there is a branch protruding at exactly the height where the circumference is to be taken? However, with careful planning, we could deal with most sampling problems we might encounter in this study.

However, experiments in ecology and evolution often require measuring attributes that are more complex than tree circumference or age. For example, the goal might be to characterise a habitat patch according to the species that live there. If the habitat patch is large, then counting every plant or animal in the patch may be impossible. Instead, ecologists commonly estimate the species composition of the patch by subsampling. Two common methods are _quadrat sampling_ and _transect sampling_ .

Quadrats are usually squares of a fixed size. Often researchers use rigid square frames to outline quadrats. Other times, quadrats are laid out with string. Sometimes (in a slight misuse of terminology), researchers use circular or even triangular “quadrats.” In each case, researchers sample the individuals that fall within the quadrat. Care must be taken to define what is meant by “within.” If the individuals are plants, they might fall partly within the quadrat. If they are animals, they might enter the quadrat or leave it during sampling. The researcher must determine how such individuals will be counted. For example,

10

will he count only individuals that are completely within the quadrat, or all individuals that are at least partly within the quadrat? After sampling, the researcher can combine results across many quadrats to infer the character of the full habitat patch.

Transects establish lines rather than areas for sampling. Sometimes a researcher will set the start and endpoints of each transect, and suspend a string between those points to demark the line. Individuals that fall directly beneath the string are sampled. Other times, the researcher might set start and endpoints and walk between them in a straight line without a visible guide. In this case, the researcher will often sample all individuals that lie within a predetermined distance of the transect line.

Quadrats and transects establish units of fixed size and shape in which sampling will take place. Sometimes quadrats and transects are placed randomly in the patch that will be assessed. At other times, they are uniformly spaced. In either case, it is critical is that the placement of quadrats and transects be independent of the response variables to be studied.  For example, if the goal is to assess flower density, one must not place quadrats preferentially in areas with more flowers. Arriving at an unbiased protocol for determining quadrat or transect locations can require careful thought!

Behavioural studies face a similar challenge. How do we sample and characterise the complex set of behaviours that an animal can exhibit? The first step in this process is to create precise definitions for each behaviour that we will record. Good definitions allow us to unambiguously identify each behaviour, and so ensure repeatability.

Sampling itself is usually conducted by one of two methods. In _scan sampling_ , the researcher identifies fixed points in time at which sampling will take place. Then, the researcher records what each animal in the population is doing at those precise times. This method allows the researcher to estimate a time budget for animals in the population, and does not weight one animal’s behaviours more heavily than anothers. However, data from scan sampling can be biased if animals can leave the sampling site, and if those animals might behave differently when they are away from the sampling site. Moreover, scan samples do not tell us the order in which individuals perform behaviours, and may not be useful if the goal is to predict future behaviours based on current behaviours.

Another form of behavioural sampling is the _focal follow_ . In focal follows, the researcher selects a particular animal, and records everything that animal does during a fixed time period. Focal follows allow researchers to get detailed information about the behaviour of particular animals, and about the order in which behaviours occur. However, because they focus on individual animals, they generate less information about the population as a whole than behavioural scan sampling.

11

As with other parts of experimental design, there is no single “right” way to choose a sampling method. Rather, you will need to choose the method that is most likely to provide the information you need to answer the research question.

#### **Literature cited**

Deinert, E. I. 2003. Mate location and competition for mates in a pupal mating butterfly _in_ C. L. Boggs, W. B. Watt, and P. R. Ehrlich, eds. _Butterflies: Ecology and Evoluiton Taking Flight_ . The University of Chicago Press, Chicago, IL.

Schulte-Hostedde, A. I. and J. S. Millar. 2000. Measuring sexual size dimorphism in the yellow-pine chipmunk ( _Tamias amoenus_ ). Can J Zool 78:728-733.

12

### **Chapter 2. Comparing the means of two groups**

In Science, we test our ideas by comparing them to empirical evidence. The ideas we test are hypotheses. We use experiments to generate data, but how do we turn those data into evidence to test our hypotheses? There are many approaches, but in this handbook we will focus on one common approach: _frequentist hypothesis testing_ .

Frequentist hypothesis testing was developed by biologist, geneticist, and statistician Ronald Aylmer Fisher (figure 2.1). Fisher argued that we cannot prove a hypothesis is true, but we can demonstrate that a hypothesis is _likely to be true_ by demonstrating that the alternatives are likely to be false. Fisher’s reasoning can be best explained with examples. Indeed, most

**Figure 2.1. Sir Ronald A. Fisher.**

of the rest of this handbook consists of examples in which we apply frequentist hypothesis testing. However, before we begin to think about examples, we need to take a step back and think about how to prepare data for analysis.

#### **Preparing data for analysis**

The most common mistake that earlycareer researchers make when beginning to analyse their data is to organise the data in the wrong way. Fortunately, this is easy to avoid.

The best way to set up your data is almost always in the form of a table. Each row in the table corresponds to a single observation, or _data point_ . Each column represents one description of that observation. For example, the data in table 2.1 are part of a set collected by Anne Hayden and Andrew Essink. Hayden and Essink studied the time people spent in restrooms in the Rivertown Crossings Mall in Grandville, Michigan on three different days in November of 2003. For each observation, they recorded the number seconds from the time a person entered the restroom

|**duration**|**gender**|**date**|
|---|---|---|
|93|women|Thursday|
|183|women|Thursday|
|124|women|Thursday|
|214|women|Thursday|
|122|women|Thursday|
|78|women|Friday|
|186|women|Friday|
||…||
|110|men|Saturday|
|60|men|Saturday|
|62|men|Saturday|
|59|men|Saturday|
|45|men|Saturday|
|86|men|Saturday|
|116|men|Saturday|
|69|men|Saturday|

**Table 2.1. Visit durations to men’s and women’s restrooms at the Rivertown Crossings Mall in November 2003.**

until they came out. They also recorded the gender of the restroom that the person entered (they could not directly observe the gender of the person), and they recorded the day of the week on which the visit took place. Each row in table 2.1 corresponds to one observed restroom visit. The first column tells us how many seconds the person spent in the restroom, the second tells us the

13

gender of the restroom the person entered, and the third tells us the day of the week on which the visit took place. Table 2.1 shows only part of the data set. The full data set is in the folder Data Sets on Dropbox (restroom_time.csv).

Hayden and Essink were interested in studying how the visit duration depends on the gender of the restroom visited. So, visit duration is their _response variable_ . Gender of the restroom and day of the week are variables that might affect the visit duration. Different books and different statistical software use different names for variables that might affect a response ( _e.g_ ., independent variables, covariates, factors). In this handbook we will call them _predictors_ . By convention, researchers often put the response variable in the first column of the data table, but as we will see later this is not required.

#### **Visualising the data**

Let’s visualise the full restroom data set. One way to do this is to look directly at the data itself. To do this, you can download restroom_time.csv from Dropbox into a folder on your computer, and open the file in a spreadsheet programme like Excel. You will see the same data illustrated in table 2.1, but there will be more of it.

We can also visualise the restroom data using R. If you have not yet downloaded R onto your computer, do that now (see Appendix 2 for instructions). Then, open R. You will need to tell R where to find the data you want to study. If you are using the RStudio interface, you can go to the “Files” tab in the bottom right panel and navigate to the directory where your data are stored. Then, from the “More” menu, select “Set As Working Directory.” If you are using the native R interface, you can set the working directory from the “Misc” menu on a Mac or the “File” menu on a PC. Finally, read the restroom time data into R by typing the command

rt=read.csv("restroom_time.csv",header=TRUE)

at the command prompt in the R console. This command reads the data set from the working directory, and saves it in data frame named rt. I used rt for “restroom time,” but you could give the data a different name if you prefer. The text header=TRUE tells R that the first row of restroom_time.csv contains the names of the data in each column. To see the full data set, type the name of the data frame into the console

rt

|duration|gender|day|
|---|---|---|
|1      93|women|Thursday|
|2      183|women|Thursday|
|3      124|women|Thursday|
|4      214|women|Thursday|

…

If you want to see just the list of durations instead of the full data set, type

14

rt$duration

(2.3)

[1]   93 183 124 214 122  78 186  54 311 200 126 144 121  85  72 158 [17] 157 147  96  64  92 108 149 129 301 185 212 182 180  46  79 104 [33] 113  96 135 128 282 104  65 108 106  98 136  84  91 106  49  89 [49] 246  73  47  66  74  64  91 267  82  73 114  73  48  85  63  82 [65]  90 106  54 432  68  67  48 250  66  92 206  59  93 353  67  53 [81]  87 146 116 177 149  91  92  91  68 110  60  62  59  45  86 116 [97]  69

This command tells R to display the data in the column duration of the data frame rt. The durations will be shown as a list rather than a column, but the data is exactly the same as in the full data frame. Lists like this one that have only one dimension ( _i.e_ ., one row or one column) are called _vectors_ .

Often, it is easier to visualise data with figures than with tables or lists. One intuitive way to visualise the restroom data is with a histogram. To see a histogram of visit durations, type

hist(rt$duration,breaks=20,xlab="visit duration in seconds")

into the R console. Here, the text hist(rt$duration … tells R to make a histogram of the duration data. The text breaks=20 tells R to collect the visit durations into 20 bins. Each bin corresponds to a bar in the histogram. The text xlab="… tells R how to label the _x_ -axis. The output will look like figure 2.2.

<!-- Start of picture text -->
100 200 300 400<br>15<br>Frequency 5<br>0<br><!-- End of picture text -->

visit duration in seconds

Figure 2.2 shows the duration of visits to both the men’s and women’s **Figure 2.2** . **Durations of restroom visits in Rivertown Crossings Mall in November of** restrooms. However, if we want to **2003.** compare visits to the two restroom types, it may be useful to see the men’s and women’s restroom data plotted separately. We can do this with the commands

**Figure 2.2** . **Durations of restroom visits in Rivertown Crossings Mall in November of 2003.**

split.screen(c(2,1))

screen(1) b=20*(1:22) hist(rt$duration[which(rt$gender=="men")],breaks=b, main="men",xlab="visit duration in seconds")

screen(2) hist(rt$duration[which(rt$gender=="women")],breaks=b, main="women",xlab="visit duration in seconds")

15

Figure 2.3 shows the result. The code we used to make this figure might seem more complicated than the code we used to make figure 2.2, but if we break it down we can understand it.

1. split.screen(c(2,1)) tells R to split the display screen. The c(2,1) tells R that the display screen should have two rows and one column. This creates a two-panel output, with one panel directly over the other.

2. screen(1) tells R to draw the next figure in the first panel of the split screen.

3. We will use the vector b to define bins for the histograms. In figure 5, we told R to make 20 bins, but we let R choose the best bin spacing to display the data. This time though, we are making different panels for the men’s and women’s

#### **men**

<!-- Start of picture text -->
100 200 300 400<br>visit duration inseconds<br>women<br>100 200 300 400<br>visit duration in seconds<br>12<br>6<br>Frequency<br>0<br>8<br>4<br>Frequency<br>0<br><!-- End of picture text -->

**Figure 2.3** . **Durations of visits to men’s (top) and women’s (bottom) restrooms in Rivertown Crossings Mall in November of 2003.**

restrooms. To make it easy to compare between these panels, we want to make the bins in each panel exactly the same. So, we will tell R where we want the bins. In the command b=20*(1:22), the (1:22) makes a vector of the numbers 1, 2, …, 22, and the 20* multiplies each number in this vector by 20. So, b is a vector with entries 20, 40, …, 440. By setting breaks=b, we tell R to use these as the breakpoints for the bins in the histogram.

4. main="… tells R how to label each histogram in our figure.

5. Finally, and most importantly, rt$duration[which(rt$gender=="men")] tells R which data to use in the histogram. This piece of the code is composed of several parts, and it is easiest to understand if we break if down even further.

   - a. Recall that rt$duration is a vector that contains the durations of restroom visits in our data set. Similarly, rt$gender is a text vector that reports which restroom each person visited.

   - b. The command which looks at a list of logical statements, and returns the numbers of the statements that are true. The “==” operator is a logical statement that returns TRUE is two things are equal and FALSE if they are not equal. So, which(rt$gender=="men") returns the row numbers of all of the restroom visitors in our data set that entered the men’s restroom.

   - c. The syntax “[…]” is used for _indexing_ . It tells R to choose some entries

16

of a data object. Here rt$duration[which(rt$gender=="men")] tells R choose all of the durations for which rt$gender is men. In the second panel, we use similar code to show visits to the women’s restroom.

This might seem like a lot to memorise, and it would be. Remember though, you do not need to memorise it! You can look it up when you need it.

At this point, you may be thinking that making figures in R is more cumbersome than in some point-and-click programmes like Prism, SPSS, or even Excel that you may have used in the past. I agree! But, the advantage is that, with experience and a bit of tinkering, you can control figures in R much more precisely than you can control figures in these other programmes. This is important in Science, where precise figures can be critical to effectively communicating your results.

Making figures, and indeed writing any code, can be complicated. It may take several tries to get your code working exactly the way you want. So, while you can always enter code directly into the R console, you may find it easier to write your code in a scripting window. A scripting window is essentially a word processor for your R code. You can write your code, edit it, fix typos, and then send it to the R console to be executed. If it doesn’t work as expected, you can edit it in the scripting window and then execute it again. You can also save R scripts to be used or modified later. Researchers often invest time in making good figures once, and then use those codes with small modifications throughout their careers.

If you want to work in a scripting window, you can open one from the “File” menu in either RStudio or native R. Depending on your version of R, choose either “New Script” or “New Document” – they mean the same thing.

#### **Approach 1. The Monte Carlo method**

From a casual observation of figure 2.3, it looks like the men’s and women’s restrooms at Rivertown Crossings Mall may be used differently. But, Science requires more than casual observations. Science requires evidence. So, how do we formally test the hypothesis that the two restrooms are used differently?

Before we can test a hypothesis, we need to make sure it is precisely stated. For example, what do we mean by “differently?” There are many ways that restroom use might be different. We might be interested in the median visit durations. Or, we might want to compare the variance in the duration of visits to the two restroom types. But often, it is most interesting and useful to compare population means. So, let’s state our hypothesis as “The mean visit duration to the men’s restroom is different from the mean visit duration to the women’s restroom.”

17

We can start by simply looking at the means of the two groups. The command

mean(rt$duration[which(rt$gender=="women")])

[1]  133.78

gives us the mean visit duration to the women’s restroom in the study. Recall that the part in parentheses, rt$duration[which(rt$gender=="women")], selects the duration data for observations where the gender of restroom visited is “women.” The mean visit duration to the women’s restroom was 133.78 s.  Using the analogous command, we find that the mean visit duration to the men’s restroom was 106.16 s. So, the mean visit duration to the women’s restroom was 27.63 s longer than the mean visit duration to the men’s restroom.

But, what does this really tell us? If we divide restroom users into groups in any way, for example by birth month or shirt colour, we will certainly find some differences in visit duration among the groups. Presumably restroom visit duration does not _depend_ on birth month or shirt colour – these differences would be due to chance variation among individual visits or visitors rather than to any real differences among the groups. But, we want to know whether the difference between visit durations to the restroom types is due to something more than chance – that is, if there is some real difference in the behaviour of the visitors. So, a reasonable question to ask is “What is the probability that we would have observed a difference as large as 27.63 s in a random sample if there were really no difference in the times people spend in the two restroom types?” The statement that there is no difference in the time people spend in the two restroom types is called the _null hypothesis_ . If we would be very unlikely to see a difference as large as the observed difference in a random sample if the null hypothesis were true, then we infer that the null hypothesis is probably false. That is, we infer that people really do use the restroom types in different ways.

This brings us to the fundamental question of frequentist hypothesis testing:

#### **_What is the probability that we would obtain a result at least as extreme as the one in our observed data by chance alone?_**

All of the statistical analyses that we will study in the remainder of this handbook are concerned with answering this question. I have argued that we do not need to memorise statistical methods because we can look them up when we need them. But, if you are going to memorise something from this handbook, it should be this question!

Perhaps the most intuitive way to address our question is with an approach called the _Monte Carlo method_ . Consider the subset of the restroom data shown in the table on the left in figure 2.4 (next page). For the first data point, the duration of the visit was 93 s and the visit was to the women’s restroom. But, if there were really _no difference_ in the way that people use the

18

<!-- Start of picture text -->
duration  gender  duration  gender<br>93  women  124  women<br>183  women 62  women<br>124  women 78  women<br>214  women 59  women<br>122  women 183  women<br>78  women 69  women<br>186  women 60  women<br>110  men  186  men<br>60  men 86  men<br>62  men 93  men<br>59  men 214  men<br>45  men 45  men<br>86  men 116  men<br>116  men 122  men<br><!-- End of picture text -->

restroom types, then there is no reason that this visit _had_ to have been to the women’s restroom. It could just as easily have been to the men’s restroom. And, the same is true for every other visit in the data set. So, if people use the restroom types the same way, then any rearrangement of the observed durations among the restroom types would be just as likely as the one we saw. For any possible rearrangement, we can ask what the difference in visit time to the restroom types would have been. This would be one example of a difference that we might have seen by chance alone.

**Figure 2.4** . **One alternative realisation of the restroom use data.** The table on the left shows a subset of the restroom use data. The table on the right shows an alternative realisation of the same data. All of the same data exists, but durations have been randomly reassigned among visits. The black arrow shows where one value was reassigned.

The table on the right in figure value was reassigned. 2.4 shows one rearrangement of our subset of the duration data. In practice of course, we want to rearrange all of the duration data. That table would have 97 rows and would be too big to show here. However, we can easily make such a rearrangement in R with the command

samp1=sample(rt$duration,length(rt$duration),replace=F)

Here, sample(rt$duration,… tells R to choose values at random from the duration data. The next argument, length(rt$duration), tells R how many values to choose. length(rt$duration) returns the number of entries in the vector rt$duration. So, code 2.7 tells R to choose the same number of values as are in the original duration data. replace=F tells R to sample without replacement. That means R will not choose the same value from rt$duration more than once. Thus, samp1 is a new vector that includes all of the values that were in rt$duration, each chosen once, but in a different order. We call this a _permutation_ of the duration data.

We can calculate the difference in visit times to the men’s and women’s restrooms in this permutation of the duration data using the same method we used above. The mean duration of visits to the men’s restroom is

mean(samp1[which(rt$gender=="men")])

[1]  118.57

and the mean duration of visits to the women’s restroom is

mean(samp1[which(rt$gender=="women")])

[1]  120.02

19

<!-- Start of picture text -->
Figure 2.5. Histogram<br>of the differences in the<br>mean visit durations to<br>the men’s and women’s<br>**** restrooms in six<br>random permutations<br>of the duration data.<br>-30 -20 -10 0 10 20 30 The * represents the<br>difference in the<br>differences in permutations observed data.<br>2.0<br>1.0<br>Frequency<br>0.0<br><!-- End of picture text -->

We get the difference by subtracting. When I did this the first time, I got means of 120.02 s for the women’s restroom and 118.57 s for the men’s restroom, so the difference was 1.45 s. I created five new permutations and found differences of 6.75 s, 18.07 s, 3.60 s, -8.76 s, and 9.18 s.

Let’s visualise the result so far.  Figure 2.5 shows the differences between visit durations to the men’s and women’s restrooms that I obtained in my first six permutations of the duration data. From this, it looks like differences as large as 27.63 s are not common. But, six permutations is not enough to be sure.  To be sure, we might want to look at 10,000 or 100,000 permutations. We can make R create those by inserting the commands we just used into a _for loop_ .

difs=numeric() for (i in 1:100000) { samp=sample(rt$duration,length(rt$duration),replace=F) mean_womens=mean(samp[which(rt$gender=="women")]) mean_mens=mean(samp[which(rt$gender=="men")]) samp_dif=mean_womens-mean_mens difs=c(difs,samp_dif) }

Again, it is easiest to understand this code if we consider it line-by-line. The first four lines in the curly brackets are the commands we have already used to find the difference in visit durations to the restroom types in a random permutation of the data. The command for (i in 1:100000) tells R to repeat the code in the curly brackets 100,000 times. The variable difs is new. It will store the differences we find in our permutations. The command difs=numeric() creates an empty vector called difs. That is, it creates a variable named difs that will be a vector but that has no entries when it is created. Every time R repeats the for loop, the command c(difs,samp_dif) adds one entry to the vector difs. The value of that entry is samp_dif, the difference between visit times to the women’s and men’s restrooms in the most recent permutation of the duration data. When R is finished, difs is a list of 100,000 examples of differences between the mean visit durations to the restroom types that we obtained by chance alone. Figure 2.6 on the next page shows a histogram of those differences.

20

<!-- Start of picture text -->
Figure 2.6. Histogram of<br>the differences in visit<br>durations to the women’s<br>and men’s restroom in<br>10 5  permutations of the<br>observed data.  Red<br>-60 -40 -20 0 20 40 60 indicates differences<br>simulated differences between men’s and women’s restroom visit  greater than the observed<br>difference between female and male restroom visit duration<br>durations (in seconds)  difference.<br>Frequency 1000<br>0<br><!-- End of picture text -->

Recall the question we are trying to answer: what is the probability that we would see a difference between visit durations to the two restroom types at least as large as the difference we observed in the real data (here, 27.63 s) simply due to chance? In figure 2.6, differences shown in red are at least as great as those in the observed data. We can count the differences in the lower (lefthand) tail with

lower_tail=sum(difs<=-27.63)

and in the upper (right-hand) tail with

upper_tail1=sum(difs>=27.63)

Like the “==” operator we saw earlier, the “<=” and “>=” operators are _logicals_ . Here, they make new vectors with the same size as difs, but where each entry is TRUE if the inequality is true and FALSE if it is false. The command sum(…) totals up the entries of those vectors. If we ask R to do maths with logicals, it treats TRUE as 1 and FALSE as 0. So, the new variable lower_tail tells us how many of our permutations had differences less than or equal to -27.63 s, and the new variable upper_tail tells us how many of our permutations had differences greater than or equal to 27.63 s. To turn these into proportions, we can divide them by the total number of permutations we made, in this case 100,000. When I did this, the lower tail contained a proportion 0.02734 of the differences, and the upper tail contained a proportion 0.02918 of the differences. Together, both tails contained a proportion 0.05652 of the differences.

So, in our random permutations, the probability of obtaining a difference at least as large as the difference in the observed data was 0.05652. We call this number a _p-value_ , and it is the answer to our question. But, what does this p- value tell us about our hypothesis? By convention, we say that a p-value below 0.05 provides _statistically significant evidence_ for our research hypothesis. If the p-value is less than 0.05, the observed pattern is unlikely to have occurred by chance, our null hypothesis can be rejected, and our research hypothesis is likely to be true. However, the 0.05 cut-off for statistical significance is arbitrary. In reality, p-values are a continuous measure of the strength of evidence in our data. A p-value of 0.05 provides only slightly stronger evidence than the p-value of 0.0562 that we obtained. For this reason, may researchers consider p-values between 0.05 and 0.10 to be weakly significant evidence for the research hypothesis. If the p-value is higher than 0.10, most researchers believe there is

21

not sufficient evidence to reject the null hypothesis, and thus that the data does not provide evidence for the research hypothesis.

Misinterpreting p-values is a common error for early-career researchers. So, it is important to stop for a moment to think carefully about what p-values _do not_ mean:

1. **A low p-value does not** **_prove_ your research hypothesis** . Your results can provide evidence for your research hypothesis, and that evidence may be strong, but even strong evidence is not proof. By analogy, imagine that you walk into a room, and on a table you see ten pennies, all on heads. You might conclude that someone arranged them that way. Indeed, the probability that all ten coins would show the same face just by chance ( _i.e_ ., the p-value for testing whether the coins fell at random) is <0.002. Nonetheless, the coins _might_ have fallen at random. So, you have evidence, but not proof. This can be confusing for the non-scientific public, who often think that because scientists avoid words like “proof,” our evidence is weaker than it really is.

2. **A high p-value does not provide evidence for the null hypothesis, and it does not allow you to reject the research hypothesis** . A high p- value means that you _could have_ obtained the observed results by chance, but it does not mean you _did_ obtain them by chance. Consider the coin analogy again. Imagine that, among the pennies on the table, six show heads and four show tails. The probability that at least six coins would show the same face by chance is 0.7539. So, you have no reason to believe that someone placed the coins in a particular way. However, you have no evidence that _no one_ placed the coins. So, you cannot reject the hypothesis that the coins were placed.

Finally, when you report the results of your analysis, it is important to remember that a p-value by itself is not enough. If you find evidence for an effect, you should also report the effect size. For example, in our restroom visit data, we have weak evidence that people spent more time in the women’s restroom than in the men’s. We infer that, in the population as a whole, visit times to the two restroom types differ. But, this is not very useful unless we also know _by how much_ they differ. The best estimate for the difference is the observed difference, 27.63 s. So, we might report “People who entered the women’s restroom in our study spent 27.63 s longer on their visits than people who entered the men’s restroom. This difference was marginally significant (p = 0.05652).”

#### **One-tailed and two-tailed hypothesis tests**

Hypothesis tests like the one above can be _one-tailed_ or _two-tailed_ . Which type of test we should use depends on our hypothesis.

In the example above, our research hypothesis was that the mean restroom visit duration differs between the two restroom types. Our null hypothesis was that the mean visit durations do not differ. The observed

22

difference was 27.63 s. Our p-value is the probability that we would see data that appears to support the research hypothesis at least as strongly as the observed data does, _if the null hypothesis were true_ . There are two ways that random permutations could result in differences at least as great as the one we observed in the data: either visits to the women’s restroom could be longer than visits to the men’s by at least 27.63 s (as in the upper tail of figure 2.6) or visits to the men’s restroom could be longer than visits to the women’s restroom by at least 27.63 s (as in the lower tail of figure 2.6). We added these two tails together to obtain our p-value of 0.05652.

The situation would have been different if we had started our study with an _a priori_ expectation. For example, we might have expected that visits to the women’s restroom would be longer than visits to the men’s. Then, our research hypothesis would have been “Visits to the women’s restroom have a longer mean duration than visits to the men’s,” and our null hypothesis would have been “Visits to the women’s restroom _do not_ have a longer mean duration than visits to the men’s.” When we computed our p-value, we would not be interested in permutations where visits to the men’s restroom were longer than visits to the women’s. Those permutations do not appear to support our research hypothesis by chance alone. Instead, we would be interested only in permutations where the mean visit duration to the women’s restroom was longer than the mean visit duration to the men’s restroom by at least 27.63 s ( _i.e_ ., the upper tail of figure 2.6). So, we would compute a one-tailed p-value of 0.02918.

This example illustrates an important point in hypothesis testing. Hypotheses generated with _a priori_ knowledge result in lower p-values than hypotheses generated without _a priori_ knowledge. However, we cannot use the same data to generate a hypothesis that we will later use to test it. For example, it would have been wrong to look at the histograms in figure 2.3, observe that women seem to have longer restroom visit durations than men, and then use the same data to test the hypothesis.

To understand why this is so, imagine that we are studying a case where the null hypothesis is true (or at least very, very close to true – we could argue about whether a null hypothesis is ever _really_ true). An example might be men’s and women’s IQs: researchers have not found a consistent difference between the mean IQs of men and women in the general public. If we sample 20 men and 20 women, we will observe some difference in the mean IQs of the genders due to chance alone. In our sample, the IQs of men might be higher or the IQs of women might be higher. For the purpose of illustration, imagine that women have the higher IQs in our sample. Now, imagine that we look at this difference and use it to generate the hypothesis “The mean IQ of women is higher than the mean IQ of men in the population from which our sample was drawn.” Then, we use the Monte Carlo method to generate a distribution of differences that we _might_ have seen by chance (as in figure 2.6). If we use a one-tailed test, we are asking if the observed difference between women’s and men’s IQs is in the top 5% of the values we obtained by permutation. But, we already know that it is in the top 50%, or we wouldn’t be testing this hypothesis! So, our probability of inferring a significant difference would be 5% divided by 50%, or 0.10. That

23

means that, by using the same data to form and then to test our hypothesis, we overestimate the strength of our evidence.

#### **Approach 2. The t-test**

The Monte Carlo approach is a powerful and accurate way of computing p-values. However, it is computationally demanding. If you ran code 2.10 above, it probably took more than a minute to run. Before we had modern computers, the Monte Carlo approach could take days or weeks to compute a p-value. Researchers needed an approach that was faster but still reasonably accurate.

A solution to this problem was developed by William Sealy Gosset (figure 2.7), a chemist and statistician at the Guinness brewery in Dublin. Gosset worked under the pseudonym Student, because Guinness prohibited its employees from publishing work that might be useful to its competitors. Gosset was interested in comparing the yields of different barley varieties based on samples of each variety. The problem is analogous to our restroom visit problem, where we were interested in comparing the mean visit durations to women’s and men’s restrooms based on a sample of people who visited those restrooms. Gosset noticed that, under certain conditions, the distribution of differences in means that we can observe by chance (that is, the distribution shown in figure 2.6) is predictable. We can describe this

**Figure 2.7. William Sealy Gosset (Student)**

distribution if we know just two things about our sample: the variance (which tells us how different the individual observations are) and the sample size (the number of observations in our sample). We can compute these values directly from the sample itself. If we compute the distribution of possible differences in this way, then we can calculate the proportion of the distribution with values larger than our observed difference (that is, in the tails), and thus we can calculate the p-value for the observed difference. So, there is no need to create simulated distributions. The predictable distribution that Gosset discovered is called a _t-distribution_ , and tests based on this distribution are called _t-tests_ .

There are two main types of t-tests, and which one we use depends on the hypothesis we are testing. The _two-sample t-test_ asks whether the means of two populations are different. This is analogous to our restroom example, where we asked whether the mean visit duration was different for two restroom types. The _one-sample t-test_ asks whether the mean of a single population is different from some value of interest. For example, if we wanted to know whether the mean visit duration to the women’s restroom is longer than 2 minutes, we would use a one-sample t-test.

People often talk about a test called the _paired t-test_ . This test is used if the research question is not about the means of two populations as a whole, but

24

rather about the difference between members of two populations that can be paired in some way. For example, perhaps we are not interested in whether visit durations depend on the gender of the restroom, but rather whether restroom visit durations by husbands are different from those of their wives. This might be a sensible question to ask if we expect that visit durations by members of couples are correlated. For example, perhaps people spend longer in the restroom if they think that their partner will spend a long time, so if they come out quickly themselves they will have to stand around waiting. To study this, we would record visit durations for opposite-gendered couples, where each man’s visit would be paired with a specific woman’s visit. In practice, the paired t-test is really just a special case of the one-sample t-test. The sampling unit is the pair (in our example, the couple), and our response variable is the difference between members of the pair ( _e.g_ ., the man’s visit duration minus the woman’s visit duration). To find out whether husbands have different restroom visit durations than their wives, we calculate the differences within couples, and then conduct a one-sample t-test to find out if the mean within-couple difference is significantly different from zero.

Conducting t-tests in R is easy. In general, if we want to measure the evidence that the populations represented by samples a and b have different means, we can use the code

t.test(a,b)

For example, to ask whether restroom visit durations differed between the restroom types at the Rivertown Crossings Mall, we can use

> w.dur=rt$duration[which(rt$gender=="women")] (2.14) m.dur=rt$duration[which(rt$gender=="men")] t.test(w.dur,m.dur)

Here w.dur=rt$duration[which(rt$gender=="women")] creates a vector called w.dur that contains the durations of all visits to the women’s restroom from the date frame rt, and m.dur=rt$duration[which(rt$gender=="men")] creates a similar vector of all visits to the men’s restroom. The code t.test(w.dur,m.dur) compares the groups. When you run the code, you will get the following output

t.test(w.dur,m.dur)

Welch Two Sample t-test

data:  w.dur and m.dur t = 1.9535, df = 92.973, p-value = 0.05377 alternative hypothesis: true difference in means is not equal to 0 95 percent confidence interval: -0.4573838 55.7088757 sample estimates: mean of x   mean of y 133.7826    106.1569

25

Here, R reports that it has applied a Welch Two Sample t-test. Welch’s t-test is a modification to Student’s t-test that can be used when one group is more variable than the data for the other.

There are several important pieces of information in output 2.15. Perhaps the most important is the p-value. Recall that the p-value is the probability that we would see a result as extreme as in the observed data by chance alone if the null hypothesis were true. Using the Monte Carlo approach, we obtained a p- value of 0.05652. Using a t-test we get 0.05377, which is very similar. We are asking the same question from the two approaches, so it should not surprise us that we get similar answers!

The value df stands for _degrees of freedom_ . Degrees of freedom increases with the sample size, and describes the shape of the t-distribution. If df is large, the t-distribution is close to the classic normal distribution. If df is small, the t- distribution has “fat tails.” We call this leptokurtosis. A fat-tailed t-distribution includes more extreme values, and this means that the p-value will be higher. This reflects the fact that we have less confidence in estimates derived from small samples. The value t is the _t-statistic_ . The t-statistic indicates how far the observed value is from the null expectation. Here, the null hypothesis is that visit durations do not differ between the restroom types, so the null expectation for the difference is zero. The t-statistic is scaled to the standard deviation of the observed data. So, a t-statistic of 2 means that the observed means of the groups differ by an amount equal to two standard deviations of the observed data. In general, higher t-statistics indicate larger differences between the groups, and thus lower p-values. In practice, R uses the degrees of freedom and the t-statistic to compute the p-value, and you will seldom use these values yourself. Nonetheless, some journals require authors to report them.

The _95% confidence interval_ has a somewhat difficult interpretation. Imagine that we could draw a new sample from a population with properties similar to those in our observed data. That is, men and women in the source population would differ by the same amount as in our observed data, and the variability within men and women in the source population would be the same as in our observed data. Imagine also that the new sample has the same size as our original sample. Then, there would be a 95% chance that the observed difference between men and women in our new sample would fall within the 95% confidence interval. The 95% confidence interval does _not_ mean that we are 95% sure the true value falls in this range. Nonetheless, people often use it as a rough surrogate for the range of in which the true value might plausibly fall.

Finally, the means at the end of the output above are simply the means for visits to the women’s and men’s restrooms, respectively. These are the same values we calculated directly using code 2.6.

By default, the command t.test applies a two-tailed, two-sample t-test. If we want to conduct a one-tailed test (where our hypothesis was generated before we looked at the data!), we can add alternative="less" or alternative="greater" to the command. For example,

26

(2.16)

t.test(w.dur,m.dur,alternative="greater")

tests the hypothesis that the first group (visits to the women’s restroom) had a greater mean duration than the second group (visits to the men’s restroom). If we want to ask whether the restroom visit duration for a group differs from some value of interest ( _i.e_ ., a one-sample t-test), we can use the syntax

t.test(v,mu=x)

where v is the vector of values we want to test, and x is the value of interest. For example, to ask if the mean time visitors spent in the women’s restroom was greater that 120 s, we could use

t.test(w.dur,mu=120,alternative= "greater")

#### **Reporting results**

When reporting results, the goal is to be clear and concise. For the analysis in code 2.15, we might say

“We found weak evidence that visits to the women’s restroom were longer than visits to the men’s restroom (134 s vs 106 s; Welch’s t-test, t = 1.95, df = 92.97, p = 0.054).”

This gives the reader all of the information they need in a single sentence. The reader knows the means for each group and the p-value associated with the difference between the means. The test we used should have been reported in the methods, but we have reminded the reader here. The reader also knows the t-statistic and the degrees of freedom. They are unlikely to need these, but many journals require them to be reported. We have not reported all of the decimal places for any of the values we reported. Remember that these are estimates of population values based on a small sample. It is unlikely that they are accurate to four decimal places! There is no universal rule about how many decimal places or significant figures to report, so we need to think about what is useful for readers and required by journals. Finally, we have claimed that we found “weak evidence” for a difference between the genders in restroom visit duration. This is because our p-value is below 0.1, but not below the commonly accepted 0.05 threshold for statistical significance. Scientists quibble about where the cut-offs for “evidence” and “weak evidence” should be, but if we present an accurate p-value, readers can assess the strength of the evidence for themselves.

A good figure can help readers understand our results, so we will want to support the most important results of our work with figures. R gives us very precise control over figures, but that comes at a price – making figures in R is not as simple as the point-and-click methods in some other data handling programmes. There is nothing to prevent you from analysing your data in R and making your figures with a different programme, and some people do that. But, if you stay in Science, you will probably make a lot of figures during your career,

27

and you will want them to be perfect. So, it is worth investing the time to learn to make figures in R.

One intuitive figure for presenting the results of a t-test is a bar chart. Let’s walk through the process of making a bar chart in R step-by-step. We want our bar chart to show the means of the groups we are studying. In this case, we are studying the mean visit durations to the men’s and women’s restrooms. We can calculate those means with

men_mean=mean(rt$duration[which(rt$gender=="men")]) women_mean=mean(rt$duration[which(rt$gender=="women")])

This stores the mean visit durations to the men’s and women’s restrooms as men_mean and women_mean, respectively. To create a bar chart, we can use

barheights=c(mens_mean,womens_mean) lbls=c("men’s","women’s") bp=barplot(barheights,names=lbls, ylab="restroom visit duration in seconds",ylim=c(0,160))

Here, the first line combines the means for men and women into a single vector, and names that vector barheights. The second line creates the labels men’s and women’s that we will use for our bars, and stores them in a list called lbls. Finally, the command barplot creates the plot. The first argument is the vector of bar heights, and the second is the list of names for the bars. The text ylab="restroom visit duration in seconds" tells R how to label the _y_ -axis. The text ylim=c(0,160)) tells R that the y-axis should run from 0 to 160. If we leave this out, R will choose the axis limits itself, and we may not like its choice. In addition to creating a figure, the command barplot outputs the locations of the bars on the _x_ -axis. We have stored this information as bp because it will be useful to us later.

<!-- Start of picture text -->
y -axis.<br>Figure 2.8 .  Mean visit durations<br><!-- End of picture text -->

We could stop here, but most readers like to see standard error bars on bar plots (figure 2.8). The reason is that the means we are reporting are only estimates. For example, we are estimating the mean visit duration to the men’s restroom at Rivertown Crossings Mall based on a sample of just some of the restroom visitors. The standard error measures our confidence that the true mean of the population is close to the observed mean in our sample. Mathematically, standard error is the standard deviation divided by the square root of the sample size. We can calculate the standard errors for the visit durations to each restroom using

**Figure 2.8** . **Mean visit durations to the men’s (n = 51) and women’s (n = 46) restrooms at Rivertown Crossings Mall in November of 2003.** Error bars show one standard error.

28

men_sd=sd(rt$duration[which(rt$gender=="men")]) men_samp_size=length(rt$duration[which(rt$gender=="men")]) men_se=men_sd/sqrt(men_samp_size)

women_sd=sd(rt$duration[which(rt$gender=="women")]) women_samp_size=length(rt$duration[which(rt$gender=="women")]) women_se=women_sd/sqrt(women_samp_size)

Here, the command sd(…) takes the standard deviation of the sample, and length(…) counts the number of entries in the sample vector ( _i.e_ .,  the sample size). The command sqrt(…) takes the square root of its argument. Thus, men_se and women_se are the standard errors for the visit durations to the men’s and women’s restrooms, respectively.

Finally, we can use the values we have calculated to add standard error bars to our bar chart. We will add the error bars by hand using the command segments. The command segments(a,b,c,d) draws a line from point (a,b)  to point (c,d). Here, a and c are the _x_ -coordinates and b and d are the _y_ -coordinates for each point. We can take the _x_ -coordiantes from the vector bp we created above, and calculate the y-coordinates.

segments(bp[1],men_mean-men_se,bp[1],men_mean+men_se) segments(bp[2],women_mean-women_se, bp[2],women_mean+women_se)

So, the error bar for the duration of visits to the men’s restroom is placed at the centre of the first bar on the _x_ -axis ( _i.e_ ., at bp[1]), and stretches from the mean minus the standard error ( _i.e_ ., men_mean-men_se) to the mean plus the standard error ( _i.e_ ., men_mean+men_se). The error bar for the duration of visits to the women’s restroom is analogous.

##### **women**

#### **The normality assumption**

Earlier in this section, we observed that t-tests work under certain conditions, but we did not specify what those conditions are. In general, t-tests assume that the response variable follows a normal distribution in each of the groups that we are comparing. Real data does not always meet this assumption. For example, figure 2.9 shows the number of lifetime car accidents for 50 women and 50 men among the students at Hope College in Holland, Michigan. The number of students in each bin decreases monotonically. Moreover, the number of car accidents per student is a discrete variable, and normal distributions are continuous. So, accident numbers are not normally distributed, and a t-test may not be a reliable way to compare the mean accident numbers in this data.

<!-- Start of picture text -->
0 1 2 3 4 5<br>car accidents<br>men<br>0 1 2 3 4 5<br>car accidents<br>30<br>15<br>frequency<br>0<br>30<br>15<br>frequency<br>0<br><!-- End of picture text -->

<!-- Start of picture text -->
Figure 2.9 .  Number of lifetime car<br>accidents for 50 women (top) and<br>50 men (bottom) students at<br>Hope College.<br><!-- End of picture text -->

**Figure 2.9** . **Number of lifetime car accidents for 50 women (top) and 50 men (bottom) students at Hope College.**

29

When the question they want to answer is difficult, scientists often answer an easier question instead. In this case, it is difficult to study the difference in the mean number of car accidents for men and women at Hope College. It is easier to study the difference in the mean ranks of the accident numbers for students of each gender. The test we use to do this is called a _Wilcoxon test_ . The _Mann-Whitney U test_ that you may have encountered in other units is a special case of the Wilcoxon test.

The Wilcoxon test relies on the idea that we can rank our data points according to the value of the response variable. We assign the lowest rank to the lowest value of the response. If we have identical responses, then those responses receive the same rank. For example, if the responses for a set of seven data points were {1.5, 3, 17, 3, 0.9, -7, 14}, then the ranks would be {3, 4, 7, 4, 2, 1, 6}. Each ranked data point is associated with a predictor. In the car accident data, this predictor is the gender of the driver. So, we can ask, “What is the probability that one gender would have a mean rank at least as low as in the observed data by chance alone if the null hypothesis were true (that is, if there were no true relationship between gender and rank)?” As for the t-test, the answer to this question is a p-value. However, unlike the t-test, the Wilcoxon p-value can be computed for any data set, regardless of the distribution of the responses.

Conducting a Wilcoxon test in R is similar to conducting a t-test. To measure the evidence that men and women at Hope College have different numbers of car accidents, we can import the data from the Dropbox folder using:

hc=read.csv("Hope_College.csv",header=TRUE)

and examine it using

> head(hc)

|accidents gender|
|---|
|1         0      w|
|2         0      w|
|3         0      w|
|4         0      w|
|5         0      w|
|6         0      w|

We can conduct a Wilcoxon test using

> acc.w=hc$accidents[which(hc$gender=="w")] (2.25) acc.m=hc$accidents[which(hc$gender=="m")] wilcox.test(acc.w,acc.m,data=hc)

Notice that in this code we have used which(hc$gender=="w") rather than which(hc$gender=="women"). This is because gender in this data set is coded with w and m rather than with women and men. If you run this code, you will find a

30

p-value of 0.12. So, we do not have evidence that men and women are involved in different numbers of car accidents.

Some people believe that the Wilcoxon test is simply an alternative to the t-test that can be used when the data we are interested in are not normally distributed. This is incorrect. Wilcoxon tests and t-tests answer different questions. A t-test asks whether two populations have different means. A Wilcoxon test asks whether two populations have different mean ranks. To understand the difference, imagine that we have a box of lottery balls, where half are red and half are white. Among the red balls, half bear the number 1, and the other half bear the number 10. All white balls bear the number 2. The mean number on the red balls is (1 + 10)/2 = 5.5, and the mean number on the white balls is 2. However, for every white ball, there are exactly as many red balls with higher numbers as there are with lower numbers. So, the mean rank of the white balls is exactly the same as the mean rank for the population, which must also be exactly the mean rank for the red balls. That is, the mean numbers on the white and red balls are different, but the mean ranks of the white and red balls are exactly the same. If we used a t-test and a Wilcoxon test to compare these populations, they would give us different answers.

So, how should we decide whether to use a t-test or a Wilcoxon test? We can follow this set of rules:

1. If you are interested in mean ranks, you will need a Wilcoxon test. One case where you might be interested in mean ranks is if your response variable is ordinal ( _e.g_ ., responses on the Likert scale). Recall from the previous chapter that ordinal data can be ranked, but they are not numerical. For ordinal data, it is not clear what the mean really tells us, and a mean rank may be an informative measure.

2. If you are interested in mean values and your data are approximately normally distributed, you will need a t-test.

3. If you are interested in mean values and your data are not normally distributed, but if the deviation from normality is not too extreme, you may be able to use a t-test anyway. Often, t-tests are robust to small deviations from normality. In this case though, when you report your results, you should warn your reader that your data are not normally distributed, and you should interpret your p-values conservatively. For example, if you obtain a p-value of 0.04, you might consider this only weak evidence for a difference in the means of the two groups.

4. If your data are clearly not normally distributed, and if a mean rank is good enough to answer your biological question, then a Wilcoxon test may be a good option.

Finally, what if your data are clearly not normally distributed, but you are interested in comparing population means, and comparing mean ranks will not be good enough? In this case, neither a t-test nor a Wilcoxon test is appropriate.

31

However, if you are willing to write a few lines of code, you can use the Monte Carlo approach that we have already discussed. In the Monte Carlo approach, we tested the possibility that two samples were drawn from the same distribution, but we did not assume anything about what that distribution looks like. So, we can apply the Monte Carlo approach regardless of whether our data is normally distributed.

32

### **Chapter 3. Comparing the means of more than two groups**

In the previous chapter, we studied methods to ask whether the means of two groups are different. Sometimes however, we might want to compare the means of more than two groups. For example, we might have three genotypes of a flowering plant species, and we might want to know which one attracts the most bees.

One naïve way to approach this problem would be to make a series of pairwise comparisons. If we have genotypes A, B, and C, we might ask if the mean number of bees per hour attracted by genotype A is different from that of genotype B, and then if B is different from C, and is C is different from A.

However, there is a problem with this approach. Imagine that there were really no difference among plant genotypes in attractiveness to bees. If we sample flowers with genotypes A and B from the population and compare them with a t-test, what is probability that we would infer a difference even if no true difference exists? Remember that a p-value is the probability that we would obtain a result as extreme as the one in the observed data if the null hypothesis were true. So, if we set our arbitrary cut-off for significance at p = 0.05, then if the null hypothesis is true, the probability of inferring a significant difference by chance alone is 0.05. That is, in 5% of studies the difference between groups in our sample will be large enough that we will believe it is real, even though there is no difference between the groups in the full population. This is called the _false positive rate_ , or the _type I error rate_ , and it is often denoted with the variable _α_ . By setting our cut-off at 0.05, we are deciding that this false positive rate is low enough that we can call results this strong or stronger “evidence.” Now, imagine that we add genotype C to our analysis. We already have a 5% chance of incorrectly inferring a difference between genotypes A and B. Now, there is some additional probability that genotype C might appear different from A or from B by chance alone. So, by adding a genotype, we increase the probability of inferring an effect where no real effect exists. If we consider a very large number of genotypes, say 100, we are almost certain to infer a significant difference between some at least pair of genotypes even if the flowers of every genotype are in reality absolutely identical. This problem is called _multiple testing_ , because it arises when we make multiple comparisons within the same data set.

R. A. Fisher introduced a solution to this problem. His method, called _analysis of variance_ or _ANOVA_ , works by comparing the variability explained by the groups ( _i.e_ ., variability among groups) to the unexplained variability in the data ( _i.e_ ., the variability within groups). If there is more variability among groups than within them, then differences among groups are unlikely to be due to chance, and there are likely to be real differences in the group means in the population.

33

<!-- Start of picture text -->
SD = 4.0 SD = 0.5<br>0 5 10 15 20 25 0 5 10 15 20 25<br>0 5 10 15 20 25 0 5 10 15 20 25<br>0 5 10 15 20 25 0 5 10 15 20 25<br>4 4<br>2 2<br>0 0<br>4 4<br>2 2<br>Frequency 0 0<br>4 4<br>2 2<br>0 0<br><!-- End of picture text -->

**Figure 3.1. Three samples drawn from the same distribution (left), and three samples with the same means as the corresponding let-hand panels but drawn from distributions with reduced variability (right).** On the left, we have no reason to believe that the samples came from different distributions (p = 0.70). Samples on the right are very unlikely to have come from the same distribution (p = 7.52 x 10<sup>-16</sup> ). SD is the standard deviation of the source distribution in each column.

Figure 3.1 illustrates this idea. The samples shown in the panels on the left and right in each row have the same means (16.0, 17.9, and 15.3 from top to bottom). However, the variability within samples is greater on the left. Intuitively, you might think that the samples on the left were all drawn from the same distribution. If so, you would be correct – that is how I generated them. In contrast, the samples on the right seem to be different. For example, every observation in the middle panel is greater than every observation in the bottom panel. If your intuition says these samples are from different distributions, then you are right again. In fact, the probability of seeing a difference this large difference _among_ groups when there is so little variability _within_ them just by chance alone is 7.52 x 10<sup>-16</sup> !

#### **Working through an ANOVA**

The easiest way to understand ANOVA is to consider an example. We will use the data set chickwts that comes preloaded into R. These data report the masses of chicks ( _Gallus gallus_ ) fed for six weeks on each of six different diets. (The authors have sloppily named the response variable weight, but the measurements are in grams and so are certainly masses not weights!) To see the chickwts data, simply type chickwts into the R console

##### chickwts

weight      feed 1     179 horsebean 2     160 horsebean 3     136 horsebean 4     227 horsebean 5     217 horsebean 6     168 horsebean

…

34

<!-- Start of picture text -->
casein horsebean linseed meatmeal soybean sunflower<br>400<br>300<br>grams<br>200<br>100<br><!-- End of picture text -->

**Figure 3.2.** On the left, a box-and-whiskers plot of the mass of six-week old chicks raised on each of six experimental diets. Data are from the dataset chickwts in the R datasets package. On the right, John Tukey, inventor of the box-and-whiskers plot.

We can visualise the chickwts data using a _box-and-whiskers_ plot

boxplot(weight~feed,data=chickwts,ylab="grams")

(figure 3.2). Here, the text weight~feed tells R to plot mass on the _y_ -axis and feed types on the _x_ -axis. This use of the character ~, called a tilde, is very common syntax in R. The variable to the left of the tilde is the response, and the variable to the right is the predictor. The tilde itself can be read as “depends on.” We will see this syntax again and again in this handbook.

Box-and-whiskers plots were introduced by American statistician John Tukey. The dark line in each box represents the median value for the group, and the bottom and top of each box represent the 25<sup>th</sup> and 75<sup>th</sup> percentiles. The whiskers extend up to 1.5 times farther than the 25<sup>th</sup> (bottom) and 75<sup>th</sup> (top) percentiles, but stop at the last data point if it is within that limit. If there are additional data points beyond the ends of the whiskers, these are shown as circles.

From a glance at figure 3.2, it looks like growth differs for chicks with different diets. For example, chicks raised on horsebean seem to be smaller than chicks raised on casein or sunflower seeds. But, let’s analyse this formally by studying the variability within and among the groups.

The measure of variability that we will focus on is called the _sum of squared deviation_ . In general, the mean across all individuals measured in a study is called the _grand mean_ . The grand mean mass of chicks from all six feed groups in our study is

mean(chickwts$weight)

[1] 261.3099

No individual chick in the study has exactly this mass. Instead, each chick’s mass is the grand mean plus some positive or negative difference that we call _deviation_

35

from the mean. We can calculate the deviation for each individual chick by subtracting the grand mean from the individual weights

dev_tot=chickwts$weight-mean(chickwts$weight)

To find the squared deviation, we square these values. Then, to find the sum of squared deviation for the population, we simply sum these squares. For brevity, we can do these two steps in one line of code

ss_total=sum(dev_tot^2) ss_total

##### [1] 426685.2

I have called this value ss_total because it captures the total variability ( _i.e_ ., the sum of squared deviation) in chick mass in our data set.

Now, let’s partition this total variability into variability among groups and variability within groups. The variability among groups measures how the mean mass for each treatment differs from the grand mean for the study. So, it captures the effect of the treatments. The variability within groups measures how the mass of chicks within each treatment differs from the mean for that particular treatment. So, it captures variability due to everything _except_ the treatments.

To partition variability, it is easiest if we have a vector that lists the mean mass for chicks in each treatment.  We can obtain this with

> treat_mean=ave(chickwts$weight,chickwts$feed) (3.6) treat_mean

[1] 160.2000 160.2000 160.2000 160.2000 160.2000 160.2000 [7] 160.2000 160.2000 160.2000 160.2000 218.7500 218.7500 [13] 218.7500 218.7500 218.7500 218.7500 218.7500 218.7500 [19] 218.7500 218.7500 218.7500 218.7500 246.4286 246.4286 [25] 246.4286 246.4286 246.4286 246.4286 246.4286 246.4286 [31] 246.4286 246.4286 246.4286 246.4286 246.4286 246.4286 [37] 328.9167 328.9167 328.9167 328.9167 328.9167 328.9167 [43] 328.9167 328.9167 328.9167 328.9167 328.9167 328.9167 [49] 276.9091 276.9091 276.9091 276.9091 276.9091 276.9091 [55] 276.9091 276.9091 276.9091 276.9091 276.9091 323.5833 [61] 323.5833 323.5833 323.5833 323.5833 323.5833 323.5833 [67] 323.5833 323.5833 323.5833 323.5833 323.5833

Here, the command ave takes the mean weight for the chicks in each of the feed groups. I called the result treat_mean because it contains the means for each treatment and assigns those to each chick in that treatment. For example, the first 10 chicks in the study were raised on horsebean, and the mean mass of chicks raised on horsebean was 160.2 grams. The next 12 chicks were raised on linseed, and the mean mass of chicks raised on linseed was 218.75 grams.

36

To find the part of the variability in the population that is due to the treatments, we take the difference between the treatment mean for each chick and the grand mean, square that difference, and sum over all chicks (note the analogy to codes 3.4 and 3.5)

dev_treat=treat_mean-mean(chickwts$weight) ss_treat=sum(dev_treat^2) ss_treat

##### [1] 231129.2

This is the among-group part of the sum of squared deviance. I called it ss_treat because it captures the sum of squared deviation due to treatments.

To find the part of the variability that is due to everything _except_ the treatments, we subtract the treatment means from the mass of each individual chick, and then square and sum those differences

> dev_err=chickwts$weight-treat_mean (3.8) ss_err=sum(dev_err^2) ss_err

[1] 195556

This is the within-group part of the sum of squared deviation. It captures all of the variability that is not explained by the treatments. This measure is often called the _sum of squared error_ , and I have respected that naming convention here. Error in this sense does not imply a mistake on the part of the researcher. Rather, it implies error in the ability of the treatments to predict the masses of the individual chicks in the study. Notice that ss_treat + ss_err = ss_tot. That is, the part of the variability due to treatments and the part due to everything other than treatments add up to the total variability in the population. That is what we should expect.

If there really were no effect of treatment in our study, then we could think of our data as if the responses (here, the individual chick masses) had been drawn at random from a single population. There would be variability among the treatment means, but this would be due only to chance. If we simulated many data sets by drawing at random from the source population, the variability among treatments would usually be small relative to the variability within treatments. However, sometimes it would be large.  When properly scaled<sup>1</sup> , the ratio ss_treat/ss_err in the simulated data sets would follow a well-studied distribution called an _F-distribution_ . By comparing the results of our observed ss_treat/ss_err to this F-distribution, we can estimate the probability of seeing variability among treatments at least as large as our observed variability simply

> 1 To scale ss_treat/ss_err, we multiply by ( _k_ -1)/( _n_ - _k_ +1), where _n_ is the number of observations and _k_ is the number of treatments. The result is called an F-statistic. We compare the F-statistic to an F- distribution with _k_ -1 and _n_ - _k_ +1 degrees of freedom.

37

due to chance. This is the p-value for the hypothesis that the treatments in our study have different mean responses.

#### **Conducting an ANOVA in R**

The example above illustrates the principle behind ANOVA, but in practice we rarely take the time to work out an ANOVA by hand. It is very easy to implement ANOVA in R. For the chickwts data, the command

cw_anova=aov(weight~feed,data=chickwts)

analyses the variability in weight among and within the treatments in feed. The tilde means the same thing it meant in code 3.2 – weight depends on feed. The text data=chickwts tells R to use the data in chickwts. Alternatively, you could use cw_anova=aov(chickwts$weight~chickwts$feed). In either case, the results of the analysis are stored as cw_anova. To see them, we use the command

summary(cw_anova)

(3.10)

Df Sum Sq Mean Sq F value   Pr(>F) feed         5 231129   46226   15.37 5.94e-10 *** Residuals   65 195556    3009 --Signif. codes: 0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

In this table, the values in the Sum Sq column are the ss_treat and ss_err values we calculated above, and the F value is the F-statistic for the analysis. The Pr(>F) is the probability of seeing ss_treat this large due to chance alone, and is thus the p-value for this analysis. Usually, people will report the F-statistic and degrees of freedom with the p-value. For example, here we might report

“We found strong evidence for an effect of diet on chick mass (F(5,65) = 15.37, p < 0.0001).”

If you reported your sample size in your methods (as you should!), then reporting the F-statistic and degrees of freedom is redundant. An interested reader could back-calculate your F-statistic from the p-value. Nonetheless, many journals and reviewers like to see this information. Note that I have reported the p-value as simply “<0.0001.” Some authors report exact p-values even if those are very small. However, knowing that a p-value is 10<sup>-8</sup> instead of 10<sup>-4</sup> does not change how we should interpret the result, and very small p-values may be precise but they are unlikely to be accurate. So, I usually report p-values to four decimal places, and report smaller p-values as “p < 0.0001.”

#### **The** **_post hoc_ Tukey test**

ANOVA studies the total variability among all treatment groups in a study. It tells us whether the treatments differ, but it does not tell us which treatments differ from which other treatments. Often however, that is the information we

38

really want to have. It is tempting to revert to pairwise t-tests to answer this, but then we face the multiple comparison problem that we discussed at the beginning of this chapter.

One solution to this problem, proposed by John Tukey and later advanced by Clyde Kramer, is called _Tukey’s honest significant difference test_ , or sometimes the _post hoc Tukey test_ . This test makes pairwise comparisons between all treatments in a study while taking multiple comparisons into account. To conduct a _post hoc_ Tukey test based on the ANOVA we just conducted, we can use the command

TukeyHSD(cw_anova)

(3.11)

Tukey multiple comparisons of means 95% family-wise confidence level

Fit: aov(formula = chickwts$weight ~ chickwts$feed)

$`chickwts$feed`

diff         lwr       upr     p adj horsebean-casein    -163.383333 -232.346876 -94.41979 0.0000000 linseed-casein      -104.833333 -170.587491 -39.07918 0.0002100 meatmeal-casein      -46.674242 -113.906207  20.55772 0.3324584 soybean-casein       -77.154762 -140.517054 -13.79247 0.0083653 sunflower-casein       5.333333  -60.420825  71.08749 0.9998902 linseed-horsebean     58.550000  -10.413543 127.51354 0.1413329 meatmeal-horsebean   116.709091   46.335105 187.08308 0.0001062

…

Here, the argument of the command TukeyHSD(…) is the result of our aov analysis. In the output table, the first column specifies the treatments that are being compared, the diff column reports the observed difference between them, and the p adj column reports the probability that a difference that great could arise by chance alone. The signs in the diff column correspond to the order of the treatments in the row names. For example, in the first row, horsebean minus casein produces a difference of -163.38 g. So, chicks in the casein treatment were larger by 163.38 g on average.

One common way to report the results of a _post hoc_ Tukey test is with a bar chart as shown in figure 3.3 (next page). Here, the bars represent the means for each treatment, and the error bars show the standard errors within each treatment. These are the same conventions that we used when we made bar charts to report the results of t-tests.  However, in this figure we have added horizontal lines over the bars. Treatments that fall under the same horizontal line are not significantly different. This gives readers an easy visual guide to assess which treatments are significantly different from which others.

When reporting the results of a _post hoc_ Tukey test, it may be tempting to cut-and-paste the output table from TukeyHSD() directly into your paper. Avoid that temptation! Reporting science is like any other kind of writing. You want to give your readers all of the information they need to understand the argument you are making, but not so much information that they get lost in the details. The

39

<!-- Start of picture text -->
horsebean linseed soybean meatmeal casein sunflower<br>350<br>250<br>grams<br>150<br>50<br>0<br><!-- End of picture text -->

**Figure 3.3. Mean mass of six-week old chicks raised on each of six different diets** . Error bars show standard errors around the mean. Treatments that fall under the same horizontal line are not significantly different (α = 0.05).

output in (3.11) includes a lot of information your readers do not need. If you ask them to wade through this table to find the information they do need, many will skip over the table entirely, and will miss the evidence behind your argument. In general, the more simply you can report your results, the more effective your writing will be. If your analysis includes only three or four groups, you may be able to report all of the pairwise differences in the text of your paper. You could tell readers that group 1 either is or is not different from group 2, group 2 either is or is not different from group 3, and group 1 either is or is not different from group 3, and you could report the expected difference and the p-value for each comparison. But, if your analysis has six groups like the one we just did, there are 15 pairwise comparisons to make, and if you report all of these in the text readers will struggle to process the information. So, you may have to think carefully about what readers really want to know, and focus your text on that.

#### **Assumptions and alternatives**

Fisher’s ANOVA makes important assumptions about the data being analysed. First, it assumes that deviation from the mean (that is, error) within each treatment is normally distributed. This does not mean that the response variable will be normally distributed across the entire data set. For example, figure 3.4 is a histogram in which the red, green, and blue bars represent responses to three different treatments. The full histogram has three peaks, so the responses across the whole study are not normally distributed. However, within each treatment, responses are normally distributed about the treatment mean. So, the data satisfies the assumption of normality. Second, Fisher’s ANOVA assumes that variability within each treatment is equal. That is, on average, the

<!-- Start of picture text -->
0 5 10 15<br>response<br>25<br>15<br>Frequency 5<br>0<br><!-- End of picture text -->

**Figure 3.4. An example of a response variable that meets the assumption of normality.** The red, green, and blue bars show histograms of responses to three different treatments. Within each treatment, responses are normally distributed around the treatment mean.

40

data points within any one treatment have about the same deviation from the treatment mean as the data points within any other treatment.

If responses within treatments are not normally distributed, researchers sometimes use a Kruskal-Wallis test instead of an ANOVA. Like the Wilcoxon test introduced in the previous chapter, the Kruskal-Wallis test avoids the normality assumption by analysing the rank order of the responses rather than the raw response data. That means that the Kruskal-Wallis test does not test for a difference in means among treatments, but rather tests for differences in mean ranks. The command for

**Figure 3.5. Olive Jean Dunn**

implementing a Kruskal-Wallis test is analogous to the command that implements an ANOVA:

cw_kwtest=kruskal.test(weight~feed,data=chickwts) cw_kwtest

Kruskal-Wallis rank sum test

data: weight by feed Kruskal-Wallis chi-squared = 37.3427, df = 5, p-value = 5.113e-07

The appropriate _post hoc_ test for a difference in mean ranks was developed by statistician Olive Jean Dunn (figure 3.5), and is called Dunn’s test. Dunn’s test is not included in R, but you can download the R package dunn.test from CRAN (see the Appendix for instructions on how to download R packages). After you have downloaded and installed dunn.test, you can implement the test with

dunn.test(chickwts$weight,chickwts$feed,method="by")

Kruskal-Wallis rank sum test

data: x and group Kruskal-Wallis chi-squared = 37.3427, df = 5, p-value = 0 Comparison of x by group (Benjamini-Yekuteili) Col Mean-| Row Mean |     casein   horsebea    linseed   meatmeal    soybean ---------+------------------------------------------------------horsebea |   4.813069 |    0.0000* | linseed |   3.308292  -1.658736 |    0.0047*     0.2418 | meatmeal |   1.415755  -3.364059  -1.819817 |     0.3253    0.0048*     0.1902 | soybean |   2.499922  -2.602093  -0.933255   0.974144 (output truncated for brevity)

41

The first argument of dunn.test is a vector with the response variable you want to study, and the second is a vector with the treatment names. The text method="by" tells R to use the Benjamini-Yekuteili method for assessing the difference between pairs of treatments. (There are other options, but the Benjamini-Yekuteili method is a reasonable default.)

Unless the response data is ordinal ( _e.g_ ., data on the Likert scale), researchers are often more interested in comparing means than in comparing mean ranks. Moreover, ANOVA is reasonably robust to violations of the normality assumption. So, many researchers use ANOVA rather than the KruskalWallis test even if error is not normally distributed. In this case, it is important for the researcher to report that error was not normally distributed, and to interpret his or her p-values conservatively. For example, if error were not normally distributed, the researcher might conclude that a p-value of 0.05 obtained by ANOVA is only weak evidence of a difference in means among treatments. A p-value of 0.001 however would still be strong evidence for a difference among means.

In some studies, the variance within some treatments is greater than within others, and this also violates the assumptions of ANOVA. We can see whether the variance is unequal among groups using

aggregate(weight~feed,data=chickwts,var)

(3.14)

feed   weight 1    casein 4151.720 2 horsebean 1491.956 3   linseed 2728.568 4  meatmeal 4212.091 5   soybean 2929.956 6 sunflower 2384.992

The function aggregate applies another function (in this case var) to groups in a data set. Here, aggregate uses the data in chickwts. It analyses weight by group, where the groups are defined by feed. The text var tells R to take the variance of each group (but we could have used mean to have R take the mean, hist to make R plot histograms, _etc_ .). The output of this command lists the variance of the response variable within each group.

ANOVA is reasonably robust to unequal variance. As a rule of thumb, we do not need to worry unless the variance of some groups is more than about 4 times greater than that of others. So, in the chickwts data, Fisher’s ANOVA should be reasonably accurate. However, a simple correction for unequal variance, _Welch’s correction_ , exists and is included in R. Because it is so easily done, many researchers use ANOVA with Welch’s correction whenever they suspect that variance may be unequal among treatments. To conduct and ANOVA with Welch’s correction, we use

42

oneway.test(weight~feed,data=chickwts)

(3.15)

One-way analysis of means (not assuming equal variances)

data:  weight and feed F = 19.6617, num df = 5.000, denom df = 29.952, p-value = 1.177e-08

Like Fisher’s ANOVA, the _post hoc_ Tukey test is not absolutely accurate when variance among treatments is unequal. Therefore, researchers sometimes use the Games-Howell test to make _post hoc_ comparisons between treatment means when variance among treatments is unequal. If you want to use the GamesHowell test, you can find it implemented in the R package rstatix.

#### **Two-way ANOVA**

The chicken feed experiment that we analysed above had only one predictor: feed type. The researchers were able to control other variables that might have affected chick growth. For example, at cooler temperatures chicks use more energy to stay warm and have less energy for growth, so all chicks were raised at the same temperature. When data is collected in natural settings rather than in the lab, it is often impossible to control all of the factors that might affect a response variable. This adds variability to our data, and unexplained variability makes it harder to see the results we are interested in studying.

If we cannot get rid of unexplained variability by controlling it in our experiments, sometimes we can get rid of it by explaining it. To do that, we can include additional factors that might affect our response variable in our analysis. To illustrate this, we will use a data set called “bike_pass.csv,” which you can download from Dropbox. Recall from Chapter 2 that we can read this data into R using

bike=read.csv("bike_pass.csv",header=TRUE) head(bike)

(3.16)

time vehicle helmet      pass 1   aft     bus      n 1.0446667 2  morn     bus      n 1.0370000 3  noon     bus      n 1.1528182 4   aft     car      n 1.3967760 5  morn     car      n 1.3182672

…

The data set “bike_pass.csv” includes more than 2300 observations of cars passing cyclists. This is too much data to display in its raw form all at once. If we want to see what the data looks like without displaying all of it, the command head will display just the first few lines. For each observation in this data set, the researchers recorded the time of day (morning; mid-day, which they called “noon;” or afternoon), the type of vehicle (car, LGV, SUV, bus, HGV, taxi, or PTW), whether the cyclist was wearing a helmet, and the distance (in meters) at which

43

the car passed the cyclist. We will ask whether two of these predictors, vehicle type and helmet, affect the space that drivers give cyclists when passing.

The principle here is the same as in the one-way ANOVA. If we think of our two predictors as treatments, then our goal is to measure the variability among treatments and to compare that to the variability within treatments. By analysing both predictors together, we can “explain” the variability due to each predictor when we analyse the other, and so increase our power to detect results. Moreover, we can take this one step further. We can look for an interaction between the predictors. That is, we can ask whether the drivers of different vehicle types respond differently to helmets. As above, we will make R do the work for us. After all, that is what R is for.

Conducting a two-way ANOVA requires only a slight modification of the code we used to conduct a one-way ANOVA

ba=aov(pass~helmet+vehicle+helmet*vehicle,data=bike)

Here we have told R to analyse the variance in pass using helmet and vehicle as predictors, and to store the results with the name ba. The text helmet*vehicle tells R to include an interaction between helmet and vehicle in the analysis. We can get the result with the command

summary(ba)

Df Sum Sq Mean Sq F value   Pr(>F) helmet            1    4.3   4.264  29.841 5.19e-08 *** vehicle           6    6.9   1.156   8.092 1.13e-08 *** helmet:vehicle    6    0.4   0.073   0.509    0.802 Residuals      2341  334.5   0.143 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

This table is exactly analogous to the table in 3.10. The first thing to notice is that the p-value associated with the interaction is greater than 0.05. So, we have no evidence for an interaction between helmet and vehicle. If there is no evidence that a predictor affects the response variable, it is often a good idea to remove that predictor from the model. We can remove the interaction from the model by simply removing it from the code in 3.18. Notice that this time I am saving the results as ba1. Since I am not overwriting the variable ba, I can go back and look at it again if I need it without rerunning the code in 3.18.

ba1=aov(pass~helmet+vehicle,data=bike) summary(ba1)

Df Sum Sq Mean Sq F value   Pr(>F) helmet         1    4.3   4.264  29.878 5.09e-08 *** vehicle        6    6.9   1.156   8.102 1.10e-08 *** Residuals   2347  334.9   0.143 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

44

In this result, we appear to have strong evidence ( _i.e_ ., low p-values) for the hypotheses that drivers pass cyclists at a different distance if they are wearing helmets, and also that the drivers of different types of vehicles pass cyclists at different distances. But, before we attempt to interpret this, let’s try one more thing. Let’s change the order of the predictors in the code

ba2=aov(pass~vehicle+helmet,data=bike) summary(ba2)

(3.20)

Df Sum Sq Mean Sq F value   Pr(>F) vehicle        6    7.1   1.180   8.269 7.00e-09 *** helmet         1    4.1   4.121  28.880 8.46e-08 *** Residuals   2347  334.9   0.143 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Notice that when we change the order of the predictors, the p-values and the sums of squares also change!

This illustrates an important point with the aov function: _the order in which the predictors enter the model matters_ . In general, we can interpret these outputs to report the p-value associated with the last predictor while controlling for the first predictor. So, output ba2 tells us that that drivers responded differently to cyclists with or without helmets (F(1,2347) = 28.88, p < 0.0001), and output ba1 tells us that drivers of different vehicle types pass cyclists at different distances (F(6,2347) = 8.10, p < 0.0001). But, output ba tells us that there is no evidence for an interaction between helmets and vehicle types (F(6,2341) = 0.51 p = 0.802). That is, we have no evidence that drivers of different vehicle types respond differently to helmets. Notice that these three results come from different models!

Knowing that there are differences is interesting, but we would also like to know what those differences are. For this, we can use the _post hoc_ Tukey test again. Because TukeyHSD works with the aov output, we must be careful to study the right model. If we want to find the effects of vehicle types while controlling for helmet use, we should examine ba1:

TukeyHSD(ba1) Tukey multiple comparisons of means 95% family-wise confidence level Fit: aov(formula = pass ~ helmet + vehicle, data = bike) $helmet diff        lwr        upr p adj y-n -0.08512504 -0.1156638 -0.0545863 1e-07 $vehicle diff          lwr          upr     p adj car-bus   0.261987347  0.095430813  0.428543881 0.0000745 HGV-bus   0.073238604 -0.132108637  0.278585845 0.9415202 LGV-bus   0.193050733  0.016261076  0.369840389 0.0219066

…

45

This output shows the magnitudes and p-values for the pairwise differences in passing margins among vehicle types. For example, there is evidence that busses pass cyclists more closely than cars (by 26.20 cm, p < 0.0001) or lorries (by 19.31 cm, p = 0.0219) do. There are additional significant differences if we look at the full table, but to save space I have only presented the first few rows here. If we want to see comparisons when cyclists are or are not wearing helmets while controlling for vehicle type, we should examine model ba2:

TukeyHSD(ba2)

Tukey multiple comparisons of means 95% family-wise confidence level

Fit: aov(formula = pass ~ vehicle + helmet, data = bike)

$vehicle

diff         lwr           upr     p adj car-bus   0.258279758  0.09172322  0.4248362915 0.0001016 HGV-bus   0.064572641 -0.14077460  0.2699198812 0.9681360 LGV-bus   0.188515952  0.01172630  0.3653056084 0.0278291

…

$helmet

diff        lwr         upr p adj y-n -0.08357617 -0.1141149 -0.05303744 1e-07

Here we find strong evidence that drivers pass cyclists more closely when they are wearing helmets than when they are not (by 8.36 cm, p < 0.0001).

In the example above, both helmets and vehicle types might be interesting predictors. Sometimes though, we might include a predictor in an ANOVA even though we are not interested in that predictor itself. For example, imagine that in the analysis above, passing distance was evaluated by four different observers. If some observers underestimate passing distances and others overestimate passing distances, this will add unexplained variability to our data set and potentially obscure the results we are interested in studying. By including the identity of the observer as a predictor in our ANOVA, we can explain this variability. This will give us a clearer picture of the results we are really interested in studying. In this case, we would add the observer to the model first, because we want to control for the effect but we are not interested in drawing inferences about it.

46

### **Chapter 4. Understanding the effects of numerical predictors**

In the previous two chapters, our goal was to compare the mean value of a response variable observed in different groups, where groups were defined by one or more categorical attributes. Often however, the attributes that describe individuals in a population are numerical rather than categorical. For example, we might be interested in how the number of females in the harem of a male elk ( _Cervus canadensis_ ) depends on his body size. Body size varies continuously, so it is not clear how we would assign males to categories. Moreover, it is not clear that we _should_ assign males to categories. If we were to arbitrarily divide the population “small” ( _i.e_ ., smaller than the mean) and “large” ( _i.e_ ., larger than the mean) groups, we would ignore information about the exact size of the individuals within each group. An approach that allows us to use all of the information we have available might better.

In this chapter we will study one such approach: _linear regression_ . For most of the chapter, we will work with data from the 1994 Canadian Survey of Labour and Income Dynamics for the province of Ontario. The full data set is available from Statistics Canada (http://www.statcan.gc.ca), but you can download the subset of the data we will use from Dropbox, where it is saved under the name “can_inc.csv.”  The data set contains the average hourly wage for 100 Canadian workers, along with the age, self-reported sex, native language, academic aptitude<sup>2</sup> , and total years of formal education for each individual. You can inspect the data by reading the file into R as a data frame and then typing the name of the data frame into the R console:

ci=read.csv("can_inc.csv",header=TRUE) ci

wage age sex    lang       apt school 1   10.56  40   m english 114.36080   15.0 2   11.00  19   m english  95.58686   13.2 3   17.76  46   m   other 102.16705   14.0 4   14.00  50   f english 125.61239   16.0 5    8.20  31   m english 114.25153   15.0 6   16.97  30   f english  97.54081   13.5

…

In the examples in this chapter, we will use linear regression to understand how an individual’s hourly wage depends on the potential predictors in this data set.

It is worth thinking for a moment about the column labelled “sex” in the data set we are about to study. Respondents to this survey were required to choose either male or female, so the variable “sex” in this data set is binary, even though there is growing evidence that sex in humans is not binary. Moreover, in 1994, most people had a much poorer understanding of the difference between

> 2 All of the data is real, except for academic aptitude, which I have made up to illustrate point we will consider later.

47

<!-- Start of picture text -->
8 10 12 14 16 18 20<br>years of education<br>40<br>30<br>20<br>hourly wage in C$<br>10<br>5<br><!-- End of picture text -->

**Figure 4.1. Hourly wage as a function of years of formal education for 100 Canadian workers in 1994.**

“sex” and “gender” than we have today. So, did respondents report their sexes or their genders? We cannot know. All we know for sure is that the column labelled “sex” shows the sex that each respondent reported. But, that may still be enough to answer some interesting questions.

#### **Simple linear regression**

Let’s start with a simple analysis. Given the effort you are putting in to your study at the University of Manchester, you might hope that an individual’s hourly wage depends at least in part on their number of years of formal education. We can create a scatter plot to see whether our data suggest such a pattern for workers in Ontario in 1994. The command

> plot(ci$school,ci$wage,xlab="years of education",ylab="hourly (4.2) wage in C$")

creates the plot in figure 4.1. In the command plot, the first argument (ci$school) gives the _x_ -coordinate for each point, and the second argument (ci$wage) gives the _y_ -coordinate for each point. There may be a trend in the data: certainly all of the highest wages belonged to workers with above the average years of education, and no one with a university degree (~16 years of education) earned less than C$10 per hour. But, it is hard to assess this trend simply by eye.

One step forward might be to plot a line through the data, as in figure 4.2 on the next page. Each data point in the figure has some deviation from the red line. The length of the blue line descending from the leftmost point is the deviation for that point. The sum of the squared deviation across all of the data points measures the amount of variability in the data that is _not_ explained by the red line. The _line of best fit_ is the line that minimises the sum of squared deviation. Thus, the line of best fit is the line that best explains the variability in the data set. In figure 4.2, the red line is the line of best fit.

48

<!-- Start of picture text -->
8 10 12 14 16 18 20<br>years of education<br>40<br>30<br>20<br>hourly wage in C$<br>10<br>5<br><!-- End of picture text -->

**Figure 4.2. Hourly wage as a function of years of formal education for 100 Canadian workers in 1994.** The line of best fit is shown in red. The blue line shows the deviation of the leftmost point from the line of best fit.

The line of best fit is an example of a linear model. If we know the value of the predictor (here, years of education), then the line of best fit predicts ( _i.e_ ., models) the value of the response (here, hourly wage). In figure 4.2, the line of best fit slopes upward with increasing education, which seems to support the relationship between education and wage that we hypothesised. But, is this really _evidence_ ? We can draw a line of best fit through any cloud of data points. That line will almost always have a slope, and so will almost always explain at least some of the variability in the response variable. The question we must answer is, “ _What is the probability that the line of best fit would explain at least this much of the variability in the response variable in the sample if there were really no relationship between the predictor and the response in the full population_ ?” That is, what is the probability of obtaining a relationship at least as strong as the one we see in the data just by chance alone? Once again, this is the fundamental question of frequentist statistics.

To answer this question, we can use the same approach we used in ANOVA. That is, we can compare the amount of variability explained by the line of best fit to the unexplained variability in the response variable. This idea is illustrated in figure 4.3. Figure 4.3 shows the same data as figures 4.1 and 4.2, with the line of best fit again plotted in red. The horizontal black line is the mean wage for all individuals in the data set. The vertical blue line shows the deviation from the line of best fit for a representative data point. Thus, this line captures

<!-- Start of picture text -->
8 10 12 14 16 18 20<br>years of education<br>40<br>30<br>20<br>hourly wage in C$<br>10<br>5<br><!-- End of picture text -->

**Figure 4.3. Hourly wage as a function of years of formal education for 100 Canadian workers in 1994.** The mean wage over all workers is shown in black. This would be the predicted value of each workers wage if there were no effect of education. The line of best fit to the education data is shown in red. This is the best prediction of each workers wage is there is an effect of education. The vertical green line shows the deviation from the mean explained by the line of best fit, and the vertical blue line shows the unexplained deviation for a representative data point.

49

variability that _is not_ explained by the line of best fit. The vertical green line captures the part of deviation from the mean that _is_ explained by the line of best fit. If the amount of variability explained by the line of best fit is large relative to the part that is not explained by the line of best fit, then we are unlikely to see a result this strong by chance alone. Just as in ANOVA, the ratio of explained to unexplained variability that we would expect to see by chance alone follows a known distribution, and we can use that distribution to calculate the probability of seeing a result as extreme as the one in our observed data by chance. That probability is the p-value associated with the predictor in the model.

Conducting linear regressions in R is easy. To build the linear model, we use the code

s.lm=lm(wage~school,data=ci)

Here, wage is the response variable, school is the predictor, and the command lm stands for linear model. The code data=ci tells R to find the vectors wage and school in the data frame ci. The text s.lm names the linear model we are creating. To see the result, we use

summary(s.lm) Call: lm(formula = wage ~ school, data = ci) Residuals: Min      1Q  Median      3Q     Max -10.406  -5.193  -1.107   3.687  24.613 Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)   3.0277     3.2303   0.937 0.350924 school        0.9057     0.2313   3.916 0.000166 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.883 on 98 degrees of freedom Multiple R-squared:  0.1353, Adjusted R-squared:  0.1265 F-statistic: 15.34 on 1 and 98 DF,  p-value: 0.0001664

There is a lot of useful information in this summary, but we will focus on just a few things. First, in the Estimate column, the value associated with school is effect size of that predictor. Recall that school reports how much formal education each person has, and it is measured in years. So, the estimate associated with school tells us that for each additional year of education, a worker can expect to earn an additional C$0.9057 per hour. The value in the Pr(>|t|) is the p-value associated with that predictor. Because the p-value is small, we can be confident that the relationship between education and wage is not due to chance alone. The Multiple R-squared value tells us the proportion of the variability in the response variable that is explained by the predictors in

50

the model. Here, the model explains 13.53% of the variability in the data. Is that good? That depends on the goal of the study. If the goal is to predict wage based on education alone, then the low R<sup>2</sup> value suggests we will not be able to do that accurately. Most of the variability in wage is not explained by education: some people with relatively little education earn high wages, and some people with more education earn low wages (as we saw in figure 4.1). However, if the goal is simply to show that earnings increase with education, then the positive effect size and the low p-value mean that we can say this with confidence.

When reporting the results of a simple linear regression, it is important to report both the p-value and the effect size of the predictor, since these convey different information. For the analysis above, a researcher might report, “We found a significant positive effect of education on hourly wage <mark>(</mark> _<mark>β</mark>_ <mark>= 0.9057 C$ h</mark><sup>-1</sup> <mark>y</mark><sup>-1</sup> <mark>, p = 0.0002, t = 3.916, df = 98).” The Greek letter</mark> _<mark>β</mark>_ <mark>is often used to indicate effect sizes for linear regression. The effect size usually has units (here, Canadian dollars per hour per year), and these must also be reported. As with ANOVA, the t-statistic and degrees of freedom are redundant if you have reported your sample size with your methods, but many readers like to see them anyway.</mark>

<mark>The results of linear regression lend themselves to graphical presentation as well. We can produce the plot in figure 4.2 using the code</mark>

> plot(ci$school,ci$wage,xlab="years of education",ylab="C$/h") (4.5) abline(s.lm,col="red")

The plot command in code 4.5 is similar to the one in command 4.2. The command abline(s.lm,col="red") adds the line of best fit obtained from the model s.lm, and the argument col="red" tells R to plot that line in red.

#### **Mean centring predictors**

Look again at the output from code 4.4. There is a row in the output table labelled (Intercept). The _intercept_ is the point at which the line of best fit crosses the _y_ -axis. That is, it is the predicted value of the response variable when the predictor is equal to zero. Our model predicts that a worker with no formal education would earn C$3.0277 per hour. This intercept is not very useful to us. It is well outside the range of educations that we observed in the data set, and we have no reason to believe our predictions will hold when the predictors are outside of the range we studied. For a predictor like age, the problem is even worse. The predicted wage when age equals zero is nonsense – people of age zero do not work!

We can transform our predictor in a way that makes the intercept more meaningful by _mean centring_ . To mean centre a predictor, we subtract the mean value from each of the observed values. For the predictor school, we can use the command

51

(4.6)

mc_school=ci$school-mean(ci$school) mc_school

[1] 1.353 -0.447 0.353 2.353 1.353 -0.147 -1.647 0.353 …

The new vector mc_school contains the difference between each observed education value and the population mean education value. A person with exactly the mean amount of education would have zero in mc_school, while a person with greater than average education would have a positive value and a person with less than average education would have a negative value. We can use the mean centred predictor in linear regression just as we used the raw predictor above. Focusing on the interesting parts of the result:

s.lm=lm(wage~mc_school,data=ci) summary(s.lm)

… Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)  15.3875     0.6883  22.356  < 2e-16 *** mc_school     0.9057     0.2313   3.916 0.000166 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 Residual standard error: 6.883 on 98 degrees of freedom Multiple R-squared:  0.1353, Adjusted R-squared:  0.1265 F-statistic: 15.34 on 1 and 98 DF,  p-value: 0.0001664

The value of the intercept is now 15.3875 C$ h<sup>-1</sup> . This is the expected wage for a worker with exactly the average education. The very low p-value indicates that a worker with average education can expect to earn more than C$0 per hour (which by itself is not a very surprising or interesting result!). Notice that the other values we are interested in ( _e.g_ ., the effect size and p-value associated with education and the R<sup>2</sup> value) are not changed by mean centring.

It is not always necessary to mean centre predictors. However, in cases like the one above, mean centring can make model outputs easier to interpret.

#### **Dichotomous predictors**

In the example above, we used years of formal education as a predictor for hourly wage. Years of formal education ( _i.e_ ., school) is a continuous variable. Other variables in the data set ( _i.e_ ., sex and lang) are dichotomous. Individuals reported that they were either male or female; they were either native English speakers or they were not. Many people believe we cannot use dichotomous predictors in linear regression, but that belief is incorrect.

In our data set, sex is qualitative. “Male” and “female” are categories, not numbers. To use sex as a predictor in a linear regression, we need to convert this information into a numerical predictor. One easy way to do this is to create a new vector called male. The vector male will have a value of 1 for each male in the study, and a value of 0 for each female in the study. We call this kind of

52

variable and _indicator_ , because a value of 1 indicates that the subject reported that they were male, and a value zero indicates that the subject reported that they were not male. To make this indicator, we can use the code<sup>3</sup>

male=rep(1,length(ci$sex)) male[which(ci$sex=="f")]=0

The command rep in 4.8 creates a vector in which the first argument, the number 1, is repeated for every entry in ci$sex. So, after this step, male is a vector of all ones with the same length as ci$sex. The second line identifies each entry of ci$sex that is equal to f, and it sets those entries of male equal to zero. (If we wanted to do this in a more intuitive - but more time consuming - way, we could have opened “can_inv.csv” in Excel and entered data into a column called male by hand. But, why should we work if we can make R work for us?!)

Once we have created the predictor male, we can use it just as we used the continuous predictor school above.

s.lm=lm(wage~male,data=ci) summary(s.lm)

…

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)   12.865      1.139  11.290  < 2e-16 *** male           4.135      1.459   2.835  0.00557 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 7.116 on 98 degrees of freedom Multiple R-squared:  0.07578, Adjusted R-squared:  0.06635 F-statistic: 8.035 on 1 and 98 DF,  p-value: 0.005573

Here, the value in the Estimate column of the row male is the effect of being male on hourly wage. Men in the data set earned C$4.135 per hour more than women. The intercept is the expected wage when the predictor equals zero. So, C$12.865 is the expected wage for women, because women are indicated by zeros in the predictor male. And, C$4.135 + C$12.865 = C$17.00 is the expected wage for men.

We can create a plot for this model using the code

> plot(male,ci$wage,xlab="sex",ylab="wage in C$/h",xaxt="n") (4.10) axis(1,at=0:1,labels=c("female","male")) abline(s.lm,col="red")

> 3Another way to make this indicator is with the command male=as.numeric(ci$sex=="m"). Here the logical ci$sex=="m" creates a vector that is TRUE when ci$sex=="m" and FALSE when ci$sex=="f". The command as.numeric(…) converts TRUEs into 1s and FALSEs into 0s. There are often multiple ways to achieve the same thing in R!

53

Here, plot is the same command we used in code 4.2. The added text xaxt="n" suppresses the automatic _x_ -axis, and the command axis(… places the labels “female” and “male” at points 0 and 1 on a new _x_ -axis. The result is shown in figure 4.4.

#### **Multiple linear regression**

We have already learned to use t-tests to compare the means of two groups. You may wonder why we would want to use linear regression to compare means when we have a simpler a test available. The answer is that linear regression allows us to test the effects of multiple predictors at the same time.

<!-- Start of picture text -->
female male<br>Figure 4.4. Hourly wage as a  sex<br>function of the self-reported sex<br>of Canadian workers in 1994.<br>40<br>35<br>30<br>25<br>20<br>wage in C$/h<br>15<br>10<br>5<br><!-- End of picture text -->

In all of the approaches we have studied so far, we have detected the effect of a predictor on the response variable by comparing the variability explained by the predictor to the unexplained variability. If the variability explained by the predictor is large relative to the unexplained variability, then the relationship between the predictor and the response variable is unlikely to be due to chance alone, and we can infer that the relationship is real. By reducing the amount of unexplained variability in the data, we can increase the ratio of explained to unexplained variability, and increase our power to detect the effects we are interested in studying. If a response variable depends on more than one predictor, including all of the important predictors in the model allows us to explain more variability, reduce the unexplained variability, and increase the power of our analysis.

We can build a linear model with multiple predictors by simply adding a term to the code we have already used:

s.lm=lm(wage~mc_school+male,data=ci) summary(s.lm)

…

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)  12.7949     1.0555  12.123  < 2e-16 *** mc_school     0.9199     0.2215   4.153 7.05e-05 *** male          4.2502     1.3515   3.145  0.00221 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.59 on 97 degrees of freedom Multiple R-squared:  0.2153, Adjusted R-squared:  0.1991 F-statistic: 13.31 on 2 and 97 DF,  p-value: 7.81e-06

54

Note that, unlike the aov function in Chapter 3, the lm function is not sensitive to the order in which predictors are added. In 4.11, the row mc_school gives the effect size and p-value associated with years of formal education, and the row male gives the effect size and p-value associated with sex. Notice that the p-values are smaller than those given by simple regression in codes 4.7 and 4.9. Because there is less unexplained variability in our data, we are even more sure than before that the relationships between these predictors and our response variables are not due to chance. The intercept and effect sizes have changed slightly from those we obtained with codes 4.7 and 4.9. This is because the effect sizes reported for each predictor here are independent of the other predictor. That is, a man can expect to earn C$4.25 more per hour than a woman when they have the same amount of education. The intercept of C$12.79 per hour is the expected wage for a woman ( _i.e_ ., an individual for whom male = 0) with average education ( _i.e_ ., an individual for whom mc_school = 0).

We may wish to visualise this result in a figure. Because mc_school is the mean centred years of formal education, individuals with less than average education will have negative values and individuals with more than average education will have positive values. This will not be very intuitive to readers. So, let’s rebuild the model using the raw predictor school instead of the meancentred predictor mc_school

s.lm=lm(wage~school+male,data=ci) summary(s.lm)

…

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)   0.2408     3.2175   0.075  0.94050 school        0.9199     0.2215   4.153 7.05e-05 *** male          4.2502     1.3515   3.145  0.00221 ** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.59 on 97 degrees of freedom Multiple R-squared:  0.2153, Adjusted R-squared:  0.1991 F-statistic: 13.31 on 2 and 97 DF,  p-value: 7.81e-06

Notice again that changing between mean centred and raw predictors does not change effect sizes or p-values, although it does change the intercept. We can the plot the results using

plot(ci$school,ci$wage,col="blue",xlab="years of education",ylab="wage in C$/h") points(ci$school[which(ci$sex=="f")], ci$wage[which(ci$sex=="f")],col="red") abline(0.2408,0.9199,col="red") abline(0.2408+4.2502,0.9199,col="blue")

55

<!-- Start of picture text -->
8 10 12 14 16 18 20<br>years of education<br>35<br>25<br>wage in C$/h 15<br>5<br><!-- End of picture text -->

**Figure 4.5. Wage as a function of years of formal education among male (blue) and female (red) workers in Ontario in 1994.**

Here, the first line,  plot(…), creates a scatter plot of all of the data, just as in code 4.2. The second line, points(…,col="red"), plots just the points for which sex=="f" in red. The same points were plotted in blue by the first line, but the second line plots over them. So, after these two lines, we will see a scatter plot with males in blue and females in red. The third line, abline(0.2408,0.9199, col="red"), adds a red line to figure. This line predicts the wage for women as a function of their years of education. In abline, the first argument is the intercept and the second is the slope. We take these directly from the output of code 4.12. The intercept for women is 0.2408, and the slope of wage as a function of education (for either sex) is 0.9199. The final line adds a blue line that predicts men’s wages as a function of education. The intercept for men’s wages is 0.2408 ( _i.e_ ., the intercept for women) plus the effect of being a male, which is 4.2502 (and is the same for all men). The slope of wage on education is still 0.9199. The result is figure 4.5.

Code 4.11 builds a linear model with two predictors, but we are not limited to two. For example, we might be interested in how wage depends on education, age, sex, _and_ native language. We can study this in exactly the same way we did for the model with two predictors. Code 4.14 does three things, each of which we have already done above for other predictors. First, it mean centres age, and saves the result in mc_age. Second, it creates a numerical version of native language, where each individual has value of 1 if they are native English speakers and 0 otherwise, and saves the result as english. Finally, it builds and summarises a linear model.

mc_age=ci$age-mean(ci$age)

english=rep(1,length(ci$lang)) english[which(ci$lang=="other")]=0

56

s.lm=lm(wage~mc_school+mc_age+male+english,data=ci) summary(s.lm)

…

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept) 11.45168    1.82344   6.280 1.01e-08 *** mc_school    0.91607    0.20982   4.366 3.22e-05 *** mc_age       0.21851    0.05029   4.345 3.49e-05 *** male         5.24222    1.26863   4.132 7.74e-05 *** english      0.86832    1.75479   0.495    0.622 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.081 on 95 degrees of freedom Multiple R-squared:  0.3456, Adjusted R-squared:  0.3181 F-statistic: 12.54 on 4 and 95 DF,  p-value: 3.108e-08

From the intercept in the results, we can see that a woman (ie, male=0) whose native language is not English (ie, english=0) and who is of average age (ie, mc_age=0) and education (ie, mc_school=0) can expect to earn C$11.45 per hour. A man with the same age and education can expect to earn C$5.24 per hour more than the woman. In general, a person can expect to earn C$0.92 per hour more for every additional year of formal education, and older workers can expect to earn an additional C$0.22 for each year of their age. Notice that the p-value associated with english is large. So, although native English speakers in the data set earn more than non-native speakers, this difference might easily be due to chance. So, we have no evidence for an effect of native language on hourly wage in Ontario in 1994.

#### **Interactions**

In the regression models we have looked at so far, we have focused on _main effects_ . Main effects tell us how a predictor affects the response variable, independent of all of the other predictors. For example, the results of 4.14 tell us that if two people differ only in their education ( _i.e_ ., they have the same sex, age, and native language), the person with more education can expect to make C$0.92 per hour more for every additional year of education.

In many systems, predictors _interact_ . When this is true, the effect of one predictor on the response variable depends on the value of another predictor. For example, we might conjecture that the effect of education on hourly wage depends on age. When workers are young, an employer has little to evaluate them on other than their educations, so perhaps education matters a great deal in salary decisions. As workers get older, employers can evaluate their track records at work, and education may play a less important role in salary decisions. If the effect of education on salary decreases with age, we say that there is a _negative interaction_ between the predictors. If it increases, we say there is a positive interaction between the predictors.

57

To look for an interaction between predictors, we add a multiplicative term to our model. In this case, we are looking for an interaction between age and education, so we add a term mc_age*mc_school

s.lm=lm(wage~mc_school+mc_age+male+english+mc_age*mc_school, data=ci) summary(s.lm)

…

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)      11.41374    1.81013   6.305 9.28e-09 *** mc_school         0.81517    0.21814   3.737  0.00032 *** mc_age            0.23897    0.05162   4.630 1.17e-05 *** male              5.21140    1.25941   4.138 7.63e-05 *** english           0.95848    1.74279   0.550  0.58364 mc_school:mc_age  0.02982    0.01917   1.556  0.12315 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.036 on 94 degrees of freedom Multiple R-squared:  0.3621, Adjusted R-squared:  0.3281 F-statistic: 10.67 on 5 and 94 DF,  p-value: 3.874e-08

In this output, the row mc_school:mc_age reports the interaction. The p-value associated with the interaction is 0.1232, which means that we do not have evidence for an interaction between age and education in our data.

Age and education are continuous predictors, but interactions can also occur between dichotomous predictors, or between dichotomous and continuous predictors. One interesting interaction to look for might be between age and sex. Our data suggest that women in the labour force earned about 31% less than men, but does this depend on their age? For example, did younger women do better in terms of wage parity?

We can add an interaction between age and sex to our model in the same way we added an interaction between age and education

> s.lm=lm(wage~mc_school+mc_age+male+english+mc_age*mc_school+ (4.16) mc_age*male,data=ci)

58

##### summary(s.lm)

…

Coefficients: Estimate Std. Error t value Pr(>|t|) (Intercept)      12.78174    1.73361   7.373 6.77e-11 *** mc_school         0.80202    0.20431   3.926 0.000166 *** mc_age            0.03816    0.07197   0.530 0.597183 male              4.90329    1.18223   4.147 7.42e-05 *** english           0.01197    1.65130   0.007 0.994231 mc_school:mc_age  0.03079    0.01795   1.715 0.089657 . mc_age:male       0.35812    0.09508   3.766 0.000290 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 5.653 on 93 degrees of freedom Multiple R-squared:  0.4465, Adjusted R-squared:  0.4108 F-statistic:  12.5 on 6 and 93 DF,  p-value: 2.748e-10

When one of the predictors in a model is an indicator ( _e.g_ ., male), we can think of the class coded as zero (here, females) as the baseline. The class coded by one (here, males) is compared against this baseline. So, here, the intercept tells us the expected hourly wage for a woman with the population mean age and education, and the effect of male tells us how the expected hourly wage of a man differs from that of a woman if they both have the mean age and education. When the model includes an interaction between mc_age and male, the row mc_age reports the effect of age in the baseline sex (females), and the row labeled mc_age:male tells us how the effect of age in males differs from that in females.

With this in mind, let’s interpret the results in 4.16.  First, a woman with the population mean age and education can expect to earn C$12.78 per hour. As before, there is a positive effect of education on hourly wage: for each additional year of education, a worker of either sex can expect to earn an additional C$0.80 per hour. There is still a positive effect of being male: a man with the population mean age and education can expect to earn C$4.90 per hour more than a woman with the same age and education. There is still no effect of native language on hourly wage (p=0.9942). However, the effect of age on hourly wage is interesting. The main effect of age is C$0.03816 h<sup>-1</sup> , and the p-value is 0.5972. This is the effect of age in the baseline sex ( _i.e_ ., women). So, we have no evidence that older women earn more than younger women. However, there is a strong positive interaction between being male and age. The effect size of the interaction mc_age:male is C$0.35812 h<sup>-1</sup> . So, older men earn more than younger men. To find the effect of age on male wage, we add the interaction to the baseline effect of age in women. Thus, older men in the labour force earned an additional C$0.03816 h<sup>-1</sup> + C$0.35812 h<sup>-1</sup> = C$0.39128 h<sup>-1</sup> for every additional year of age. Finally, with all of the predictors in the model, there is weak evidence (p=0.08966) for a positive interaction between age and education. That is, contrary to our guess above, education may become slightly _more_ valuable as a worker gets older. Again though, the evidence for this last interaction is weak!

59

#### **Selecting and reporting best models**

We have now tried many different linear models to describe our data. How do we decide which one to report? Statisticians have dedicated careers to this question, and there is no single correct answer. Here, we will consider just one option: _backward selection_ . I have chosen this approach because it is simple and it works reasonably well for models with small numbers of predictors. Moreover, it is replicable. If two researchers study the same predictors in the same data set and they both use backwards selection, they will arrive at the same final model. This helps avoid a practice called p-hacking, which can occur when researchers consider many different models and choose the one that agrees most strongly with the story they want to tell. As you continue in Science, you will learn that there also are problems with backwards selection. For example, while backward selection will always select a model, it may not always select the best set of predictors for your response variable. If you will be considering models with large numbers of predictors, you may wish to make a more thorough study of approaches to model selection.

In backward selection, we start with the _full model_ . The full model is the model that contains all of the predictors that we are interested in studying. We can think of the model in 4.16 as our full model. As a rule of thumb, the full model should not include more than one predictor and/or interaction for every ten data points (some people would say for every 20 data points). We have 6 predictors (treating each interaction as a predictor) and 100 data points, so we are probably safe. Some of the predictors in 4.16 ( _e.g_ ., english) do not have significant effects on the response variable. So, we have no reason to believe that they help to explain the response. Our goal is to remove these from the model one-by-one until only significant predictors remain. It is important to remove predictors one-by-one because, when we remove one predictor, the significance of other predictors can change. Removal is a stepwise process, where in each step we remove one predictor according to the rules:

1. Remove the predictor or interaction with the largest p-value, but

2. Do not remove a predictor while any of its interactions remain in the model.

We repeat these steps until we are left with a model that includes only significant predictors (or, only significant predictors and insignificant predictors that are part of significant interactions).

Let’s apply this approach to the model in 4.16. The full model is

60

> s.lm=lm(wage~mc_school+mc_age+male+english+mc_age*mc_school+ (4.17) mc_age*male,data=ci)

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept)      12.78174    1.73361   7.373 6.77e-11 *** mc_school         0.80202    0.20431   3.926 0.000166 *** mc_age            0.03816    0.07197   0.530 0.597183 male              4.90329    1.18223   4.147 7.42e-05 *** english           0.01197    1.65130   0.007 0.994231 mc_school:mc_age  0.03079    0.01795   1.715 0.089657 . mc_age:male       0.35812    0.09508   3.766 0.000290 ***

The predictor with the largest p-value is english. So, we remove this from the model.

s.lm=lm(wage~mc_school+mc_age+male+mc_age*mc_school+ mc_age*male,data=ci)

(4.18)

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept)      12.79237    0.92029  13.900  < 2e-16 *** mc_school         0.80235    0.19826   4.047 0.000106 *** mc_age            0.03808    0.07062   0.539 0.591056 male              4.90273    1.17336   4.178 6.57e-05 *** mc_school:mc_age  0.03079    0.01785   1.725 0.087835 . mc_age:male       0.35822    0.09347   3.832 0.000229 ***

Now, the predictor with the largest p-value is mc_age. But, mc_age is part of a significant interaction with male, so we cannot remove it. The next largest p- value is associated with the interacton mc_school:mc_age. Should we remove this? There is some debate about this. When we remove a variable, we are saying that we think it has no effect on the response variable. With a p-value of 0.087835, we cannot be confident that there is an effect, but we cannot be confident that there is _not_ an effect either. My preference is to leave it, but then to be very cautious when interpreting it. Since there is nothing else for us to remove, the “best” model by backward selection is the model in 4.18.

If we want to obtain p-values for predictors that we have removed from the model, it is best to add each one back into the best model by itself and record its p-value when it is the only “extra” predictor in the model. That way, the p- value for predictors that we have removed is not confounded by other predictors that have also been removed from the model.

According to the best model selected above, we should infer that several predictors and their interactions affect hourly wage. How do we present this information to the reader? When a model includes multiple predictors, figures can be misleading and difficult to understand, so it is often clearest to present results in tables. For this analysis, the body of the text we might write, “We found a significant positive effect of education on hourly wage (b = 0.80 C$ h<sup>-1</sup> y<sup>-1</sup> ,

61

p = 0.0001; table 4.1). Men earned higher wages than women of similar age and education (b = 4.90 C$ h<sup>-1</sup> , p < 0.0001). We found a significant positive effect of age on hourly wage in men (b = 0.40 C$ h<sup>-1</sup> y<sup>-1</sup> , p < 0.0002) but not in women (p = 0.5911), and we found a weakly significant positive interaction between age and education (b = 0.03 C$ h-<sup>1</sup> y<sup>-1</sup> y<sup>-1</sup> , p = 0.0878). We found no effect of native language on hourly earnings (p = 0.9942).”

|**Predictor**|**Effect size**|**t-statistic**|**p-value**||
|---|---|---|---|---|
|intercept|12.79 C$ h<sup>-1</sup>|13.90|<0.0001|**Table 4.1. Predictors**|
|education|0.80 C$ h<sup>-1</sup>y<sup>-1</sup>|4.047|0.0001|**of hourly wage**<br>|
|age|0.04 C$ h<sup>-1</sup>y<sup>-1</sup>|0.539|0.5911|**among workers in**<br>**Ontario Canada in**|
|sex|4.90 C$ h<sup>-1</sup>|4.178|<0.0001|**,**<br>**1994.**|
|age by education|0.03 C$ h<sup>-1</sup>y<sup>-1</sup>y<sup>-1</sup>|1.725|0.0878||
|age by sex|0.36 C$ h<sup>-1</sup>y<sup>-1</sup>|3.832|0.0002||

Sometimes researchers may want to include a predictor in their linear regression even if it is not significant. For example, perhaps we are studying how body mass in goslings depends on the height of their parents’ nest on a cliff face. Perhaps we know from a large body of existing research that body mass in goslings differs by sex. So, we might want to control for sex by including it as a predictor in the model. If we find that the relationship between sex and body mass in our model is not significant, that does not mean that body mass does not differ by sex. We already know it does based on past research. The fact that we did not detect a relationship may just mean we did not have enough statistical power to detect it. So, we might want to include this predictor in our model anyway, to ensure that we are controlling for any effects it _might_ have. We call this _forcing_ the predictor into the model. This is fine, and it can even be a very good approach to analysis. But, it is important the we make the decision about whether we will force some predictors into the model based on our knowledge of the system before we begin examining the data. If we examine the data and then decide which predictors to include in

an unprincipled way, it will be very difficult to convince readers that we have not cherry-picked our results. In fact, it might even be hard to convince ourselves of that!

#### **Collinearity**

The data set we have been working with includes a potential predictor apt, or “academic aptitude,<sup>4</sup> ” that we have not yet considered. Academic aptitude is a measure of an individual’s ability to succeed in

<!-- Start of picture text -->
40 60 80 120 160<br>academic aptitude<br>18<br>14<br>10<br>years of education<br>8<br><!-- End of picture text -->

**<mark>Figure 4.6. Academic aptitude predicts years of formal education.</mark>**

> 4 Remember from footnote 2 that I made this data up. All of the rest of the data in this data set are real, but the academic aptitude data are fake. Academic aptitude may be a real thing, but measuring would be difficult and we do not have that data for this system!

62

school. We might expect apt to be closely related to years of education, since students who achieve highly might stay in school longer. To see whether this is true, we can look at a scatter plot of years of education as a function of academic aptitude (figure 4.6 on the previous page). In this figure, we see that academic aptitude and years of education are strongly correlated – that is, one clearly predicts the other. In fact, the R<sup>2</sup> for the relationship is 0.96, which means that academic aptitude explains about 96% of the variability in education. We call strong correlation between two variables _collinearity_ .

Let’s add mean centred academic aptitude to the best model we selected above

mc_apt=ci$apt-mean(ci$apt) s.lm=lm(wage~mc_school+mc_age+male+mc_age*mc_apt+mc_age*male +mc_apt,data=ci) summary(s.lm)

…

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept)   12.803646   0.925291  13.837  < 2e-16 *** mc_school      0.075132   0.945027   0.080 0.936804 mc_age         0.039207   0.070966   0.552 0.581951 male           4.909340   1.178884   4.164 6.97e-05 *** mc_apt         0.074458   0.093859   0.793 0.429621 mc_age:mc_apt  0.002465   0.001682   1.466 0.146005 mc_age:male    0.355114   0.093887   3.782 0.000275 ***

The addition of mc_apt to the model appears to change everything! Now, neither school nor academic aptitude appear to affect hourly wage. If we go through backward selection, we would first remove mc_school

> s.lm=lm(wage~mc_age+male+mc_age*mc_apt+mc_age*male+mc_apt, (4.20) data=ci)

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept)   12.802533   0.920282  13.912  < 2e-16 *** mc_age         0.039642   0.070380   0.563 0.574596 male           4.910741   1.172505   4.188 6.34e-05 *** mc_apt         0.081752   0.019707   4.148 7.34e-05 *** mc_age:mc_apt  0.002456   0.001669   1.472 0.144385 mc_age:male    0.355011   0.093381   3.802 0.000255 ***

and then in the next step remove the interaction between mc_age and mc_apt

63

(4.21)

s.lm=lm(wage~mc_age+male+mc_age*male+mc_apt,data=ci)

Coefficients:

Estimate Std. Error t value Pr(>|t|) (Intercept) 12.72998    0.92459  13.768  < 2e-16 *** mc_age       0.02576    0.07017   0.367 0.714358 male         4.96233    1.17915   4.208 5.83e-05 *** mc_apt       0.09115    0.01876   4.860 4.64e-06 *** mc_age:male  0.35298    0.09394   3.757 0.000296 ***

The main effects in this new “best” model seem to be mostly the same. The expected hourly wage for a woman of average academic aptitude is C$12.72 h<sup>-1</sup> (compared to in C$12.79 h<sup>-1</sup> the previous “best” model with mc_school), the effect of being male is C$4.96 h<sup>-1</sup> (compared to in C$4.90 h<sup>-1</sup> previously), and the effect of age on male hourly wage is C$0.38 h<sup>-1</sup> y<sup>-1</sup> (compared to in C$0.40 h<sup>-1</sup> y<sup>-1</sup> previously). The interaction between education and age has disappeared, but we did not have confidence in that relationship anyway. The big change is that the effect of years of education has now been replaced by an effect of academic aptitude.

So, does this mean that academic aptitude rather than years of formal education affects hourly wage? Not necessarily. When two or more variables are highly collinear, we may not be able to untangle their effects. Perhaps academic aptitude affects both years of education and hourly wage. Or, perhaps academic aptitude affects years of education, and years of education affects hourly wage. Perhaps both academic aptitude _and_ years of education affect hourly wage. Or, perhaps all three of them are affected independently by some other variable that we have not measured in our study. We will have to settle for the conclusion that academic aptitude, years of education, and hourly wage are strongly correlated, and that we cannot assign causality.

In general, when two predictors are highly collinear, it is often best to select _a priori_ the predictor we are most interested in studying, and to include only that predictor in the model. Our results will tell us whether that predictor is correlated with the response variable. Then, in our discussion, we can admit that the mechanism that drives the correlation might involve the other predictor. For example, in this case we might report, “We found a strong positive correlation between years of education and expected hourly wage in both men and women. However, academic aptitude closely predicts years of education (R<sup>2</sup> = 0.96). Therefore, we cannot rule out the possibility that the effect on hourly wage is driven by academic aptitude rather than by greater education.”

#### **Assumptions of linear regression**

Linear regression analysis relies on a number of assumptions about the data being analysed. There are advanced techniques for dealing with violations of these assumptions, but most of these are beyond the scope of this handbook. Here, we will identify the four key assumptions and point out a few simple methods we might use for dealing with some special types of violations.

64

_1. Linear regression assumes that the data points are independent_ . This means that the value of the response variable for any one data point does not depend on the value of the response variable for any other. One common case in which this assumption violated is in time series data. For example, imagine that we are studying closing prices on the New York Stock Exchange. In general, the opening price on one day is similar to the closing price on the day before. So, the prices on consecutive days are not independent. This is called _temporal autocorrelation_ . Sometimes, we can make time series data independent. For example, perhaps we can study the change in price for each day instead of the closing price. But, this won't work if the market experiences trends – that is, if it usually goes up or goes down for several days in a row.

The field of time series analysis was developed to allow researchers to analyse temporally autocorrelated data, but we will not study time series statistics in this unit. In your field courses, it may be be ~~s~~ t to ensure that your data points are independent with careful experimental ~~d~~ esign.

_2. Linear regression assumes that predictors have linear effects on the response variable_ . Consider the data in figure 4.7a. Femur length is a good predictor of brain volume, but it is _not_ a linear predictor. If we fit a straight line to the data, it will do a poor job of predicting the value of brain volume. Violations of the linearity assumption can sometimes be addressed by _transforming_ variables. To transform a variable, we adjust the value of that variable for each data point according to some mathematical formula. Often, there is a strong theoretical reason to choose a particular transformation. For example, in the case of femur length and brain volume, we can imagine what would happen if we were simply to scale up an animal’s body size. If we multiply and animal’s height by a factor of _x_ without changing the relative size of its body parts, then we would expect its femur

<!-- Start of picture text -->
a<br>2 4 6 8 10 12<br>femur length<br>b<br>2 4 6 8 10 12<br>femur length<br>1000<br>400<br>brain volume<br>0<br>8<br>6<br>4<br>2<br>brain volume^(1/3)<br><!-- End of picture text -->

<!-- Start of picture text -->
Figure 4.7. Brain volume (a) and the<br>cube root of brain volume (b) as<br>functions of femur length.<br><!-- End of picture text -->

**Figure 4.7. Brain volume (a) and the cube root of brain volume (b) as functions of femur length.**

length to increase by a factor of _x_ . But, if we increase an animal’s height by a factor of _x_ without changing its proportions, then we would also expect its width and depth to increase by factors of _x_ . Volume is a three-dimensional measure. For example, a brain has a height, a width, and a depth. So, brain volume would increase by a factor of _x_<sup>3</sup> . In figure 4.7b we plot the cube root of brain volume as a function of femur length, and the relationship is close to linear. So, we can use linear regression to study the cube root of brain volume as a function of femur length.

_3. Linear regression assumes that unexplained variability in fitted model is approximately normally distributed_ . Many people believe that linear regression

65

requires response values and/or predictor values to be normally distributed. This is incorrect. What linear regression does assume is that the unexplained variability (sometimes called the _error_ , or _residual error_ ) in the fitted model is approximately normally distributed.

When we build a linear regression in R, the unexplained variability associated with each data point is stored in a vector of _residuals_ . We could formally test whether these residuals are normally distributed, but it is seldom worth the effort. If the data set is small, formal tests will fail to detect even large deviations from normality. If the data set is large, formal tests will detect

**Figure 4.** **~~8~~ . Histogram of the residuals of the best** **~~<u><mark>m</mark></u>~~** **<u><mark>odel</mark> of hourly wage</u>** **<u><mark>from</mark></u> code 4.18.** -15 -5 0 5 10 15 20 resid(s.lm)

deviations from normality even if those deviations are too small to affect the regression analysis. So, a better way to see whether the residuals are approximately normally distributed is simply to look at them.

Let’s create a histogram of the residuals of the best model for our hourly wage data

hist(resid(s.lm),20)

Here resid(s.lm) indicates the residuals of the model s.lm we built in code 4.16, and 20 tells R to divide the values into 20 bins. The result is figure 4.8. Even at a glance, the distribution in figure 4.8 does not look normal. In particular, it seems to have a long right tail.

Sometimes, we can remedy non-normal residuals by transforming the response variable. One common approach for distributions with long right tails is to log transform the response. For example, figure 4.9 shows the residuals of a model fitted to the raw (4.9a) and the log-transformed (4.9b) response variable in a simulated data set. (I have not provided the data set for these figures.) Here, log transformation _normalises_ the residuals.

To log-transform the response variable in our hourly wage data, we can create a new variable that is the logarithm of the original (raw) response.

ln_wage=log(ci$wage)

Then, we repeat our backward selection process from the beginning. Since we have walked through backward selection above, I will not show that again here. We will find that the best model is

> s.lm=lm(ln_wage~mc_school+mc_age+male+mc_age*male,data=ci) (4.24)

If we plot a histogram of the residuals (figure 4.10), it _might_ be better. It still has long tails, but now they are on

66 -0.6 -0.2 0.0 0.2 0.4 0.6 **Figure 4.10. Histogram of the best model of log(hourly wage).** resids

both sides. Symmetry is a step in the right direction. Moreover, there may be a theoretical reason for log transforming wage data: earnings gaps are often larger in absolute terms at the upper end of the earnings spectrum. For example, in UK academia, the gap between pay points for qualified lecturers are about £700 per year, but the gaps between pay points at the upper end of the leadership and management pay scale are about £2,800 per year, and university vice chancellors often receive pay packages that are several hundred thousand pounds per year larger than the academics who deliver teaching and research<sup>5</sup> . So, it might make sense to revisit our analysis of the Canadian income data using log-transformed wage as a response variable. And, if we are not sure which approach is better, we might want to do the analysis both ways to see if the results are the same.

_Outliers_ are a special form of deviation from normality. Outliers are data points with residuals that are abnormally large compared to the rest of the data. The two right-most residuals in figure 4.8 might be outliers. Outliers are important because they can strongly affect the model fitting. For example, in figure 4.11, the red line shows the best fit of the predictor to the response variable if we include all of the data. The black line shows the best fit if we ignore the point [3.9, 2.0]. The model fits most of the data better if we ignore the outlier.

<!-- Start of picture text -->
2.0 2.5 3.0 3.5 4.0<br>predictor<br>5.0<br>response 4.0<br>3.0<br>2.0<br><!-- End of picture text -->

**Figure 4.11. Scatter plot of simulated data, with lines of best fit that ignore (black) or include (red) and outlier.**

We cannot ignore an outlier just because we do not like how it affects our results. That would mean ignoring evidence because we do not like what it tells us, which is not scientific. However, we might have an _a priori_ reason to doubt one or more of our data points. For example, perhaps we are interested in how activity at an ant colony depends on temperature. On each of 15 days, we count the number of ants leaving a colony during one minute. On one of these days, it was raining. If we do not know whether rain affects ant activity, we might initially leave the data point in our analysis. But, if that point turns out to be an outlier, this might indicate that ants do something fundamentally different in the rain, and the data point from the rainy day might not accurately reflect the pattern we observed on sunny days. In this case, we might consider excluding the data point, and then restricting our interpretation to sunny days. If we do exclude an outlier, we will need to justify that decision carefully in our methods.

In the case of our wage data, there does not appear to be an easy transformation that will fully normalise the residuals, and we have no strong justification for excluding potential outliers. So, the unexplained variability in the response variable will have to remain non-normal, and the normality assumption of the regression model will be violated. What can we do? In this

> 5 But don’t worry! The VCs assure us that they are worth every penny that we (well, _you_ really) pay them, and they must be experts on this or they wouldn’t get such big salaries!

67

case, we probably do not need to worry. Look again at table 4.1. The estimation of effect sizes in linear models does not depend on the normality assumption, but p-values do. Since our residuals are not normally distributed, we cannot be confident that our p-values are exactly accurate. But, the p-values associated with education, sex, and the age by sex interaction in our model are extremely small. Even if these p-values change by two orders of magnitude, the results will remain significant. So, we can be confident of these results. The effect of the age by education interaction is less significant, and we will have to admit to our reader that we cannot have much confidence in this effect. But, we would not have much confidence in this effect even if the residuals were normally distributed, because the p-value was already quite large. So, the violation of the normality assumption does not affect the interpretation of our results.

_4. Finally, linear regression assumes that unexplained variability in the fitted model is homoscedastic_ . Homoscedasticity means that every data point has the same expected error. This is analogous to the assumption of equal variance in t-tests and ANOVA. A quick way to check for homoscedasticity is to plot residuals as a function of the model predictions for every data point. For our hourly wage model, we can do this using

plot(predict(s.lm),resid(s.lm))

The result is figure 4.12 on the next page. We may have a violation of the homoscedasticity assumption in our model. When the predicted wage is low, the prediction is very accurate, but when the predicted wage is higher the unexplained variability in the response increases. Unevenness in the unexplained variability across the data set is called _heteroscedasticity_ . Sometimes, a simple transformation will remove heteroscedasticity. When unexplained variability increases with the predicted response, a log transformation will sometimes help.  If transformation does not help, researchers sometimes deal with heteroscedasticity by weighting variance, but this is an approach we will not cover here.

<!-- Start of picture text -->
Figure 4.12. Residuals<br>plotted as a function of<br>predicted response in<br>the best model of<br>hourly wage.<br>10 15 20 25 30 35<br>predict(s.lm)<br>15<br>5<br>0<br>resid(s.lm)<br>-5<br>-15<br><!-- End of picture text -->

Just as with violations of normality, a slight violation of the homoscedasticity assumption may not be fatal to an analysis. However, if we know that our data are heteroscedastic, we will want to interpret our results

68

with caution. For example, we might require smaller p-values before we infer a relationship between the predictor and response variables.

#### **Rank correlation tests**

If assumptions 2 to 4 above are badly violated and we cannot correct the problems with transformations, then we may wish to consider a rank correlation test instead of a linear regression. Rank correlation tests are similar to the Wilcoxon and Kruskal-Wallis tests that we considered in previous chapters. In this case, instead of looking for a relationship between the predictor and response values, we rank the predictor and response values and look for a relationship between their ranks. The tests ask whether the response is a _monotonic function_ of the predictor: that is, does the response value consistently increase or decrease with the predictor? Rank correlation tests do not assume that the relationship between the predictor and response variables is linear, and they do not allow us to predict response values based on predictor values. But, they can tell us whether two variables tend to increase or decrease together.

The most well-known rank correlation test is Spearman’s r test. We can implement this in R using

cor.test(ci$wage,ci$school,method="spearman", alternative="greater")

Spearman's rank correlation rho

data:  ci$wage and ci$school S = 118738.6, p-value = 0.001864 alternative hypothesis: true rho is greater than 0 sample estimates: rho 0.2874973 Warning message: In cor.test.default(ci$wage, ci$school, method = "spearman", alternative = "greater") : Cannot compute exact p-value with ties Here, the first two arguments of cor.test are the response and predictor we wish to study, and the third argument tells R to apply Spearman’s rtest. The text alternative="greater" tells R that our a priori hypothesis is that the predictor and response variables are positively correlated, and thus that we should use a one-tailed test. If our hypothesis were that the variables are negatively correlated, we would use alternative="less", and if we had no _a priori_ expectation we would simply omit this term. The warning message tells the user that the p-value cannot be calculated exactly if there are ties in the rankings ( _i.e_ ., if there are duplicate values in the predictor or the response). However, there is no need to be alarmed. The p-values for the correlation can still be estimated, and the estimates are very accurate. R reports these estimates. As in our linear model, we find strong evidence for a relationship between wage and education.

69

Kendall’s t test is an alternative to Spearman’s r test. It is less commonly used, but has the advantage of being slightly easier to interpret. For Kendall’s  t test , the test statistic (ie, t ) is _concordance_ . If we were to randomly select two observations from our data set and compare two measures between them, the concordance is the probability that the observation with the higher value of the first measure also has the higher value of the second. To put this in terms of our Canadian income example, imagine that we randomly selected two individuals from our data set, and we compare their ages and their wages. The concordance is the probability that the individual with the higher age also has the higher wage. Because concordance is easy to understand, I often prefer Kendall’s t test to Spearman’s r test. But, they almost always produce similar results!

70

### **Chapter 5. Categorical responses to categorical predictors**

In the data sets we have considered so far, the predictors have been either categorical or numerical, but the response variables have always been numerical. That is, the response has been measured and reported as a number. However, in some kinds of experiments, the responses are categorical. How do we analyse this kind of data? Let’s consider an example.

The data set “spiders.csv” on Dropbox contains observations of mate choice by female wolf spiders ( _Schizocosa uetzi_ ). Males of this species can have either dark forelegs or light forelegs (Shamble et al. 2009) (Figure 5.1). The dark foreleg is believed to be a sexual ornament that attracts the attention of females during courtship (Scheffer et al. 1996). In the experiment from which

<!-- Start of picture text -->
Figure 5.1. Dark and light foreleg<br><!-- End of picture text -->

**Figure 5.1. Dark and light foreleg phenotypes of male** **_S. uetzi_ .** Photos from Shamble _et al_ . (2009).

these data were taken, a female spider was presented with one dark-legged male and one light-legged male, and she was allowed to choose a mate. This was repeated with 80 different females. Trials were conducted either in the light or in the dark. Moreover, the 80 females were collected from three different substrates: grass, leaf litter, or rocks. It is believed that females with different genotypes use different substrates, and that a female’s genotype may influence her mate preference (Gilman et al. 2019).

The data in “spiders.csv” looks like this

spiders=read.csv("spiders.csv",header=TRUE) spiders

chose    trial  origin 1   dark leg    light   rock 2   dark leg    light   rock 3   dark leg    dark    rock 4   dark leg    light   rock 5   dark leg    light   rock 6   dark leg    light   grass 7  light leg    light   grass

…

#### **Testing for deviations from** **_a priori_ expectations**

The simplest question we might ask of our data is whether females chose dark-legged males more often than we would expect by chance. To find out how many females chose dark-legged males, we can use

71

sum(spiders$chose=="dark leg")

(5.2)

##### [1] 59

As we saw in earlier chapters, the code spiders$chose=="dark leg" creates a new vector of the same size as spiders$chose with a TRUE for every entry where the choice was"dark leg" and a FALSE everywhere else. The command sum counts the TRUEs in this vector. The answer tells us that 59 females chose darklegged males as mates. Because we know that there were 80 females in the experiment (we can use length(spiders$chose) to confirm this), we know that 21 females chose light-legged males as mates. If females were equally likely to choose dark-legged or light-legged males, what is the probability that at least 59 females would have chosen dark-legged males by chance alone?

Let’s imagine that, in any given mating trial, a female has some probability _p_ of choosing a dark-legged male. If we consider just one mating trial, the probability that the female chooses a dark-legged male is _p_ , and the probability that she chooses a light-legged male is (1- _p_ ).

If we consider two mating trials, the two females together might choose two, one, or no dark-legged males. The probability that both females choose dark-legged males is _p_ x _p_ = _p_<sup>2</sup> . So, with probability _p_<sup>2</sup> , two dark-legged males will be chosen. The probability that the first female chooses a dark-legged male and the second chooses a light legged male is _p_ (1 – _p_ ). In this case, one darklegged male is chosen. But, there is another way that one dark-legged male might be chosen. The first female might choose a light-legged male and the second might choose a dark-legged male. This occurs with probability (1 – _p_ ) _p_ , which is the same as _p_ (1 – _p_ ). So, altogether, the probability that one dark-legged male is chosen is 2 _p_ (1 – _p_ ). Finally, the probability that neither female chooses a darklegged male is (1 - _p_ )(1 - _p_ ) = (1 – _p_ )<sup>2</sup> . We can make this easier to see by putting it in a table:

|**Dark-legged**<br>**males chosen (****_k_) **|**Probability of**<br>**any one**<br>**realisation**|**Possible**<br>**realisations**|**Number of**<br>**possible**<br>**realisations**|**Total probability**|
|---|---|---|---|---|
|2|_p_<sup>2</sup>|DD|1|_p_<sup>2</sup>|
|1|_p_(1 -_p_)|DL, LD|2|2_p_(1 -_p_)|
|0|(1 -_p_)<sup>2</sup>|LL|1|(1 -_p_)<sup>2</sup>|

We can create a similar table for three mating trials

|**Dark-legged**<br>**males chosen (****_k_) **|**Probability of**<br>**any one**<br>**realisation**|**Possible**<br>**realisations**|**Number of**<br>**possible**<br>**realisations**|**Total probability**|
|---|---|---|---|---|
|3|_p_<sup>3</sup>|DDD|1|_p_<sup>3</sup>|
|2|_p_<sup>2</sup>(1 -_p_)|DDL, DLD, LDD|3|3_p_<sup>2</sup>(1 -_p_)|
|1|_p_(1 -_p_)<sup>2</sup>|DLL, LDL, LLD|3|3_p_(1 -_p_)<sup>2</sup>|
|0|(1 -_p_)<sup>3</sup>|LLL|1|(1 -_p_)<sup>3</sup>|

72

for four mating trials

|**Dark-legged**<br>**males chosen (****_k_) **|**Probability of**<br>**any one**<br>**realisation**|**Possible**<br>**realisations**|**Number of**<br>**possible**<br>**realisations**|**Total probability**|
|---|---|---|---|---|
|4|_p_<sup>4</sup>|DDDD|1|_p_<sup>4</sup>|
|3|_p_<sup>3</sup>(1 -_p_)|DDDL, DDLD,<br>DLDD, LDDD|4|4_p_<sup>3</sup>(1 -_p_)|
|2|_p_<sup>2</sup>(1 -_p_)<sup>2</sup>|DDLL,DLDL,<br>LDDL, DLLD,<br>LDLD, LLDD|6|6_p_<sup>2</sup>(1 -_p_)<sup>2</sup>|
|1|_p_(1 -_p_)<sup>3</sup>|DLLL, LDLL,<br>LLDL, LLLD|4|4_p_(1 -_p_)<sup>3</sup>|
|0|(1 -_p_)<sup>3</sup>|LLLL|1|(1 -_p_)<sup>4</sup>|

and so on. If we want to know the probability of seeing _at least k_ dark-legged males chosen in _n_ trails, we can simply sum up the appropriate cells in the last column of the appropriate table. This is called a _binomial test_ , because the distribution in the last column of tables above is binomial.

Fortunately, we do not have to do binomial tests by hand, because R will do them for us. To do a binomial test for our spider data, we use

binom.test(59,80,0.5,alternative="greater")

Exact binomial test

data:  59 and 80 number of successes = 59, number of trials = 80, p-value = 1.265e-05 alternative hypothesis: true probability of success greater than 0.5 95 percent confidence interval: 0.6444349 1.0000000 sample estimates: probability of success 0.7375

The argument 59 in code 5.3 is the number of dark-legged spiders chosen, and the argument 80 is the total number of mating trials. The next argument, 0.5, is the null hypothesis we are testing. If leg colour were not related to mate choice, then females would be equally likely to choose either dark or light-legged males. (If every mating trail had one light-legged and two dark-legged males, we would use 2/3 here instead.) Finally, we used alternative="greater" because our _a priori_ hypothesis was that females prefer dark-legged males. Therefore, we want to find the probability of seeing 59 or more dark-legged males chosen by chance alone. If we had had no _a priori_ expectation, we could have omitted this code to get a two-tailed significance test. The p-value in the output of 5.3 is the p-value associated with our hypothesis test. The probability of success is the best estimate for the probability that females choose dark-legged males. We can think of this as a measure of female preference. Notice that 0.7375 = 59/80, so the best

73

estimate for the probability of choosing a dark-legged male is simply the observed value.

The binomial test assumes that observations result from independent trials. That is, in our spider data, the test assumes that the mate choice made by any one female does not affect the choice made by any other. The binomial test is an _exact test_ . That means that the p-value is calculated exactly, and not estimated from a distribution. Because it is an exact test, the accuracy of p-values calculated by the binomial test does not depend on the sample size. So, we can use the binomial test even if we have small numbers of observations.

If the sample size is sufficiently large, we have another option for testing deviations from a priori expectations: the _chi-squared goodness of fit test._ The chisquared goodness of fit test works by comparing the number of observed responses of each type (in our example, dark- and light-legged males) to the number of expected responses of each type. We observed the following

||**Dark-legged**<br>**males chosen**|**Light-legged**<br>**males chosen**|**Total choice**<br>**trials**|
|---|---|---|---|
|**Observed**|59|21|80|

If the null hypothesis is that females are equally likely to choose dark- and lightlegged males, then the expected number of responses would be

||**Dark-legged**<br>**males chosen**|**Light-legged**<br>**males chosen**|
|---|---|---|
|**Expected**|0.5 x 80 = 40|0.5 x 80 = 40|

We calculate a test statistic by taking the difference between the observed and expected value in each cell, squaring that difference, dividing by the expectation for that cell, and summing across the whole table. Here, the test statistic would be (59 - 40)<sup>2</sup> /40 + (21 – 40)<sup>2</sup> /40 = 18.05. If we were to generate data randomly under the null hypothesis, the test statistic would follow a chi-squared distribution with _C_ – 1 degrees of freedom, where _C_ is the number of cells in the table. We can compare our observed test statistic to this distribution to find the probability that we would see a value at least as large as the one we observed by chance alone. The chi-squared goodness of fit test is reasonably accurate as long as the expected number of observations in every cell is greater than 5. So, a chisquared test should be fine for our spider data.

As with the binomial test, R can do a chi-squared test for us. For our spider data, we would use

74

(5.4)

> chisq.test(c(59,21),p=c(0.5,0.5))

Chi-squared test for given probabilities

data:  c(59, 21) X-squared = 18.05, df = 1, p-value = 2.152e-05

In code 5.4, the text c(59,21) tells R to create a vector with two entries, 59 and 21. These are the observed numbers of dark- and light-legged males chosen in the spider data. The vector p contains the expected probabilities of each outcome (here, 0.5 because we are testing the null hypothesis that females treat each male phenotype equally). The p-value here is approximately twice that produced by the binomial test, because the chi-squared always test is two-tailed.

One advantage to the chi-squared test goodness of fit test over the binomial test is that we can use the chi-squared test when there are more than two possible responses. For example, we can imagine a case where each female has three male phenotypes to choose from instead of two. In some wolf spider species, males can have light forelegs, dark forelegs, or forelegs that are ornamented with tufts of hair. If 13 females chose light-legged males, 28 choose dark-legged males, and 39 choose tufted males, then we could conduct a chisquared test using

chisq.test(c(13,28,39),p=c(1/3,1/3,1/3))

Chi-squared test for given probabilities

data:  c(13, 28, 39) X-squared = 12.775, df = 2, p-value = 0.001682

#### **_Post hoc_ testing for differences among responses**

The chi-squared test in 5.5 tells us that females did not choose the three male phenotypes in the experiment with equal probability. However, because the test statistic is calculated for the entire data set and not for specific pairs of responses, the test does not tell us which specific phenotypes are chosen more frequently than which others. We can find out using pairwise comparisons. As with ANOVA, pairwise comparisons create a multiple testing issue. There are three different pairwise comparisons that we can make in our example: tufted vs. dark-legged, tufted vs. light-legged, and dark-legged vs. light-legged. If we use a 0.05 cut-off to infer a significant difference in each pairwise comparison, then the probability that we will see a difference due to chance alone in at least one of the comparisons is greater than 0.05. To avoid this problem, we can use a _Bonferonni correction_ , an approach first advocated by Olive Jean Dunn.

To implement a Bonferroni correction, we divide the cut-off that we will use to infer significance by the total number of pairwise comparisons that we will make. So, in our example, we would require a p-value of less that 0.05/3 = 0.0167 in any single pairwise comparison to infer a difference between that pair of responses. To obtain the pairwise p-values, we apply binomial tests or chi-

75

squared tests to the specific pairs. For example, to compare the probabilities that tufted-legged and dark-legged males were chosen, we would use

chisq.test(c(39,28),p=c(1/2,1/2))

Chi-squared test for given probabilities

data:  c(39, 28) X-squared = 1.806, df = 1, p-value = 0.179

In the same way, we would obtain p =  0.0192 for dark-legged vs. light-legged males and p = 0.0003 for tufted-legged vs. light-legged males. From these comparisons, we can infer that tufted-legged males are chosen more frequently that light-legged males. Because 0.01915 is greater than 0.05/3 but less than 0.10/3, we have only weak evidence that dark-legged males are chosen more frequently than light-legged males. We have no evidence that tufted-legged males are chosen differently from dark-legged males.

When we use a Bonferonni correction, each additional pairwise comparison that we make lowers the threshold p-value that we will consider significant in all of the comparisons. Thus, every additional comparison makes it harder to infer results from the other comparisons. To limit this cost of the Bonferonni correction, researchers sometimes decide _a priori_ that they will consider only a subset of the pairwise comparisons in a given study. For example, in some wolf spider species, tufted forelegs are always dark. If this were true in our species, then we might be interested in only two of the pairwise comparisons in the study: tufted-legged vs. dark-legged (which would tell us whether there is an effect of tufts) and dark-legged vs. light-legged (which would tell us if there is an effect of colour). If we make only two pairwise comparisons, then our cut-off for inferring an effect would be 0.05/2 = 0.025 rather than 0.05/3 = 0.0167. It is important to note however that the decision of which pairwise comparisons to make _must_ be made before the data are collected. We would unfairly bias our results if we were to collect data, recognise (or guess) which responses are difference, and then use pairwise comparisons on only those responses.

#### **Reporting differences among responses**

In the example above, our hypothesis is about proportions. We asked what proportion of females chose dark-legged males, and whether this is greater than we would expect to see due to chance alone. One intuitive way to present proportional data is with pie charts. We can create a pie chart in R using

slices=c(39,28,13) lbls=c("tufted (39)","dark (28)","light (13)") pie(slices,lbls)

Here, slices tells R how many observations are represented by each slice of the pie, and lbls tells R how to label each slice. I included the number of

76

observations for each response in the label to make it easier for readers to compare among slices. The result is shown in figure 5.2a.

Some authors prefer bar charts to pie charts, because it is easier to compare the responses visually. We can make a bar chart in R using

lbls=c("tufted","dark","light") barplot(slices,names=lbls,ylim=c(0,40),ylab="frequency")

- I removed the numbers from the column names, because with the scale on the _y_ axis we do not need them. I used ylim=c(0,40) to make the _y_ -axis to run from 0 to 40 because (annoyingly!) R truncated the axis at 30 when I let it choose the axis limits itself. The result is shown in figure 5.2b. I added the brackets for the pairwise comparisons to the figure manually.

Some authors argue that pie charts are more intuitive than bar charts for presenting proportional data. Because our results are proportions, the total across all responses must sum to one.  So, if the proportion of one response increases, then the proportion of another must decrease. This is true in pie charts, but not in bar charts. Ultimately, the choice of how to present your results is up to you as the author. But, do not be tempted to use both a pie chart and a bar chart! There is no need to report the same result in two different figures.

Our results must also be reported in the text. In this case, we might write, “Females did not choose males of all phenotypes equally <mark>(c</mark><sup>2</sup> <mark>= 12.77,</mark> **a** tufted (39) <mark>df = 2, p = 0.0017). We found strong evidence that females chose males with tufted legs more often than males with light legs (c</mark><sup>2</sup> <mark>= 13, df = 1, p = 0.0003, Bonferonni-</mark> light (13) <mark>adjusted significance cut-off</mark> dark (28) <mark>a</mark> _B_ <mark>= 0.0167), and weak evidence</mark> **b** <mark>that females chose males with dark</mark> ~~*~~ <mark>legs more often than males with</mark> ~~°~~ <mark>light legs (c</mark><sup>2</sup> <mark>= 5.49, df = 1, p = 0.0192, a</mark> _B_ <mark>= 0.0167). We found no evidence than female chose males with tufted legs differently from males with dark legs (c</mark><sup>2</sup> <mark>= 1.81, df = 1, p = 0.179, a</mark> _B_ <mark>= 0.0167).” Notice that we defined a</mark> _B_ <mark>the first time we used it. There is no standard abbreviation</mark> tufted dark light <mark>for the Bonferonni-adjusted</mark> **Figure 5.1. Pie chart (a) and bar chart (b) showing** <mark>significance cut-off, so the reader</mark> **the frequencies of males with three different phenotypes chosen as mates by female wolf** <mark>will not know what a</mark> _B_ <mark>means</mark> **spiders in forced-choice trials** . In ( **b** ), * indicates a <mark>unless we define it.</mark> ° indicates a  indicates a

<!-- Start of picture text -->
Figure 5.1. Pie chart (a) and bar chart (b) showing<br>the frequencies of males with three different<br>phenotypes chosen as mates by female wolf<br>spiders in forced-choice trials . In ( b ), * indicates a<br>statistically significant difference, and ° indicates a ° indicates a  indicates a<br>marginally significant difference.<br><!-- End of picture text -->

**Figure 5.1. Pie chart (a) and bar chart (b) showing the frequencies of males with three different phenotypes chosen as mates by female wolf spiders in forced-choice trials** . In ( **b** ), * indicates a statistically significant difference, and ° indicates a ° indicates a  indicates a marginally significant difference.

77

#### **Testing for differences in response frequencies among groups**

In the example above, we were interested in whether some responses in our data set occurred more often than we would expect due to chance alone. However, sometimes we are less interested in the frequency of the responses itself than if that frequency differs among trials. For example, in our spider data, some trials were conducted in the light and others were conducted in the dark. If dark legs are a visual mating signal, then we might expect them to have an effect only when mating trials are conducted in the light. So, we might expect a higher percentage of females to choose dark-legged males in lighted trials than in darkened trials.

To find the number of females that chose light-legged and dark-legged males in lighted and darkened trials, respectively, we can use code of the form

sum(spiders$chose=="dark leg" & spiders$trial=="light")

##### [1] 41

Here, the code (spiders$chose=="dark leg" & spiders$trial=="light") will return TRUE only is the female chose a dark-legged male _and_ the trial was conducted in the light. Then, sum(…) will add up all of the TRUEs in the resulting vector. We can do this for all four combinations and put the results in a _contingency table._

||**light**<br>**trials**|**dark**<br>**trials**|
|---|---|---|
|**dark-legged**|41|18|
|**light-legged**|17|4|

To create this contingency table in R, we can use

choice = matrix(c(41,17,18,4), nrow = 2, dimnames = list(c("dark-legged","light-legged"), c("light trials","dark trials"))) choice

light trials dark trials dark-legged            41          18 light-legged           17           4

Here the command matrix makes a table using the values in c(41,17,18,4), and nrow=2 tells R that the table should have two rows. As R enters values into the table, it starts at the top left and moves down each column. When one column is full, it moves on to the next. The text in dimnames assigns names to the rows and columns.  We could omit names if we wanted to, but I included them because it makes the table easier to understand. I put spaces around the equals signs in the matrix command because it makes the command easier for us to read. R ignores spaces, so you can include them or leave them out as you see fit.

78

At a glance, it looks like there is not much difference in female mate choice in the lighted and darkened trials. In lighted trials females chose darklegged males with probability 41/(41 + 17) = 0.71, and in darkened trials they chose dark-legged males with probability 18/(18 + 4) = 0.82. We can test formally for a difference in these response frequencies using _Fisher’s exact test_ , which like many of the other tests we have studied is due to R. A. Fisher.

The idea behind Fisher’s exact test is similar to that behind the binomial test. Our hypothesis is that females choose dark-legged males more frequently in the lighted trials than in the darkened trials. Fisher’s exact test calculates the probability that the difference in the frequency with which dark-legged males are chosen in the lighted and darkened trials would be at least as large as in the observed data due to chance alone, subject to the constraint that the total number of dark-legged males chosen must be the same as in the observed data. In other words, it assumes that the row totals and column totals in our contingency table cannot change.  So, if ( _d_ , _l_ ) is the number of dark-legged males chosen in darkened ( _d_ ) and lighted ( _l_ ) trials respectively, then Fisher’s exact test calculates the probability that ( _d_ = 41, _l_ = 18) plus the probability that ( _d_ = 42, _l_ = 17) plus the probability that ( _d_ = 43, _l_ = 16), and so on. As its name implies, Fisher’s exact test calculates exact p-values, and therefore it is not sensitive to sample sizes. So, it is not a problem that one of the observed values in the contingency table is less than 5.

To conduct Fisher’s exact test in R, we use

fisher.test(choice,alternative="greater")

Fisher's Exact Test for Count Data

data:  choice p-value = 0.9054 alternative hypothesis: true odds ratio is greater than 1 95 percent confidence interval: 0.1476265       Inf sample estimates: odds ratio 0.539859

Here choice is the contingency table from 5.10. We set alternative to greater because our _a priori_ hypothesis was that females would choose dark-legged males more frequently in lighted trials. If we had been interested only in whether females would choose _differently_ under the two trial conditions, we would have wanted a two-tailed test and we could have omitted alternative="greater". When we define an alternative in this test, we have to be careful to think about what it means. When we use greater, we are asking whether the response in the first row is occurs _more frequently_ under the trial conditions in the first column. When we use less, we are asking whether the response in the first row is occurs _less frequently_ under the trial conditions in the first column. From 5.11 we obtain a p-value of 0.9054, so we have no evidence that females choose dark-legged males more frequently in lighted trials.

79

In the example above, we have two responses ( _i.e_ ., the chosen male phenotypes) and two predictors ( _i.e_ ., the trial conditions light and dark), but we can easily imagine a case where we have more than two responses and more than two predictors. For example, we might have an experiment where females can choose between tufted, dark-legged, and light-legged males, and where females were collected from rocks, leaf litter, or grass. Our contingency table might look like this

||**rocks**|**litter**|**grass**|**total**|
|---|---|---|---|---|
|**tufted-legged**|30|4|5|**39**|
|**dark-legged**|9|18|1|**28**|
|**light-legged**|6|3|4|**13**|
|**total**|**45**|**25**|**10**||

A common question to ask with this kind of data is whether the responses are independent of the predictors.

From the data in the contingency table, we can calculate the proportion of males chosen that had each phenotype ( _i.e_ ., tufted, 39/80 = 0.4875; dark-legged, 28/80 = 0.35; light-legged, 13/80 = 0.1625), and the proportion of females tested that came from each substrate ( _i.e_ ., rocks, 45/80 = 0.5625; litter, 25/80 = 0.3125; grass, 10/80 = 0.125). We can use this information to make a table of predicted outcomes. For example, if we know that a proportion 0.5625 of females came from the rocks and that a proportion 0.4875 of females choose tufted males, then if the response does not depend on the predictor we should expect that a proportion 0.5625 x 0.4875 = 0.2742 of all trials should be females from the rocks choosing tufted males. Because there were a total of 80 trials, we expect 21.94 observations in this cell. Repeating this for every cell, we can produce a table of expectations

||**rocks**<br>(0.5625)|**litter**<br>(0.3125)|**grass**<br>(0.125)|
|---|---|---|---|
|**tufted-legged**<br>(0.4875)|21.94|12.19|4.88|
|**dark-legged**<br>(0.35)|15.75|8.75|3.5|
|**light-legged**<br>(0.1625)|7.31|4.06|1.63|

To determine whether the observed results are more different from the expectations than we would expect due to chance alone, we can use either Fisher’s exact test or the chi-squared test, which work in the ways we have already described. We can implement these in R using code of the form

choice = matrix(c(30,9,6,4,18,3,5,1,4), nrow = 3, dimnames = list(c("tufted","dark","light"), c("rocks","litter","grass")))

80

choice

rocks litter grass tufted    30      4     5 dark       9     18     1 light      6      3     4

fisher.test(choice)

Fisher's Exact Test for Count Data

data:  choice p-value = 1.291e-05 alternative hypothesis: two.sided

chisq.test(choice)

Pearson's Chi-squared test

data:  choice X-squared = 26.9084, df = 4, p-value = 2.074e-05

Warning message: In chisq.test(choice) : Chi-squared approximation may be incorrect

In 5.12, the first command creates our contingency table, and the last two commands test to see whether the observed results differ from the values we would expect if there were no relationship between the predictor and the outcomes. Thus, this is sometimes referred to as a _test for association_ between the predictor and the responses.

Fisher’s exact test and the chi-squared test have different advantages. Because Fisher’s exact test calculates exact p-values, it is not sensitive to small sample sizes. Therefore, it is the preferred test when some cells in the contingency table have fewer than 5 observations. In this case, R will warn us that p-values estimated with the chi-squared test may not be accurate. However, if the total number of observations in the contingency table is very large, then calculating exact p-values becomes computationally inefficient. In such cases, Fisher’s exact test will fail to return a result, and we have to rely on the approximate p-value estimated with the chi-squared test.

When contingency tables include more than two rows or more than two columns, Fisher’s exact test and the chi-squared test ask whether _any_ of the response frequencies differ among _any_ of the predictors, but they do not tell us which responses differ among which predictors. For example, in 5.12 we have strong evidence that females from different origins choose mates differently, but we do not know if females from the rocks choose mates differently than females from the litter. To be even more specific, we do not know if females from the rocks choose tufted males differently than females from the litter. To find out, we

81

can conduct _post hoc_ pairwise comparisons with Bonferonni corrections, just as we did for goodness-of-fit tests previously. For this example, we would use

choice = matrix(c(30,15,4,21), nrow = 2, dimnames = list(c("tufted","not tufted"), c("rocks","litter"))) choice rocks litter tufted        30      4 not tufted    15     21 fisher.test(choice)

Fisher's Exact Test for Count Data data:  choice p-value = 5.283e-05 alternative hypothesis: true odds ratio is not equal to 1 95 percent confidence interval: 2.750926 47.960972 sample estimates: odds ratio 10.11331

If the number of responses or the number of predictors is large, there are many different pairwise comparisons that we might make. This means that Bonferonni corrections can potentially cost us a lot of statistical power. For this reason, it is often worth thinking carefully about the specific pairwise comparisons that will be of interest _before_ we begin to collect the data. Then, we can limit our _post hoc_ comparisons to this set, and thereby reduce the dominator in our Bonferonni correction.

When presenting differences in responses among predictors, bar charts are usually the most intuitive option. Often it is best to present the frequencies rather than the raw numbers, since this is the information that is of most interest to readers. If there are only two responses, a single bar for each response is enough. After all, any trial that did not get the response we plot must have gotten the other, so plotting a second bar does not add any new information. For example, if we were interested only in tufted vs. non-tufted males, we could create a plot using

choice = matrix(c(30/45,4/25,5/10), nrow = 1, dimnames = list(c("tufted"), c("rocks\n(n = 45)","litter\n(n = 25)", "grass\n(n = 10)")))

82

choice rocks\n(n = 45) litter\n(n = 25) grass\n(n = 10) tufted       0.6666667             0.16             0.5 barplot(choice,ylab="frequency of tufted males chosen", xlab="female origin",ylim=c(0,.8))

In the vector c(30/45,4/25,5/10), we have divided the number of tufted males chosen by females from each origin by the total number of females with that origin. This gives us the frequency with which those females chose tufted males. We added the sample size for each type of females to the column labels. The \n inserted in the column labels adds a hard return when the names are printed. This makes the contingency table unwieldy, but looks good in figure 5.2a (next page).

If there are more than two responses, then a single bar for each predictor will not suffice. In this case, a stacked bar chart is often an intuitive way to present the results. To present the results from code 5.12, we could use

choice = matrix(c(30/45,9/45,6/45,4/25,18/25,3/25,5/10,1/10,4/10), nrow = 3, dimnames = list(c("tufted","dark","light"), c("rocks\n(n = 45)","litter\n(n = 25)", "grass\n(n = 10)"))) choice rocks\n(n = 45) litter\n(n = 25) grass\n(n = 10) tufted       0.6666667             0.16             0.5 dark         0.2000000             0.72             0.1 light        0.1333333             0.12             0.4

barplot(choice,legend=c(rownames(choice)),ylab="frequency", xlab="female origin",xlim=c(0,4.5))

Here, we have added a legend to the bar plot to identify the colours in the stacked bars (figure 5.2b, next page). The code xlim=c(0,4.5) stretches out the _x_ -axis. If we do not do this, then R (annoyingly!) plots the legend over one of the bars.

83

<!-- Start of picture text -->
b<br><!-- End of picture text -->

<!-- Start of picture text -->
a<br><!-- End of picture text -->

<!-- Start of picture text -->
a  b<br>light<br>dark<br>tufted<br>rocks litter grass rocks litter grass<br>(n = 45) (n = 25) (n = 10) (n = 45) (n = 25) (n = 10)<br>female origin female origin<br>0.8<br>1.0<br>0.6<br>0.8<br>0.4 0.6<br>frequency 0.4<br>0.2<br>0.2<br>frequency of tufted males chosen<br>0.0<br>0.0<br><!-- End of picture text -->

**Figure 5.2. Bar plots showing (a) the frequency of tufted males chosen and (b) the frequencies of all male phenotypes chosen as mates by female wolf spiders collected from three different substrates.**

#### **Literature cited**

Gilman, R. T., K. Fowler-Finn, E. A. Hebets. 2018. A probable case of incipient speciation in _Schizocosa_ wolf spiders driven by allochrony, habitat use, and female mate choice. Am Nat 192(3):332-346.

Scheffer, S. J., G. W. Uetz, and G. E. Stratton. 1996. Sexual selection, male

morphology, and the efficacy of courtship signalling in two wolf spiders (Araneae: Lycosidae). Behav Ecol Sociobiol 38:17-23.

Shamble, P. S., D. J. Wilgers, K. A. Swoboda, and E. A. Hebets. 2009. Courtship effort is a better predictor of mating success than ornamentation for male wolf spiders. Behav Ecol 20:1242-1251.

84

### **Chapter 6. Categorical responses to numerical predictors**

In Chapters 2 and 3 we studied how to compare the means of two or more groups. In these analyses the predictors were categorical and the responses were numerical. In Chapter 4 we studied how to assess the relationship between a numerical predictor and its numerical response, and in Chapter 5 we studied how to assess the relationship between a categorical predictor and its categorical response. But, what if the predictor is numerical and the response is categorical? This kind of data is common in fields including medicine, sociology, and ecology. For example, we might have demographic data on a deer population, and we might want to know whether the probability that a fawn survives to adulthood depends on factors such as its size at birth or the age of its mother. Each fawn either survives or it does not, so the response is categorical ( _i.e_ ., either “survived” or “did not survive”). But, the predictors birth mass and age are numerical.

Naively, we might approach this with a linear model. Figure 6.1 shows the birth mass and survivorship of 50 white-tailed deer ( _Odocoileus virginianus_ ) (the data is simulated, not real). Fawns that survived to adulthood are coded with a survivorship of 1, and fawns that died before adulthood are coded with a survivorship of 0. The red line is the best-fit linear model for the data. We can see a problem immediately. For birth masses above 4.1 Kg the linear model predicts survivorship greater than one, and for birth masses below 1.8 Kg the linear model predicts survivorship less than zero. Clearly, this is nonsense!

We can solve this problem by fitting a curve instead of a straight line to our data. The most common curve that researchers use for this is called the _logistic function_ , and fitting a logistic function to data is called _logistic regression_ . The logistic function takes the form

Here, _x_ is the predictor we are studying ( _i.e_ ., birth mass) and _y_ is the expected outcome. The expected outcome is simply the probability of an _event_ , where an event is the response that is coded with a 1 (here, survival). The parameters b _0_

<!-- Start of picture text -->
Figure 6.1. A linear<br>1<br>regression through a<br>simulated data set<br>showing the mass at<br>birth and survival to<br>adulthood of white-<br>0<br>tailed deer fawns.<br>2.0 2.5 3.0 3.5 4.0 4.5<br>mass at birth (Kg)<br>survived<br><!-- End of picture text -->

<!-- Start of picture text -->
Figure 6.1. A linear<br>regression through a<br>simulated data set<br>showing the mass at<br>birth and survival to<br>adulthood of white-<br>tailed deer fawns.<br><!-- End of picture text -->

85

<!-- Start of picture text -->
a  1.0 b  1.0<br>0.8 0.8<br>0.6 0.6<br>0.4 0.4<br>0.2 0.2<br>0.0 0.0<br>-6 -4 -2 0 2 4 6 -6 -4 -2 0 2 4 6<br>x x<br>y y<br><!-- End of picture text -->

**Figure 6.2. Logistic curves with different values of (a** ) b0 **and (b)** b **1.** In **a** , b1 = 1 and b0 = -2 (red) _,_ 0 (black) _,_ or 3 (blue). The dotted grey lines show where the midpoint of each curve falls on the _x_ -axis. In **b** , b0 = 0 and b1 = -0.75 (red) _,_ 0.4 (blue) _,_ or 1 (back). A negative slope means that the probability of the event decreases as the predictor increases.

and b _1_ control the shape of the curve. Specifically, b _1_ controls the slope: at its steepest point the slope of the curve is b _1_ /4. Then, b _0_ controls where the steepest point falls on the _x_ -axis: the steepest point falls at -b _0_ /b _1_ . The steepest point always occurs when the probability of the event is exactly ½. So, -b _0_ /b _1_ is the point where the event is equally likely to occur or not to occur. Figure 6.2 shows how different values of b _0_ and b _1_ affect the shape of the logistic function.

Figure 6.3 shows a logistic regression fitted to the fawn survival data from figure 6.1. The red curve shows the predicted probability that a fawn with the birth mass shown on the _x_ -axis survives to adulthood. Because b _1_ controls the slope of the curve, it tells us how strongly birth mass affects the probability of survival. So, b _1_ is the effect size of birth mass on survival. Because b _0_ moves the curve back and forth on the _x_ -axis, it controls where the curve crosses the _y_ -axis. Thus, it controls the intercept of our probability function. The intercept is the predicted probability of the event when the predictor has a value of zero. Of course, fawns cannot have a birth mass of zero, so in this model the prediction at the intercept is not biologically meaningful. Just as with linear regression, intercepts must be interpreted with caution if zero is not a plausible value for the predictor!

How did we find the values of b _0_ and b _1_ in figure 6.3? Recall that in linear regression, we looked for a best-fit model that minimised the squared distance between the predicted response ( _i.e_ ., the best-fit line) and the observed data

<!-- Start of picture text -->
Figure 6.3. A logistic<br>1 regression fitted to the<br>same data set shown in<br>figure 6.1.  The simulated<br>data shows the<br>relationship between<br>0 mass at birth and survival<br>to adulthood for white-<br>tailed deer fawns.<br>2.0 2.5 3.0 3.5 4.0 4.5<br>mass at birth (Kg)<br>survived<br><!-- End of picture text -->

86

points. In logistic regression, we will fit the model in a slightly different way. Every observation in a logistic regression has a _likelihood_ . For example, the model in figure 6.3 predicts that a fawn with a birth mass of 3 Kg survives to adulthood with probability 0.45. So, if our data set includes a fawn with birth mass of 3 Kg that survives to adulthood, the likelihood of that observation under our model is 0.45. If our data includes a fawn with birth mass of 3 Kg that dies before adulthood, the likelihood of that observation is 1 - 0.45 = 0.55. The likelihood of observing our exact data set given our model is the likelihood of the first observation times the likelihood of the second times the likelihood of the third, and so on throughout the whole data set. Formally, we can write this as

where _L_ represents likelihood, **Y** is the observed data set, q  is the set of parameter values, and _n_ is the number of observations in the data set. Or, stated in words, the likelihood of observing exactly our set of responses given the parameter values is the product of the likelihoods of observing each individual response in the data set. When we fit the model, we look for the parameter values that maximise this likelihood. That is, we choose the parameter values under which our observed responses are most likely to occur.

#### **Conducting logistic regression in R**

We can implement logistic regression in almost the same way we implement linear regression, and many of the techniques we learned for linear regression can be applied to logistic regression too. For example, we can mean centre predictors, conduct multiple regressions, and use backward selection to choose “best” models.

To illustrate this, let’s walk through an example. In the Dropbox folder for this handbook you will find a file called “pinochet.csv.” The data set is a poll of approximately 1700 voters in the 1988 Chilean plebiscite that decided whether right-wing military dictator Augusto Pinochet would remain in power. The “no” side won the plebiscite by a margin of 56% to 44%, and Pinochet was replaced by a democratically elected president a year later. However, it may be interesting to understand who voted for Pinochet and who voted against him.

You can import the data into R using the read.csv command as you have done in previously. I named the imported data frame pino. It looks like this:

pino

|population age education income male vote|
|---|
|1        175000  29        PS   7500    1    0|
|2         15000  18         P   2500    0    1|
|3        250000  18         P   2500    0    0|
|4         25000  18         P   2500    1    0|

…

87

Here, the column population reports the size of the village or city in which the voter lived. This might be a surrogate for whether the voter came from a rural or urban community. The column age reports age of the voter. The column education reports the voter’s highest level of education: primary school (P), secondary school (S), or post-secondary school (PS). The column income reports the voter’s monthly earnings in Chilean pesos for the previous year. The column male indicates whether the voter was male (1) or female (0). As in the Canadian income data in Chapter 4, these are self-reported values. Finally, the column vote reports whether the voter voted for (1) or against (0) Pinochet.

Let’s begin by asking which of the quantitative predictors in our data set influenced whether voters supported or opposed Pinochet. The predictors age, income, and population are numerical. Sex is categorical, but it is dichotomous, and male is coded 1s and 0s. So, we can treat male as a numerical predictor, just as we did in our linear regressions in Chapter 4. Let’s also include an interaction between income and population in our analysis. This is interesting because evidence from other countries suggests that the urban poor often vote differently than the rural poor.

Altogether, we are proposing to study five quantitative predictors. Do we have enough data to do this? When we conduct a multiple logistic regression, we will estimate an effect size for each predictor in the model. A common rule of thumb says that our data should include at least 15 _cases_ for every effect size that we will estimate. The number of cases is the smaller of the number of events or non-events in the data (that is, the smaller of the number of ones or the number of zeros in the response variable). We can calculate the number of ones and zeros in vote using code we have seen before

sum(pino$vote==1)

[1] 837

sum(pino$vote==0)

[1] 867

We have 837 cases, which is more than 160 cases for each effect size that we will estimate. So, we have plenty of data!

Before we fit a model, let’s mean centre the predictors. Recall from Chapter 4 that mean centring sets the mean value for a predictor to zero. Because the intercept describes the expected response when all of the predictors are zero, mean centring makes it easier to interpret the intercept. We can mean centre the predictors using the code

mc_age=pino$age-mean(pino$age) mc_inc=pino$income-mean(pino$income) mc_pop=pino$population-mean(pino$population)

88

I have not mean centred male because it is already easy to interpret a zero in the column male.  That simply means the voter was a woman!

To fit a logistic regression to our data, we use code analogous to the code we used to fit linear regressions in Chapter 4

pino.lr=glm(vote~mc_age+male+mc_pop+mc_inc+mc_pop*mc_inc, data=pino,family=binomial)

Here, glm(… tells R to fit a _generalised linear model_ . This is a broad class of models that includes linear regression, logistic regression, and several other model types. The code family=binomial specifies a logistic regression. This may seem unintuitive, but it derives from the fact that error in a logistic regression follows a binomial distribution. If we do not specify a family for the model, R fits a linear regression by default. The code vote~mc_age+…+mc_pop*mc_inc defines the model we want to fit, and follows the same syntax we used for linear regressions. Finally, data=pino tells R to use the data in the data frame pino, and pino.lr is the name we will give to our fitted model. To see the results, we use the command summary:

summary(pino.lr)

Call: glm(formula = vote ~ mc_age + male + mc_pop + mc_inc + mc_pop *mc_inc, family = binomial, data = pino)

Deviance Residuals: Min       1Q   Median       3Q      Max -1.8502  -1.0897  -0.7086   1.1023   1.7750 Coefficients: Estimate Std. Error z value Pr(>|z|) (Intercept)    2.671e-01  7.612e-02   3.509  0.00045 *** mc_age         2.168e-02  3.452e-03   6.281 3.37e-10 *** male          -6.340e-01  1.022e-01  -6.205 5.48e-10 *** mc_pop        -4.175e-06  5.422e-07  -7.700 1.36e-14 *** mc_inc         1.376e-06  1.504e-06   0.915  0.36003 mc_pop:mc_inc  2.322e-11  1.567e-11   1.482  0.13837 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2216.4  on 1698  degrees of freedom AIC: 2228.4

Number of Fisher Scoring iterations: 4

There is a lot of information in this output, but we will focus on just two

89

things for now. The first is the p-value in the column Pr(>|z|). R calculates this using a _Wald test_ . This p-value is the probability that we would see an effect size at least as large as in the observed data if there were really no relationship between the predictor and the response. If the p-value is low, the observed relationship is unlikely to be due to chance alone. The second piece of information is the effect size in the column Estimate. The effect size is the value of b associated with the predictor in that row. If it is positive, then events become more likely as the predictor increases. If it is negative, then events become less likely as the predictor increases.

The magnitude of the effect size in a logistic regression also has an interpretable meaning, but it is less intuitive than the magnitude of the effect size in a linear regression. The effect sizes in logistic regression are reported as _log odds ratios_ . For example, the effect of age in our model, reported as a log odds ratio, is 0.02168 yr<sup>-1</sup> . The inverse of the log function is the exponential function. So, if the log odds ratio is 0.02168 yr<sup>-1</sup> , then the odds ratio is exp(0.02168) yr<sup>-1</sup> , or 1.02192 yr<sup>-1</sup> . This means that for every additional year of age a voter in the study population had, the odds that they voted for Pinochet increase by a factor of 1.02192. So, if the odds that a particular person voted for Pinochet were 4 to 1, then if that person were one year older, the odds that they voted for Pinochet would be 4 x 1.02192 = 4.088 to 1. Unless you spend a lot of time in betting shops, you might find this expression of effect sizes hard to follow, and indeed the effect sizes of logistic regression are often misrepresented in the scientific literature!

Is the model in 6.5 the best model for the data we studied? If we choose the best model by backwards selection, then that model will not include predictors that do not influence the response variable. In 6.5, some predictors have nonsignificant p-values. The predictor mc_inc is not significant, but we cannot remove it because it is included in an interaction that is part of the model. But, the interaction between mc_inc and mc_pop is also not significant. So, let’s remove that interaction.

pino.lr=glm(vote~mc_age+male+mc_pop+mc_inc,data=pino, family=binomial) summary(pino.lr)

(6.6)

(some lines omitted to save space)

Coefficients:

Estimate Std. Error z value Pr(>|z|) (Intercept)  2.988e-01  7.306e-02   4.090 4.32e-05 *** mc_age       2.168e-02  3.449e-03   6.286 3.27e-10 *** male        -6.446e-01  1.019e-01  -6.326 2.51e-10 *** mc_pop      -4.390e-06  5.238e-07  -8.380  < 2e-16 *** mc_inc       2.719e-06  1.212e-06   2.243   0.0249 * ---

Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2218.6  on 1699  degrees of freedom AIC: 2228.6

90

Now, all of the predictors are significant. So, this could be our best model.

#### **Studying quantitative and qualitative predictors in the same model**

In addition to the numerical predictors we have just studied, our data set includes the categorical predictor education. We can study numerical and categorical predictors in the same model using an approach called ANCOVA, or _Analysis of Covariance_ . Implementing ANCOVA in R is easy. We can simply add the categorical predictor to the regression model in our glm command. Here we will add a categorical predictor to a logistic regression, but we could do the same thing with linear regressions like those in Chapter 4.

Before we add education to our model, let's make sure we have enough data to do it. The full model in 6.5 included four quantitative predictors and one interaction, and thus estimated five effect sizes. The predictor education has three levels: P, S, and PS. One of these levels will serve as a baseline against which the other two will be compared, but we will need to estimate effect sizes for the other two levels. In general, if we add a qualitative predictor with _n_ levels to our model, we add _n_ – 1 to the number of effect sizes we must estimate. So, with education in the model, we must estimate 7 effect sizes. But, we have 837 cases, so again we have plenty of data.

So, let’s add education to our full model:

pino.lr=glm(vote~mc_age+male+mc_pop+mc_inc+mc_pop*mc_inc+ education,data=pino,family=binomial) summary(pino.lr)

…

Deviance Residuals: Min       1Q   Median       3Q      Max -1.8472  -1.0677  -0.6201   1.0738   1.8608 Coefficients: Estimate Std. Error z value Pr(>|z|) (Intercept)    6.588e-01  1.062e-01   6.203 5.54e-10 *** mc_age         1.476e-02  3.691e-03   3.999 6.36e-05 *** male          -5.911e-01  1.034e-01  -5.715 1.10e-08 *** mc_pop        -3.908e-06  5.515e-07  -7.086 1.38e-12 *** mc_inc         5.660e-06  1.718e-06   3.295 0.000985 *** educationPS   -9.954e-01  1.693e-01  -5.879 4.13e-09 *** educationS    -5.094e-01  1.243e-01  -4.096 4.20e-05 *** mc_pop:mc_inc  1.403e-11  1.625e-11   0.863 0.388008 --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2179.4  on 1696  degrees of freedom AIC: 2195.4

91

As before, the interaction between mc_inc and mc_pop is not significant, so we can remove it:

> pino.lr=glm(vote~mc_age+male+mc_pop+mc_inc+education,data=pino, (6.8) family=binomial) summary(pino.lr)

Call: glm(formula = vote ~ mc_age + male + mc_pop + mc_inc + education,

family = binomial, data = pino)

Deviance Residuals: Min       1Q   Median       3Q      Max -1.8324  -1.0650  -0.6193   1.0741   1.8621

Coefficients:

Estimate Std. Error z value Pr(>|z|) (Intercept)  6.854e-01  1.018e-01   6.732 1.68e-11 *** mc_age       1.465e-02  3.686e-03   3.974 7.06e-05 *** male        -5.968e-01  1.032e-01  -5.783 7.34e-09 *** mc_pop      -4.036e-06  5.323e-07  -7.582 3.41e-14 *** mc_inc       6.545e-06  1.392e-06   4.702 2.58e-06 *** educationPS -1.009e+00  1.688e-01  -5.976 2.29e-09 *** educationS  -5.216e-01  1.236e-01  -4.221 2.43e-05 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2180.1  on 1697  degrees of freedom AIC: 2194.1

Number of Fisher Scoring iterations: 4

Now, all of the predictors in the model are significant. But, is this our best model?  Recall the discussion of multiple testing at the beginning of Chapter 3. If we compare more than two groups, then the probability that at least one group will appear significantly different from at least one other is greater than our chosen significance level. So, using p-values alone to determine whether a predictor with three or more levels belongs in a model is not a good approach.

Fortunately, we have an alternative. The value AIC at the bottom of the summary in 6.8 is _Akaike’s Information Criterion_ . AIC is a measure of the likelihood of the response data set given the model and the parameters, and it is weighted for the number of parameters in the model. A lower AIC means the model is a better predictor of the observed data. So, if we remove a predictor and AIC decreases, then that predictor does not belong in the best model. If we remove a predictor and AIC increases, then that predictor does belong in the model.

92

We have already considered the model that includes all the predictors in 6.8 but without the predictor education. That was the model we built in 6.6. AIC in that model is 2228.6, and AIC in the model with education is 2194.1. So, 6.8 is the better model.

Some people would argue that we should not mix the use of p-values and AIC in backward selection. Others would argue that we should not use AIC in backward selection at all<sup>6</sup> . AIC is known to _overfit_ models. That is, it has a tendency to include predictors that do not really affect the response variable. However, in this case, all of the p-values in the model are very low (<0.0001), so we can be confident that the predictors we have identified really do predict the response.

#### **Reporting the results of logistic regression**

In order to understand our study, readers will need to know how we conducted our analysis and what results we obtained. Usually, an explanation of the analysis is included in the methods section of a write-up, and the outcome is presented in the results section.

Most students understand that a methods section must clearly explain the techniques they used in the field or in the lab.  However, a well-written methods section will also explain the precise questions the researcher asked, the data they used to address those questions, and how that data was analysed. In previous chapters in this handbook, the data has been relatively straight-forward. However, the data we studied in our logistic regression is less straight-forward. For example, we used the population of voters’ cities or towns of residence as a surrogate for whether those voters are urban or rural. How might we present our question, data, and analysis in a concise way that readers can easily understand? I might write:

We studied how voter preference for or against Pinochet depended on demographic predictors. Our predictors were the voter’s age, self-reported sex, monthly income in Chilean pesos, education, and the population of the city or town in which the voter lived. We treated education as a categorical predictor with three classes describing the highest level of education the voter had completed: primary, secondary, or post-secondary ( _i.e_ ., university) education. We used the population of the voter’s city or town of residence as a surrogate for whether the voter was urban or rural. Larger populations indicated that voters were more urban. We analysed the data with logistic regression implemented using the command glm in R, and selected the best model to predict voter preference using backward selection.

6 AIC has many uses and limitations that we will not discuss in this handbook. If you will use AIC extensively, it is well worth reading Burnham and Anderson’s excellent book _Model Selection and Multimodel Inference: a Practical InformationTheoretic Approach_ .

93

I have told readers that we analysed the data using the command glm. This is important because there are other tools that implement logistic regression, and some of them work slightly differently. The command glm produces p-values using a Wald test, and the p-values describe the probability that we would see an effect size as large as that in the observed data by chance alone. Some other commands find p-values using _likelihood ratio tests_ . The likelihood ratio test for a given predictor compares the likelihood of the responses with and without the predictor, and reports the probability that adding a random predictor to the model would increase the likelihood of the responses as much as adding the real predictor did. The questions are slightly different, but the answers are usually quite similar.  For example, the p-value for an effect of age on voter preference using the Wald test is 7.06 x 10<sup>-5</sup> , and using a likelihood ratio test it is 6.65 x 10<sup>-5</sup> . So, what we infer about our system does not depend on which test we use. Nonetheless, the exact p-value does. If a reader were to repeat our analysis by following our methods, they should be able to obtain exactly the results we did, and to do that they need to know which approach we used.

Notice that in the description above, I did not simply tell the reader we conducted a GLM. The term GLM covers a broad class of models. If I tell the reader I did a GLM, she will not know whether I did a linear regression, a logistic regression, a Poisson regression, or any one of a number of other models not covered in this handbook. If I specify for the reader that I did a logistic regression, then they will have the information they need to replicate the analysis.

How do we report the results of a multiple logistic regression? As with multiple linear regression, the most common way to report the results is with a table supported by text. For our analysis of the plebiscite data, I might write:

The probability that a voter supported Pinochet increased with age and income and decreased with education (table 6.1). Rural voters were more likely to support Pinochet than urban voters, and women were more likely to support Pinochet than men.

I have not included p-values or effect sizes in the text because they are presented in the table. Presenting so many numbers in the text would make the text

|**Predictor**|**Effect size**|**Standard**<br>**error**|**p-value**|
|---|---|---|---|
|intercept|0.69|0.010|<0.0001|
|age|0.015 yr<sup>-1</sup>|3.7 x 10<sup>-3</sup>|<0.0001|
|sex|-0.60|0.10|<0.0001|
|population|-4.0 x 10<sup>-6</sup>person<sup>-1</sup>|5.3 x 10<sup>-7</sup>|<0.0001|
|income|6.5 x 10<sup>-6</sup>peso<sup>-1</sup>|1.4 x 10<sup>-6</sup>|<0.0001|
|education (secondary)|-0.52|0.12|<0.0001|
|education (post-secondary)|-1.0|0.17|<0.0001|

**Table 6.1. Demographic correlates predicting that a voter supported Augusto Pinochet in the 1988 Chilean plebiscite.** Effect sizes are reported as log odds ratios.

94

cumbersome. I have also not mentioned the intercept in the text. The intercept tells us the probability that a very particular voter supported Pinochet. That voter was a woman ( _i.e_ ., male = 0) with the average age, income, and home town size in the data set.  Moreover, that voter had a primary school education, since that is the baseline to which the effects of the secondary and post-secondary education are compared. Because the effect size at the intercept is positive and significant, we know that this voter was more likely to support than oppose Pinochet. However, aside from the fact that this voter is the baseline against which other voters are compared, there is nothing particularly special about her. So, there is no reason to mention her voting pattern in the results.

Sometimes we might want to represent the results of a logistic regression with a figure. If there is only one predictor in the best model, we can simply plot the response variable with the logistic function fitted to it. This is what we saw in figure 6.3. Let’s construct that figure as an example. The simulated fawn survivorship data at the beginning of this chapter is saved in “deer.csv” in the Dropbox folder with this handbook. We can import that data into a data frame deer. In deer, the column bw reports the body mass at birth and s reports survivorship. To create figure 6.3, we can use the code

plot(deer$bw,deer$s,xlab="mass at birth (Kg)", ylab="survived",ylim=c(-.25,1.25))

(6.9)

s.lr=glm(s~bw,data=deer,family=binomial)

curve(1/(1+exp(-(s.lr$coefficient[1]+x*s.lr$coefficient[2]))), min(deer$bw)-.2,max(deer$bw)+.2,col="red",add=T)

Here, plot(…) creates a scatterplot , and s.lr=glm(…) fits a logistic function to the data in deer. The intercept and the effect size of the predictor in s.lr are stored as s.lr$coefficient[1] and s.lr$coefficient[2], respectively. So, 1/(1+exp(-(s.lr$coefficient[1]+x*s.lr$coefficient[2]))) is the logistic function that best predicts survivorship, where x represents mass at birth. The command curve(…,add=T) plots this function onto the scatterplot we created with the plot command. The text min(deer$bw)-.2,max(deer$bw)+.2 tells R to begin plotting the logistic function at 0.2 Kg less than the smallest birth mass, and stop at 0.2 Kg greater than the largest birth mass in the data set. So, this sets the range of values to plot.

If the best model includes more than one predictor, then plotting the effect of any one predictor is more difficult. The reason is that the probability of an event depends not just on the predictor of interest, but also on all of the other predictors in the model. In order to plot the effect of a predictor of interest, we have to choose baseline values for the other predictors. If we have mean centred the predictors, then the most intuitive value to choose for the other predictors might be zero, which represents the population mean. However, depending on what we want to communicate to the reader, we might sometimes choose other baseline values for our figures.

95

For example, let’s create a plot that shows how age affected voter preferences in the Chilean plebiscite. More specifically, let’s show this for voters of each education level. We do not want to plot the mean centred age on the x- axis, because that will not be intuitive to our readers. So, let’s refit our best model using raw rather than mean centred age as a predictor:

> pino.lr=glm(vote~age+male+mc_pop+mc_inc+education,data=pino, (6.10) family=binomial) summary(pino.lr) Call: glm(formula = vote ~ age + male + mc_pop + mc_inc + education, family = binomial, data = pino) Deviance Residuals: Min       1Q   Median       3Q      Max -1.8324  -1.0650  -0.6193   1.0741   1.8621 Coefficients: Estimate Std. Error z value Pr(>|z|) (Intercept)  1.276e-01  1.888e-01   0.676    0.499 age          1.465e-02  3.686e-03   3.974 7.06e-05 *** male        -5.968e-01  1.032e-01  -5.783 7.34e-09 *** mc_pop      -4.036e-06  5.323e-07  -7.582 3.41e-14 *** mc_inc       6.545e-06  1.392e-06   4.702 2.58e-06 *** educationPS -1.009e+00  1.688e-01  -5.976 2.29e-09 *** educationS  -5.216e-01  1.236e-01  -4.221 2.43e-05 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 (Dispersion parameter for binomial family taken to be 1) Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2180.1  on 1697  degrees of freedom AIC: 2194.1

…

If we compare 6.10 to 6.8, we will see that the only thing that has changed is the intercept. This should make sense. The goal of mean centring is to make the intercept easier to interpret, so we should not expect mean centring to change anything else.  We can use the summary in 6.10 to plot the predicted probability that voters of a given age supported Pinochet using

> curve(1/(1+exp(-(0.1276+x*0.01465))),18,70,ylim=c(0,1), (6.11) ylab="probability of supporting pinochet",xlab="voter age",col="red")

curve(1/(1+exp(-(0.1276+x*0.01465-0.5216))),col="blue",add=T) curve(1/(1+exp(-(0.1276+x*0.01465-1.1118))),col="green",add=T) legend(50,0.28,legend=c("primary","secondary","postsecondary"),col=c("red", "blue","green"),lty=1,cex=0.9)

96

<!-- Start of picture text -->
1.0<br>0.8<br>0.6<br>0.4<br>0.2 primary<br>secondary<br>post-secondary<br>0.0<br>20 30 40 50 60 70<br>voter age<br>probability of supporting Pinochet<br><!-- End of picture text -->

**Figure 6.4. The effect of age and education on voter preference in the 1988 Chilean plebiscite.** Line colours indicate the maximum level of education that the voter had completed.

In 6.11, the first curve command makes the figure, and the next two commands add curves to that figure. Because the first curve command produces the figure, it also sets the limits of the _y_ -axis and the labels on both axes. The numbers 18 and 70 set the range of voter ages for which we will show predictions. In 1/(1+exp(-(0.1276+x*0.01465))), the 0.1276 is the intercept and to 0.01465 is the effect of age on voter preference for Pinochet. So, the first (red) curve predicts how voters that are women ( _i.e_ ., male = 0) with primary school education (because voters primary school education are the baseline to which other voters are compared) and average incomes and home town sizes voted in the plebiscite. In the second (blue) curve, we have added the effect of a secondary school education ( _i.e_ ., -0.5216) to the prediction, and in the third (green) curve we have added the effect of a post-secondary education to the prediction. The command legend(…) adds a legend to the figure. In legend, the numbers 50 and 0.28 position the top left corner of the legend on the _x_ and _y_ axes, legend=… sets the text of the legend, col=… sets the colors of the lines in the legend, lty=… sets the line styles (1 indicates solid lines), and cex=… sets the text size. The result is figure 6.4.

#### **Using logistic regression to predict probabilities**

We can use the results of our logistic regressions to predict the probability of an event for any member of our study population. To demonstrate this, let’s predict to probability that some person in Chile in 1988 would have voted for Pinochet. In most of the models that we have already fit, we used mean centred predictors, because these make the intercepts more meaningful. But, when we are predicting events, we do not need to interpret the intercept. So, it is often easier to work with models fitted to the raw predictors. Let’s fit the vote data to the raw predictors now. With only minor changes to what we have already done, we can obtain

97

(6.12)

pino.lr=glm(vote~age+male+population+income+education, data=pino,family=binomial) summary(pino.lr)

Call: glm(formula = vote ~ age + male + mc_pop + mc_inc + education, family = binomial, data = pino)

Deviance Residuals: Min       1Q   Median       3Q      Max -1.8324  -1.0650  -0.6193   1.0741   1.8621 Coefficients: Estimate Std. Error z value Pr(>|z|) (Intercept)  4.946e-01  1.890e-01   2.617  0.00888 ** age          1.465e-02  3.686e-03   3.974 7.06e-05 *** male        -5.968e-01  1.032e-01  -5.783 7.34e-09 *** population  -4.036e-06  5.323e-07  -7.582 3.41e-14 *** income       6.545e-06  1.392e-06   4.702 2.58e-06 *** educationPS -1.009e+00  1.688e-01  -5.976 2.29e-09 *** educationS  -5.216e-01  1.236e-01  -4.221 2.43e-05 *** --Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1 (Dispersion parameter for binomial family taken to be 1) Null deviance: 2361.7  on 1703  degrees of freedom Residual deviance: 2180.1  on 1697  degrees of freedom AIC: 2194.1

…

We can compute the log odds that any person in population would have voted for Pinochet by summing up the effects that pertain to that person. Harvesting the effects from the output in 6.12, the formula for this summation is

f = 0.4946 + 0.01465 * age – 0.5968 * male – 4.036 x 10<sup>-6</sup> * population

+ 6.545 x 10<sup>-6</sup> * income – 1.009 * PS – 0.5216 * S

Then, to compute the log odds for a particular person, we can simply substitute the values of that persons predictors into the formula. For example, the log odds that a 20-year old man from a city of 1,000,000, with a monthly income of 2500 pesos and a secondary education would have voted for Pinochet are

0.4946 + 0.01465 * 20 – 0.5968 * 1 – 4.036 x 10<sup>-6</sup> * 10<sup>6</sup>

+ 6.545 x 10<sup>-6</sup> * 2500 – 1.009 * 0 – 0.5216 * 1 = -4.35

In this formula, the person of interest gets a value of 1 for S and 0 for PS because he had a secondary school education. If he had had a post-secondary education he would have gotten a 0 for S and a 1 for PS, and if he had had only a primary

98

school education he would have gotten 0s for both S and PS. We can convert the log odds we computed to a probability using the logistic function

1/(1 + exp(-(-4.35))) = 0.013

So, there is only a slightly greater than 1% chance this person would have voted for Pinochet. As a counterpoint, we can compute the probability that a 60-year old woman from a city of 20,000 and with a monthly income of 75,000 pesos and secondary education would have voted for Pinochet

0.4946 + 0.01465 * 60 – 0.5968 * 0 – 4.036 x 10<sup>-6</sup> * 20,000

+ 6.545 x 10<sup>-6</sup> * 75,000 – 1.009 * 0 – 0.5216 * 1 = 1.26

and

1/(1 + exp(-(1.26))) = 0.779

So, this person would have had an almost 78% chance of voting for Pinochet!

#### **An important assumption of logistic regression**

In logistic regression, we fit a specific ( _i.e_ ., a logistic) function to our data. Our model assumes that the logistic function is the correct function to describe the relationship between the predictors and the probability of events in the response variable. This may not always be true. In some cases, this can be dealt with by transforming the predictors. In other cases, the data might be better fit by some function other than a logistic function. Dealing with violations of this assumption is beyond the scope of this handbook. If you expect to use logistic regression frequently, you may wish to make a more thorough study of this assumption and how violations can be addressed. One place to start would be Fox and Weisberg’s (2001) _An R Companion to Applied Regression_ .

#### **Literature cited**

Burnham, K.P. and D. R. Anderson. 2002. _Model Selection and Multimodel Inference: a Practical Information-Theoretic Approach_ . Springer, New York, NY.

- Fox, J. and S. Weisberg. 2011. _An R Companion to Applied Regression_ . Sage, Thousand Oaks, CA.

99

### **Appendix 1: Choosing a statistical test**

|**Predictor**|**Response**<br>**variable**|**Tests**|
|---|---|---|
|Categorical|Categorical|Chi-squared test, Fisher’s exact test;<br>see Chapter 5|
|Categorical<br>(Dichotomous)|Numerical|t-test, Wilcoxon test; see Chapter 2|
|Categorical|Numerical|ANOVA, Kruskal-Wallis test; see<br>Chapter 3|
|Numerical|Numerical|Linear regression, rank correlation<br>tests; see Chapter 4|
|Numerical|Categorical<br>(Dichotomous)|Logistic regression; see Chapter 6|

**Table A1.1. Choosing a statistical test.** The most appropriate statistical test will depend on whether your data is numerical or categorical. This table offers a simple set of rules for choosing which tests to use. Ordinal response varaiables ( _e.g_ ., responses on the Likert scale) are not numerical, but can be analysed with Wilcoxon or Kruskal-Wallis tests.

100

### **Appendix 2: Installing and navigating R**

#### **R:** **_the_ tool for statistical analysis in ecology and evolution**

In this unit, we will make extensive use of a computational language called R. R is widely used for statistical analyses, although it can do many other things as well. For our purposes, you can think of R as an alternative to SPSS or Prism.

There are many advantages to learning to use R. SPSS and Prism are _programmes_ for statistical analysis. They include large but ultimately limited sets of analytical tools, and it is difficult to modify or move beyond these tools. Because R is a _language_ rather than just a programme, its limits are not intrinsic. R is limited only by the user’s knowledge and creativity. It is also easier to find help with R than with SPSS or Prism. Because R is so widely used, you can find guidance online for almost any analysis you would like to conduct. R has emerged as the tool of choice for statistics in ecology and evolution (and many other fields as well), so using R makes it easier to communicate with other scientists about your analyses. Finally, R is and will always be free. You can download it onto your laptop, and use it whenever or wherever you like. For all of these reasons, learning to use R is a good investment in your scientific career.

This unit is not a course in R. We will use R as a tool, but we will barely scratch the surface of what R can do. I will not ask you to memorise commands or bits of code. Every analysis we do will be presented in a step-by-step fashion. You can consult the handbook as much as you would like during the unit, on your field course, and afterward. Over time, you will learn the commands that you use most frequently simply because you use them. You will probably have to look up commands you use less frequently when you need them, but that is exactly what professional researchers do. If you think of R as a tool to be used rather than as something you have to commit to memory, then I think you will find it quite easy.

#### **Installing and navigating R**

R can be used through any of several interfaces. The interface determines how R appears on your computer when you use it, but the commands you will use will be the same regardless of which interface you choose. In this handbook I will assume you are using an interface called RStudio. RStudio makes saving your work intuitive, and with RStudio it is easy to edit and execute commands or even blocks of commands. This will become very useful later!

If you use a PC or a Mac, you can download RStudio from the website at <u>https://rstudio.com/products/rstudio/download/. Choose the free RStudio</u> Desktop application. The link will take you to a download page that will recommend the appropriate installation for your computer. Click on that version of RStudio to download it. The package will appear in your Downloads folder. Double-click the package and follow the instructions to install it.

101

The RStudio package is large, and will use more than 700 MB on your hard drive. If your hard drive space is very limited, you may want to work with the smaller native R installation instead. The interface will look different, and some aspects of managing your work will be less user-friendly, but the overall - functionality will be similar. You can download native R from https://cran.r <u>project.org/. Double click the appropriate version of R for your computer, find</u> the application in your Downloads folder, double click the application, and follow the instructions to complete the installation.

If you use a Chromebook, you cannot install R or RStudio on your computer, but you can use RStudio through your web browser. There are several options for this, but many students like RStudio Cloud. You can create a free RStudio Cloud account at <u>https://rstudio.cloud/. When you log in, your browser</u> will display an interface that is almost identical to the desktop version of RStudio. If you use RStudio Cloud, you will have limited online storage space for your work, and you must be connected to the Internet to use it.

#### **An overview of the RStudio interface**

After you have installed RStudio, you can explore the RStudio interface. First, you will need to open the application. If you are using a Mac, you can find RStudio in your Applications folder. If you are using a PC, the installation will have created a folder for RStudio, and may have created a desktop icon as well. In either case, find the RStudio icon and double-click it to open the application. If you are using RStudio Cloud, simply log in to your account from the RStudio Cloud web page.

When you attempt to open RStudio for the first time, you may get an error that says ‘Unable to locate R binary by scanning standard locations.’ When you downloaded RStudio, the programme R (which is the real workhorse behind the RStudio interface) should have downloaded with it. The error indicates that this - did not happen. Fortunately, it easily solved. You can go to <u>https://cran.r project.org/</u> and download and install R from there. After you have installed the correct version of R for your computer, RStudio will be able to find it and function as intended, and you will never have to go through this step again.

When you successfully open RStudio, you will see a main application window with three panels. There is an additional panel that is very useful, so let’s open that before we begin. At the top left of the application window, you will see an icon that looks like a blank page with green “+” superimposed on it (see figure A2.1 on the next page). If you hover over that icon, a text box with the words “New File” will appear.  Click that icon and select “R Script.” This will open a fourth panel in your application window. The application window should now look like figure A2.1. Let’s walk through the panels in the figure, beginning in the bottom left.

102

**Figure A2.1. The RStudio interface.** The red circle at the top left is not part of the window, but indicates the location of the “New File” tab.

#### _The R console_

The panel in the bottom left of the RStudio interface is called the _R console_ . The R console is where you will enter commands, and where your results will appear. The easiest way to see this is to do it. Try typing

##### 2+2

into the R console at the command prompt, and then hit return. R will respond with

##### [1] 4

Obviously, the answer here is “4.” The “[1]” indicates the index position of the answer. It will be easier to understand the index position after you have read a few more paragraphs. Note that by default, R will show your commands in blue, its outputs in black, and errors in red. This colour scheme makes it easier to understand the text in the console.

Of course, R is much more than a calculator. Let’s try a slightly less intuitive command called runif. The command runif is an abbreviation for _r_ andom _unif_ orm number. When executed, the command selects a random number between 0 and 1. “Uniform” means that every number between 0 and 1 is equally likely to be chosen. Try typing

##### runif(1)

at the command prompt and hitting return. Note that R is case-sensitive, so if you type Runif(1), you will get an error. When you execute the runif command, you should get an output that looks like

##### [1] 0.5448881

103

Here “0.5448881” is the random number I got when I executed the command. Your random number will be different, but it will be somewhere between 0 and 1. If you run the command again, you will get a different number.

The “1” in runif(1) tells R to produce one random number. But, you can tell R to produce many random numbers at the same time. For example, if you enter

##### runif(20)

at the command prompt, R will produce 20 random numbers. Depending on the width of the R console on your screen, the result may look something like this:

[1] 0.92181596 0.58595951 0.04299670 0.72170654 0.90984669 [6] 0.63600864 0.45898560 0.17826476 0.01910092 0.72906720 [11] 0.08957933 0.01416794 0.40668261 0.48869135 0.34720736 [16] 0.88515530 0.36424239 0.30094639 0.47674354 0.93306280

We can use this output to understand the index position. Here, 0.92181596 is the 1<sup>st</sup> random number, 0.58595951 is the 2<sup>nd</sup> , 0.63600864 is the 6<sup>th</sup> , and so on. R shows the index position for only the first number in each row.

A set of numbers like the one above, where each number is described by a single index position, is called a _vector_ . So, if a vector has 100 entries, the entries will have index numbers 1 to 100. We call vectors “one-dimensional” data objects. An _array_ is a data object with more than one dimension. For example, the object

[,1]      [,2]      [,3] [1,] 0.8652037 0.9366125 0.8768115 [2,] 0.9690215 0.5136506 0.6738999 [3,] 0.3315193 0.5287952 0.2139196 [4,] 0.4158221 0.1932359 0.4257924

is a two-dimensional array. Here, the entry 0.8652037 has the index position [1,1], the entry 0.9366125 has the index position [1,2], and so on. You will learn more about vectors, arrays and other data objects and how to manipulate them as you work though this handbook.

Finally, R remembers the commands you enter into the console. You can use your up and down arrow keys to scroll back to commands you have recently used. This allows you to execute the same command multiple times. If there were errors in your previous commands, or if you need to change them slightly, you can edit them before you re-execute them. This can save you a lot of typing!

_The session history and environment_

Next, let’s consider the top right panel. (I know I have skipped a panel, but I will come back to it!) The top right panel is home to several tabs, but we will focus on the _session history_ and the _session environment_ .

104

The session history is a list of all the commands you have used since you opened R. We have just seen that we can scroll through these commands in the console using the up and down arrow keys. You can also scroll through them in the history tab. If you select a command and click on “To Console” on the panel’s menu bar, the command will appear in the console and you can execute it again. This can be useful if you want to re-execute a command from much earlier in the session. If you select a command and click on “To Source,” the command will appear in the top left panel. We will come back to why this might be useful later.

If you select the “Environment” tab at this point in your session, you should see that the environment is empty. That is because, while we have asked R to make several computations, we have not asked it to remember the answers. If we want to see the answer to 2 + 2 again, we have to re-execute the command. If we re-execute the runif command, we will get another random number, but it will not be the same one we got before. Often however, we will want to work with the answers from our calculations, so we will need R to remember them. To do this, we have to name the objects we create. For example, let’s create a vector of 20 uniformly distributed random numbers. We can use the command

my.random.numbers=runif(20)

Here, my.random.numbers is the name we have given to our vector. Of course, we could have named it anything we want. Often shorter names are easier to work with. When you execute the command above, the object my.random.numbers will appear in the session environment. The information to the right of the object reminds us what the object it. In this case, it has numeric (i.e., num) entries indexed from 1 to 20 (i.e., [1:20]). The rest of the line shows us the first few entries in the vector. If we want to see all of the entries in my.random.numbers, you can simply type my.random.numbers into the R console and press return. My random numbers were

my.random.numbers

[1] 0.65427238 0.50199642 0.12228604 0.92221780 0.08123031 [6] 0.05734188 0.26536528 0.81910402 0.27090750 0.03385509 [11] 0.85322140 0.51988583 0.59194197 0.48352314 0.04324730 [16] 0.20883722 0.32402716 0.41742328 0.62898187 0.15730967

If we want to see just some of the entries in the object, we can take advantage of the index numbers. For example

my.random.numbers[c(11:13,15)]

[1] 0.8532214 0.5198858 0.5919420 0.0432473

shows us only entries 11, 12, 13, and 15. In the command above, 11:13 indicates all of the integers from 11 to 13, inclusive. The command c(…) combines the entries in the parentheses into a vector.

105

#### _The scripting panel_

Now, let’s return to the top left panel. This is called the scripting panel. We can use this panel for working on code, or for saving code so we can use it again later.

When you try an analysis in R, you may not get it right the first time. (I almost never do!) You might write a command, test it, find it does not work as expected, edit it, and test it again. You might go through this process many times before your analysis works correctly. If the analysis has many steps, getting it just right might be a lot of work. Once you have gotten it right, you might want to save it so you can use it again in the future. If we work in the scripting window, we can do exactly that.

To illustrate this, let’s write a simple block of code that computes the hypotenuse of a right triangle. You may remember from geometry that, if the base of a right triangle has length _a_ and the perpendicular side has length _b_ , then the hypotenuse has length Ö( _a_<sup>2</sup> + _b_<sup>2</sup> ). So, if the base of our triangle has length 4 and the perpendicular side has length 3, then our code might look like this

a=4 b=3 h=sqrt(a^2+b^2) h

Here, the first two lines set the values of _a_ and _b_ . The third line computes the hypotenuse. In R, the operator “^” indicates raising to a power, and the command sqrt() computes a square root. The last line, h, simply displays the result. We could enter this code directly into the R console as four separate commands. Alternatively, we could write this code in the scripting window. We can them select the code in the scripting window and click the “Run” icon on the menu bar to execute all four lines at once.

One advantage to writing code in the scripting window is that we can easily edit it and run it again. For example, if we want to know the hypotenuse of a different triangle, we can simply change the values of a and b, select the code, and run it again. Moreover, if we think we might want to use this code again in the future, we can save it to a file using the disk icon from the menu bar.

If we will save a code in R, it is often useful to _annotate_ that code. Annotation just means leaving notes to explain what the code does. This can be useful when we come back to the code, because if it has been a while, we may have forgotten what the code does. It can also be useful if we might want to share our code with others. To annotate codes, we can leave comments that begin with the character “#”. The “#” tells R note to attempt to execute the rest of that line. For me, the annotated version of the code above might look like this

a=4 #set lengths of triangle sides b=3 h=sqrt(a^2+b^2)   #compute hypotenuse h      #report hypotenuse

106

Note that code in the scripting window is colour-coded differently from code in the console. In general, black indicates variables, operators, and functions; blue indicates numbers; and green indicates comments and strings. As you become more accustomed to using R, the colour-coding will make reading and editing your code much easier!

#### _The files and plots tabs_

The final panel, in the bottom right, includes several useful tabs. Two of the most important are the “Files” and “Plots” tabs. We will consider two additional tabs, the “Help” and “Packages” tabs, in the last two sections of this appendix.

The “Files” tab allows users to navigate to specific directories or folders on their computer. When you have navigated to a directory or folder, you can click on the “More” icon (represented in the menu bar for the panel by a blue gear) and set that directory as the _working directory_ .  By default, any codes that you save from the scripting window will be saved to the working directory. Moreover, you can import data sets from the working directory into R for analysis. We will learn more about importing data in Chapter 2.

If you are working with RStudio Cloud, you will not be able to set a directory on your computer as the working directory. Instead, any scripts you save will be saved an online project that is part of your RStudio Cloud account. If you want to download a script you have saved to your computer, click on the “More” icon and choose the “Export” option. Similarly, in RStudio Cloud, you will not be able to import data that resides in directories on your computer. Instead, you must first upload your data to RStudio Cloud using the “Upload” icon on the menu bar.

The “Plots” tab displays graphics items that you create in R. When you analyse data, you will usually want to illustrate your results with figures. We will learn about several different types of figures in as we work through this handbook. Figures are graphics items, and when you create them they will appear in the “Plots” tab. You can send your figures to larger floating window by clicking on the “Zoom” icon from the menu bar. You can convert your figures to images by clicking on the “Export” icon. Saved images can be pasted into reports and papers.

#### **Some notes on using the native R interface**

If you are working with the native R interface, you will be able to do all of the same things you can do with RStudio. However, how you interact with R through the native interface will be slightly different. In this section, we will consider some of the most important differences.

The first thing you will notice when you open the native R interface is that the application window has only one panel. This is the R console, and it works exactly like the console in RStudio.

107

You can open a scripting window in the native R interface from the “File” menu. If you are on a Mac, choose the option that says “New Document.” If you are on a PC, the option may say “New Script” instead of “New Document,” but it means the same thing. If you want to open an existing script, choose the “Open” option and navigate to the directory where the script is saved. In any of these cases, opening the script will also open the scripting window. Unlike in RStudio, in native R there is no option to run code directly from the scripting window. So, you will need to cut and paste code from the scripting window in the R console to run it.

Another important difference between RStudio and native R is in how you set the working directory. Recall that setting the working directory is important because this is where R will look for your data. In native R, we set the working directory using the “Change Working Directory” option. On a Mac, you can find this option in the “Misc” dropdown window. On a PC, you can find it on the “File” menu. Note that this option is only used for choosing the directory. You will not be able to import data with the “Change Working Directory” option. Rather, you will import data with the read.csv command. Importing data is covered in the Chapter 2.

There are other minor differences between the native R and RStudio interfaces, but you do not need to know about them to get started. You will learn more about how the interface you have chosen works as you gain experience working with it.

#### **Finding help with R**

If you analyse data with R, help is readily available. Many R users have described their analyses and approaches online. If you are having trouble with an analysis, an Internet search will often turn up useful advice. For example, if you are trying to analyse a data set with an ordinal response variable and the approaches in your handbook do not seem appropriate, you can google “analysing ordinal data in R” and you will find many relevant web pages. These will range from simple walk-throughs to in-depth discussions of the theoretical and computational challenges of your analysis.

If you are offline, perhaps because you are working in the field, or if you just need help with a particular R command, R also has a built-in help function. To get help with a particular command, just type ? and the name of the command into the R console. For example, the get help with the runif command, type

##### ?runif

This will open a help file with a description of what the command does and how to use it. If you are using RStudio, the help file will appear in the “Help” tab of the bottom right panel in application window. If you are using native R, the help file will appear in a new floating window.

108

#### **Downloading and installing R packages**

One of biggest advantages to using R is that so many other researchers also use it. Someone has probably used R to analyse data similar to yours, and often you can find their suggestions or even their code online. For analyses that require a lot of coding, you may even find that someone has created and published code in the form of an _R package_ . You can download R packages and use them to analyse your own data.

The easiest way to download and install an R package is with the install.packages command. For example, perhaps you want to use the package dunn.test, which is introduced in Chapter 3 of this handbook. You can simply type

install.packages("dunn.test")

into the R console. R will find the package, download it, and install it for you. The first time you install a new package, R may ask you to choose a _mirror_ . A mirror is simply a server that will process your download request. It is usually best to choose the mirror closest that is to where you are working.

Installing an R package does not make it a permanent part of R. Instead, R will only load the packages you have installed when you tell it to do that. This helps to save memory that R can use for manipulating data. To load the package dunn.test, type the command

library(dunn.test)

into the R console. Alternatively, if you are using RStudio, you can go to the “Packages” tab in the bottom right panel of the application window, scroll down until you come to the package dunn.test, and tick the box next to the package name. If you want to unload the package, you can simply untick the box. In native R, you can do the same thing in “Package Manager” window, which you can access from the “Packages & Data” tab on the main menu bar. After you have loaded a package, you can use the commands it contains just like you would use any other command in R. If you close R, any packages you have loaded will be unloaded. They will remain installed, but if you want to use them again you will need to reload them.

Packages that have been written for R have documentation that explains the package and all of the commands it includes. You can find the full - documentation for packages you have downloaded at https://cran.r <u>project.org/web/packages/</u> (or, just do an Internet search).  If you need help for just a single command, you can get the same information directly from the R console. For example, to get help for the command dunn.test(), type

?dunn.test

into the R console. The help file will appear in the “Help” tab or in a floating help window, just as it would for any other R command.

109

### **Index**

AIC. _See_ Akaike's Information Criterion Akaike's Information Criterion, 92–93 analysis of covariance. _See_ ANCOVA analysis of variance. _See_ ANOVA ANCOVA, 91 annotation, 106–7, _See_ R, annotation ANOVA reporting results, 38 variability among groups, 36, 37 variability within groups, 36, 37 variability, total, 35–36 Welch's correction, 42–43 association tests for, 80–81 backward selection. _See_ linear regression _or_ logistic regression, model selection bar charts. _See_ reporting results, bar charts behavioural studies, 11 binomial test assumptions, 74 Binomial test, 71–74 Bonferonni correction, 75–76, 81–82 box-and-whiskers plot, 35 cases. _See_ logistic regression categorical data. _See_ data, categorical causality, 3 chi-squared test for association, 80–81 goodness of fit, 74–75 interpreting, 75–76 reporting results, 76–77 Chromebook, 102 collinearity. _See_ linear regression, collinearity _concordance_ , 70 confidence interval, 26 confounding factors, 5–6 contingency tables, 78, 80 continuous data. _See_ data, continuous control, 2, 4 data array, 104 categorical, 9–10 categorical, 100 continuous, 9 dichotomous, 9, 52–54, 100 discrete, 9 indexing, 16–17, 103–4, 105 mean centring, 51–52, 88–89 numerical, 9, 100 ordinal, 9, 100 quantitative, 47 transforming, 65, 66 types of, 9–10, 100 vector, 104 vectors, 15 degrees of freedom, 26 deviation, 48–50 from the mean, 36 sum of squared, 35–36, 48 dichotomous data. _See_ data, dishotomous discrete data. _See_ data, discrete diversity studies, 10–11 Dunn, Olive Jean, 41, 75

Dunn's test, 41–42 effect size, 6 Essink, Andrew, 13 event, 85 experiments design, 3–9 manipulative, 2–3 observational, 2–3 figures exporting, 107 Fisher, Ronald A., 13, 33, 79 Fisher's exact test, 79, 80–81 focal follow. _See_ sampling methods, focal follow frequentist hypothesis testing, 13 fundamental question of, 18 Games-Howell test, 43 generalised linear model, 89, 94 GLM. _See_ generalised linear model Gosset, William Sealy, 24 grand mean, 35 Hayden, Anne, 13 heteroscedasticity, 68 histograms. _See_ reporting results, histograms hypothesis, 2, 21–22 defining, 17, 23–24 null, 18, 22 indexing. _See_ data, indexing indicator variables, 53 interactions. _See_ linear regression, interactions intercept. _See_ linear regression _or_ logistic regression, intercept Kendall’s tau test, 70 Kramer, Clyde, 39 Kruskal-Wallis test, 41 likelihood, 87, 92 likelihood maximisation, 87 likelihood ratio test, 94 Likert scale, 10, 31 Likert, Rensis, 10 line of best fit, 48–50 linear regression, 47–69 alternatives, 69 assumptions, 64–69 collinearity, 62–64 dichotomous predictors, 52–54 interactions, 57–59 intercept, 51–52 interpreting, 50–51, 51–52, 54–55, 57, 59, 64, 67–69 mean centring, 51–52 model selection, 60–62 multiple, 54–64 outliers, 67 reporting results, 51 residuals, 66 simple, 48–51 _Literary Digest, The_ , 4, 5 log odds ratio, 90 logical operator, 21 logistic function, 85–86 logistic regression, 84–99 assumptions, 99

110

cases, 88 intercept, 88, 94–95 making predictions with, 97 model selection, 90–91, 91–93 reporting results, 93–97 main effects, 57 manipulative experiments. _See_ experiments, manipulative Mann-Whitney U test. _See_ Wilcoxon test mean centring. _See_ data, mean centring measurement error, 6 methods reporting, 93–94 model selection. _See_ linear regression _or_ logistic regression, model selection Monte Carlo method, 18–21 multiple testing, 33, 75, 92 noise. _See_ unexplained variablity _null hypothesis_ . _See_ hypothesis, null numerical data. _See_ data, numerical observational experiments. _See_ experiments, observational observers, correcting for differences between, 8, 46 one-tailed hypothesis tests, 22–23 ordinal data. _See_ data, ordinal outliers, 67 overfitting, 93 packages managing, 109 pairwise comparisons for chi-squared test, with Bonferonni correction, 75–76 for chi-squared, with Bonferonni correction, 81–82 problems with, 33 with Dunn's test, 41–42 permutation, 19 pie charts. _See_ reporting results, pie charts Pinochet, Augusto, 87 power, 6–7 power analysis, 7 predictor (variable), 14 p-values, 21–22 interpreting, 21–22, 94 quadrats. _See_ sampling methods, quadrats R, 101 ANCOVA, 91 annotation, 106–7 ANOVA, one-way, 38 ANOVA, with Welch's correction, 42–43 applying functions to groups with

aggregate, 42 bar charts, 27–29 binomial test, 73–74 box-and-whiskers plot, 35 chickwts, 34 chi-squared goodness of fit test, 74–75 chi-squared test for association, 80–81 colour-coding, 103, 107 contingency tables, 78 counting vector entries, 21, 71–72, 78 Dunn's test, 41–42 Fisher's exact test, 79, 80 for loops, 20

generalised linear model, 89 help with, 108 importing data, 14, 107 indexing. _See_ data, indexing indicator variables, creating, 52–53 Kruskal-Wallis test, 41 linear regression, 50–51, 54–55 logistic regression, 87–93 mean, finding, 18 mean, finding means by group, 36 packages. _See_ packages, managing permutation, 19 pie charts, 76–77 residuals of linear regression, viewing, 66 scatter plots, 48, 51, 55–56 scripting. _See_ scripting showing data, 14–15 Spearman's rank correlation test, 69 t-test, 25–27 working directory. _See_ working directory R<sup>2</sup> value, 50–51 randomness, 4–5 rank correlations tests, 69 rationale, 2 repeatability, 7–8 Repeatability, 8 reporting methods, 93–94 reporting results, 22 ANOVA, 38 bar charts, 27–29, 77 chi-squared test, 76–77 histograms, 15–17 linear regression, 51 logistic regression, 93–97 pie charts, 76–77 scatter plots, 48, 51 t-tests, 27–29 residuals. _See_ linear regression, residuals response (variable), 2, 14 RStudio, 101–7 installing, 101–2 navigating, 102–7 working directory. _See_ working directory RStudio Cloud, 102–7 accessing, 102 importing data, 107 navigating, 102–7 working directory. _See_ working directory sample size, 6, 7, 9 sampling methods, 10–12 focal follow, 11 for behaviour, 11 for diversity, 10–11 quadrats, 10–11 scan sampling, 11 transects, 10–11 sampling unit, 8–9 scan sampling. _See_ sampling methods, scan sampling scatter plots. _See_ reporting results, scatter plots Science, 2 scripting, 17, 105–7 native R, 108 Spearman's rank correlation test, 69 standard error, 28–29

111

sum of squared deviation. _See_ deviation, sum of squared sum of squared error, 37 temporal autocorrelation, 65 time series analysis, 65 transects. _See_ sampling methods, transects transforming data. _See_ data, transforming treatment, 2, 4 t-statistic, 26 t-test alternatives, 30–32 assumptions, 29 one-sample, 24–25 paired, 24–25 reporting results, 27–29 two-sample, 24

Tukey test, _post hoc_ reporting results, 39–40 Tukey, John, 35, 39 two-tailed hypothesis tests, 22–23 types of data. _See_ data, types of unexplained variability, 6–7, 37, 43, 46, 50, 54, 66 vectors. _See_ data, vectors Wald test, 90, 94 Welch’s correction. _See_ ANOVA, Welch's correction Wilcoxon test, 30–31 working directory native R, 108 RStudio, 107 RStudio Cloud, 107

112
