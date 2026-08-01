---
title: "Practical 5(1)"
source: "Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Practical/Week 4/Practical 5(1).docx"
type: document
---

After completing practical 5, you will be able to:

- Create contingency tables to study data with categorical predictors and responses

- Conduct chi squared tests and report the results clearly and concisely

Practical 4

Some of the most striking animal behaviours are involved in mating. Mating success is a key component of fitness in sexually reproducing species, and therefore mating behaviours are under strong selection. This selection can drive the evolution of extreme behaviours and traits, and these in turn can affect how populations persist and interact, and even how entire ecosystems function. This has made mating behaviour an important area of study for evolutionary biologists and ecologists.

In most animal species, females produce fewer and larger gametes than males. This means that the rate of reproduction for both sexes is limited by the number of female gametes available to them, and leads to different reproductive strategies in the sexes. Because reproduction by males is limited by the number of female gametes they can fertilise, males can increase their reproductive success by mating with more females, and they tend not to be very choosy about which females they mate with. Because there are almost always plenty of male gametes available, a female’s reproduction is limited by how many gametes she can produce herself, and having multiple mates may not increase a female’s fitness. However, having high quality mates might, because having high quality paternal genes may make her offspring more fit. As a result, females tend to be choosier than males about mating.

Spiders are an exception to this rule, because female spiders are dangerous. In many spider species, when a male courts a female, she may mate with him or she may kill him. Therefore, evolutionary theory suggests that male spiders should be very choosy, because courtship could end in death!

In 2019, Timothy Meyer and George Uetz published a study of mating behaviour in the brush-legged wolf spider Schizocosa ocreata. Meyer and Uetz were interested in how the mating and hunger status of females affect mate choice in males. Like many spiders, females in the genus Schizocosa can store sperm - one mating per lifetime can be enough to fertilise all her eggs. So, if a female has already mated, will she be less likely to mate if she is courted again? Can males detect this and avoid courting females that have already mated? Hungry females may also be more dangerous, because they might see an approaching male as a potential meal rather than a potential mate. So, are hungry females less likely to mate, and are males less likely to court them? To investigate this, Meyer and Uetz conducted mating trials. In each trial, they set up an arena with one male and one female S. ocreata. The female was either virgin or previously mated, and either recently fed or recently starved. The researchers recorded whether the male in each trial courted the female and whether the pair mated.

You can find Meyer and Uetz (2019)’s data in the file “Meyer_and_Uetz_2019.csv.” Import this data into R as you have in past weeks. I recommend that you name the data set spiders. If you do this, then the starter code for this practical will work without extensive editing. As usual, I recommend looking at the dataset you have imported so you can see what it contains. Here, the columns labelled Female and Male contain the IDs of the animals in each mating trial. In the column MatingStatus, v indicates that the female was virgin and m indicates that she had previously mated. In the column HungerStatus, f indicates that the female had recently eaten and s indicates that she had not.

Question 1

The first question we will ask today is, “Are male S. ocreata more likely to court virgin females than to court females that have already mated?” In this question, our predictor is categorical – a female is either “virgin” or “mated.” Our response is also categorical – a male either courted or he did not. (Last week we saw that we can convert dichotomous categories like these into numerical data – ie, 0s and 1s - for some analyses, but today we will treat these predictors as categories.) Our question is really about association. In particular, is courtship disproportionately associated with the predictor “virgin” and is failure to court disproportionately associated with the predictor “mated?”

Before we attempt to analyse our data, it can be helpful to look at it. You should have already looked at the data in spiders, but unless you are much cleverer than I am, you probably couldn’t see clear patterns just by eye. An easier way to look at associations between categorical variables is with contingency tables. In a contingency table, the rows correspond to one variable and the columns correspond to another. Here our contingency table might take the form:

|  | mated female | virgin female |
| --- | --- | --- |
| courted |  |  |
| did not court |  |  |

Each entry in the table is a count. For example, the cell on the top left would contain the number of males that courted when they met previously mated females, the cell on the top right would contain the number of males courted when they met virgin females, and so on.

The handbook describes how to create a contingency table “by hand” using the aggregate() and matrix() commands. That method is good practice for manipulating data, but R also offers an easier way to do this using the table() command. The table() command takes two vectors with the same length where the entries are categories, pairs the categories at corresponding positions, counts the pairs, and displays or stores them as a table. To see how it works, try

court.mate.table = table( spiders$Courtship, spiders$MatingStatus )

and then look at the result by entering the object name into the R console. You should see a table that looks like this:

m  v

n 20  9

y 54 70

I called my table court.mate.table to remind me what is in it, but you could choose  shorter name if you prefer. The row and column names are not very intuitive, but we can change the names to make the table easier to understand. The commands rownames() and colnames() assign new row and column names to data objects.

rownames( court.mate.table ) = c( "male did not court", "male courted" )

colnames( court.mate.table ) = c( "mated female", "virgin female" )

It is important to assign the right row and column names to the right rows and columns. The table() command puts the rows and columns in alphabetical order according to the category names in the original data. So, here, the row order is n then y and the column order is m then v. But, I think it is easier to just look at the original table to see the row and column order than to try to puzzle it out. After you have renamed the rows and columns, your table should look like this:

mated female virgin female

male did not court           20             9

male courted                 54            70

Q1.1: In how many trials did males court virgin females? In how many trials did males encounter but not court virgin females?

To ask whether there is evidence of a non-random association between the rows and columns in our contingency table, we can use a chi-squared test. This is one of the easiest tests you can do in R. We can simply apply the chisq.test() function to the contingency table we created:

chisq.test( court.mate.table )

Q1.2: Do we have evidence that the mating status of S. ocreata females affects whether males decide to court? How do you know?

How should we report this result? Readers need to know whether there is a significant relationship between female mating status and male courtship decisions, but they also need to know what that relationship is. I might write “Male S. ocreata were more likely to court virgin females (89% females courted) than females that had previously mated ( 73% females courted, p = 0.0239).” We can compute the percentages directly from the contingency table.

There are many ways we might illustrate the results from this analysis. One option would be to present the contingency table itself. As a rule, we cannot simply present raw data to our readers and ask them to sort it out – we need to synthesise the data to make it easy to understand. But, a contingency table is a synthesis. It presents a set of categorical observations as a smaller number of counts. Of course, if we present a contingency table, it will need clear row and column labels and a caption to explain the data, just like any other display item!

Another option for illustrating the results of a chi-squared test is to use a bar chart. You probably remember from practicals 2 and 3 that making bar charts in R can be tedious. One useful (but advanced) attribute of R is that we can create functions to do tedious things for us. A function is just a set of commands that R executes together. We can create a function, give it a name, and when we use that name R will execute the whole set of commands. The starter code for practical 5 creates a function called ct.to.barplot() that converts a contingency table with two rows and appropriate row and column labels into a bar chart. You can activate this function by running the function lines in the starter code, and then you can use it just like you would use any other R function. For this analysis, we can use

ct.to.barplot( court.mate.table )

In general, when choosing how to illustrate the results of an analysis, the best choice may depend on the exact message we want to convey to readers, and there is not always a clear “right” choice for how to do it!

Q1.3: Provide a figure with an appropriate caption to illustrate the results of the analysis above.

Because contingency tables can help us visualise data, they can be extremely useful, and knowing how to create one in R is an important skill. But, we could also execute a chi-squared test without making a contingency table first. To do this, instead of using chisq.test( court.mate.table ) to study the relationship between female mating status and male courtship decisions, we could enter the vectors with courtship and mating status directly into the chisq.test() command:

chisq.test( spiders$Courtship, spiders$MatingStatus )

Run the command above and verify for yourself that it gives the same result as chisq.test( court.mate.table ).

Question 2

Q2.1: Following the logic from question 1, test whether male courtship decisions depended on whether females have recently eaten. Report your results clearly and concisely.

Q2.2: Provide a figure or table to illustrate your result.

Question 3 (Challenge)

In previous weeks, we learned to subset datasets so that we can study just part of the data. Let’s apply that idea now.

In question 1, we found that males were less likely to court females that had previously mated. Presumably, there is a reason for this. We might hypothesise that females that have already mated are less likely to mate again when males court them. If this were true, then males might be less likely to risk courting females who had already mated.

Q3.1: Does Meyer and Uetz’s data provide evidence that, among females that were courted, females were less likely to mate if they had already mated than if they were virgin?

Q3.2: Illustrate your result with a figure or contingency table.

Question 4

Up to this point, the predictor and response variables we have studied in this practical have been dichotomous. That is, each one has had exactly two categories. One of the advantages of the chi-squared test is that we can also use it when our predictor and/or response variables have more than two categories.

In practical 2, we studied data from Tysall and colleagues’ (2020) work on latency to mate in Drosophila. Tysall and colleagues were interested in whether methods of anaesthetising fruit flies affect mating behaviour differently after the flies have recovered from anaesthesia. The purpose of anaesthetising fruit flies is so that they can be marked – marking allows researchers to identify individuals in experiments like mating trials. If different methods for anaesthetising flies have different effects on fruit fly behaviour, then this might confound the results of subsequent experiments.

Just as there are multiple methods for anaesthetising fruit flies, there are multiple methods for marking them. Some of the most common are:

- Wing clipping – a small notch is cut in one wing.

- Powder – flies are dusted with fluorescent powder that adheres to their bodies.

- Marker pen – a small dot is drawn on one wing.

- Paint – a small dot of fluorescent paint is placed on the thorax.

- Dye – coloured dye is added to the flies’ food, and the colour can be seen in the abdomen of the living flies.

Tysall and colleagues’ were interested in whether the marking methods affect the mating success of male flies that have been marked. This might be true if females avoid males with some types of mark. The research team marked 400 male flies with each of the five methods above. Then, they conducted mating trials in which they placed one female, one marked male, and one unmarked male in a “mating arena” - a small universal tube stoppered with cotton – and they recorded which male mated successfully. They ended trials after one mating, so there were no trials in which both flies mated. Some marked males escaped or died before the mating trials, so in the end the team conducted fewer than 400 trials per mark type. You can find the data from Tysall and colleagues’ study in the file "Tysall_et_al_2019b.csv". In this dataset, the column mark_type indicates the method with which the male in each trial was marked (C – wing clipping, D – food dye, Pa – fluorescent paint, Pe – marker pen, or Po – fluorescent powder). The column chosen indicates which male (M – marked or UM – unmarked) mated successfully (ie, was “chosen” by the female).

Q4.1: Does Tysall and colleagues’ data provide evidence that the method used to mark male Drosophila affects their mating success? Report your answer clearly and concisely.

Q4.2: Illustrate your result with a figure or contingency table.

Remember that the chi-squared test, like ANOVA, is an omnibus test. That is, it tells us whether the full set of associations in our contingency table is far enough from the expectation under the null (the value we would expect by chance if there were no associations between the categories) that is unlikely to be due to chance. If that is true, then we infer that the associations are not due to chance, and therefore that there is some real relationship between the predictors. However, the chi-squared test does NOT tell us which groups are significantly differently from which others. If we want to know that, we will need to conduct additional tests. This is discussed in more detail in the handbook.

Question 5

One of the goals of this unit is for you to be able to choose appropriate statistical tests from among those we have studied to test specific hypotheses. Questions 5 and 6 give you an opportunity to try this. Answer the questions below using some method or combination of methods from among those we have learned in this unit so far.

In 2020, University of Manchester student Cameron Longbottom did a research placement at the Smithsonian Tropical Research Institute in Gamboa, Panama. Longbottom studied the matador bug, Anisoscelis alipes. The matador bug is one of a group of closely related insects commonly referred to as “flag-footed bugs.” These bugs have large tibial

plates on their hindmost limbs (figure 1). The function of these plates is not known, but it is widely believed that they are advertisements of mate quality used by males when courting females. This would be consistent with Zahavi’s (1975) “handicap principle.” This idea argues that conspicuous traits like tibial plates are costly because they make animals less agile and more noticeable to predators. If a male can collect enough energy to develop such a costly trait and can survive while carrying it, he must be very fit otherwise. So, these traits act as an advertisement of his “good genes” to potential mates. Longbottom and his collaborator Ummat Somjee hypothesised that, if conspicuous tibial plates are advertisements of male quality used in courtship, then males would have relatively larger tibial plates than females. Furthermore, they hypothesised that the size of tibial plates would increase with the size of the animal, and it would increase faster in males than in females. This latter is because males that can collect enough resources to grow large would benefit from investing relatively more energy in their costly sexual signals. You can read more about this in Longbottom and colleagues’ (2022) work here.

You can find Longbottom and colleague’s (2022) data in the file “data from Longbottom et al 2022.csv”. In this data, ID is an identifying number for each individual and sex reports the sex of the individual. The column pw reports the width of the pronotum, a hard plate that covers the thorax of most beetle species. Longbottom and colleagues used the pronotum width as a surrogate for the size of the individual. The column flag.area reports the mean area of each individual’s tibial plates. The dataset also includes the lengths of the tibia, forewing, and hindwing. All lengths are in cm and areas are in cm2.

Before starting your analysis, I recommend that you log the measures of body size in the data set. Logging homogenises variability in body measurements, and linearises the relationship between length and area. If you named your data set matador.data, then you could add a logged version of (for example) pw to the data set using the code:

matador.data$log.pw = log( matador.data$pw )

Then, you can use the logged measures of body size in your analyses. (When you log some variables, you will get a warning that says “NAs introduced by coercion.” Here, this is because there is missing data for some of the individual matador bugs in the data set. When R tries to log the missing data, it returns NA, which means not a number. That is fine, because missing data really is not a number! R will ignore individuals with missing data in the analysis, and that is exactly what we want it to do. So, this warning is a good thing to notice, but it is not a problem.)

Q5.1: Test the hypotheses that i) controlling for pronotum width, males have larger tibial plates than females; and ii) the size of the tibial plate increases with pronotum width faster in males than in females. Report your results clearly and concisely. Does your result support the hypothesis that tibial plates are a signal of male quality in the matador bug?

Q5.2: Provide a figure to illustrate your result.

Question 6

Q6.1: Test the hypothesis that tibia length in A. alipes changes with forewing length. Report your results clearly and concisely.

Q6.2: Test the hypothesis that tibia length in A. alipes changes with hindwing length. Report your results clearly and concisely.

Q6.3 (Super-challenge): Test the hypothesis that tibia length in A. alipes changes with hindwing length when controlling for forewing length. Report your results clearly and concisely. Can you explain why the result in Q6.3 is different from the result in Q6.1? (The answer is not just that forewing length is in the model – that is given. The question is, why does that matter?)

References

Longbottom, C., Falk, J. J., Greenway, E. V., Johnson, M. G., Ramos, C., Rößler, D. C., . . . Somjee, U. (2022). Why does the matador bug, Anisoscelis alipes (Hemiptera: Coreidae), wave its brightly colored legs? Journal of Insect Behavior, 35, 171-182. doi:10.1007/s10905-022-09809-0

Meyer, T. B., & Uetz, G. W. (2019). Complex male mate choice in the brush-legged wolf spider Schizocosa ocreata (Hentz). Behavioral Ecology, 30(1), 27-38. doi:10.1093/beheco/ary172

Tysall, E. E., Pembury Smith, M. Q. R., & Gilman, R. T. (2020). The effects of marking methodology on mate choice in Drosophila melanogaster. Animal Behaviour and Cognition, 7(4), 492-504. doi:10.26451/abc.07.04.02.2020

Zahavi, A. (1975). Mate selection - a selection for a handicap. Journal of Theoretical Biology, 53(1), 205-214. doi:10.1016/0022-5193(75)90111-3.
