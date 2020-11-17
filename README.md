# Hypothesis-testing
T-Tests, Test of Equal or Given Proportions, F-Test

# Introduction

Hypothesis testing is a foundational concept to be aware of when exploring elementary statistics and
its uses. At the very core of hypothesis testing is the assignment of a null and alternative hypothesis.
The outcome of hypothesis testing is a rejection or acceptance of the null hypothesis. There are multiple
statistical tests that can be performed and choosing the correct one is important along with the
appropriate level of significance which is the probability of committing an error. This paper will look into
five different hypothesis tests performed in R, on various datasets and evaluate their outcomes.

# Hypothesis Testing with R

Depending on the intended objective of a hypothesis test there are many different ways it can be
approached. Based on the objectives and the data itself, the proper statistical procedure can be
selected, for instance if the intent is to understand the difference between means or whether the
relationship between variables is statistically significant (Frost, 2020). Regardless of the statistical test
being applied, a core component to hypothesis testing is the identification of a null and alternative
hypothesis. A null hypothesis states either that a difference does not exist between a parameter and a
specific value or a difference does not exist between two parameters, while the alternative hypothesis
states there is a difference (Bluman, 2018). They are represented as H0 and Ha respectively, through
the R-code Figures presented throughout this report
In addition to the assignment of hypotheses there is the general makeup of the tests that
ultimately leads to the decision made on whether to accept or reject a null hypothesis. These include
the test statistic, a level of significance, probability value (p-value) and confidence intervals. As various
tests are performed throughout this report, these values will be assessed to provide a decision on the
acceptance or rejection of each test’s null hypothesis.

# T-Tests

In this report three types of t-tests will be performed, one-sample, two-sample and paired. A one-
sample t-test is used to determine whether a sample mean is statistically different from a hypothesized

or known population mean (Kent State University, 2020). A two-sample t-test determines if there is a
difference between two population means (Stat Trek, 2020). The paired sample t-test also determines if
there is a difference between means, an important component to note however is that the observations
are dependent.
For the use of a one-sample t-test, the dataset “chem” from the R package “MASS” will be
utilized. This dataset contains 24 determinations of copper in whole meal flour. What is being evaluated is if the flour production company is producing whole meal flour with greater than 1 part per million of
copper. The R-code for a one-sample t-test and the results can be seen in Figure 1.

<img width="723" alt="Screen Shot 2020-11-16 at 8 11 25 PM" src="https://user-images.githubusercontent.com/66921930/99327569-3bbe0f80-2848-11eb-8260-ba7a92eb6b2e.png">


Based on the question posed, a null hypothesis representing that the copper in whole meal flour
is equal to or less than 1 part per million is generated with the alternative hypothesis being that there is
greater than 1 part per million copper in whole meal flour. A significance level of 95% is utilized, this
determines that if the null hypothesis is rejected there is a 5% chance of a type I error, which is
rejecting the null hypothesis when it is true. Looking at the results in Figure 1, the sample mean is 4.28,
well above our null of 1. With a t-value of 3.03 and a p-value that is quite significantly smaller than our
alpha, or significance level, of 0.05, all of this lends to the decision to reject the null hypothesis that the
amount of copper per whole meal flour is equal or less than 1 part per million. In fact, what has been
determined is the probability of erroneously rejecting the null hypothesis is only 0.3%. Based on the
95% confidence interval, it can be noted that there is a 95% chance that the confidence interval of 2.43
to infinity contains the true mean of the population (GraphPad, n.d.).
For the second, two-sample t-test, the dataset “cats” from the R package “MASS” was applied
with the intent to determine if male and female cat samples have the same body weight. Based on theintent of the experiment, the null hypothesis is assigned as the body weight of male cats equals the
body weight of female cats, with the null hypothesis being the body weights are not equal. Figure 2
provides the R-code and results of running a two-sample t-test to make this determination.

<img width="728" alt="Screen Shot 2020-11-16 at 8 12 07 PM" src="https://user-images.githubusercontent.com/66921930/99327572-3bbe0f80-2848-11eb-9e86-0fae07e47a09.png">

Reviewing the results of the test in Figure 2, a relatively high t-value is seen paired with a near
zero probability value. Since the p-value is well below the alpha, or significance value, of 0.05 the
determination is to reject the null hypothesis, stating that there is not enough evidence to support the
claim that male and female cats have the same body weight.
The final t-test being performed is a paired t-test. For this case, the dataset “shoes”, again from
R package “MASS” will be utilized, which provides the wear of shoes for material A and B for each foot
of 10 boys. In this experiment, the intent is to determine whether material A wore better than material
B. Overall, there is limited information on this particular dataset so the following assumptions are made:a higher value means more wear and when assessing if material A wore better, the assumption is that
less wear equates to wearing better. The R-code applied, and results can be seen in Figure 3.

<img width="720" alt="Screen Shot 2020-11-16 at 8 12 49 PM" src="https://user-images.githubusercontent.com/66921930/99327575-3c56a600-2848-11eb-8499-447fcd6919bf.png">

In this experiment the intent is to find if material A wore better, i.e. had less wear, than material
B, so the null hypothesis is set up as the materials having the same wear or material B wearing better,
and the alternate hypothesis is set up as material A having less wear than material B. As seen in Figure
3, a negative t-value is achieved. A negative t-value simply indicates a reversal in directionality and has
no bearing on the significance (Gillespie, 2018). As in the other t-tests, again a larger t-value and low p-
value are attained. With these results, the decision can be made to reject the null hypothesis and
express that there is enough evidence to support the claim that material A wore better than material B.

# Test of Equal or Given Proportions
Moving forward from t-tests another hypothesis testing option is the test of equal or given
proportions. This type of test is utilized for when the intent is to test that the probabilities of success in
several groups are the same or equal to specific given values (Penn State, n.d.). A count of successes
and failures as well as a count of trials is used to enable calculations to be run. To showcase the use of this type of test, the “bacteria” dataset is used from R package “MASS” to determine if an applied drug
treatment had a significant effect on the presence of bacteria compared with the placebo. The null
hypothesis is written as the combination of drug and drug+ with bacteria present in the dataset is equal
to or less than that of the placebo. The alternative hypothesis is that the presence of bacteria is greater
in those that received drug or drug+ than those that received the placebo. Figure 4 showcases the R-
code used and the results of running a prop.test.

<img width="738" alt="Screen Shot 2020-11-16 at 8 16 32 PM" src="https://user-images.githubusercontent.com/66921930/99327868-dfa7bb00-2848-11eb-9aad-183e55b12639.png">


From the results in Figure 4, the calculated p-value of 0.98 is significantly larger than the
predetermined alpha, or significance value, of 0.05. Unlike previous tests run, this results in the
determination to not reject the null hypothesis. Ultimately what this states is that there is not enough
evidence to reject the claim that there is equal or less of a presence of bacteria in those that took the
drug or drug+ when compared to those that took the placebo, with a 0.75 to 0.86 sample estimate. A confidence interval of -0.22 to 1 provides the difference between the proportions of the drug versus
placebo.

# F-Test

The final test to be conducted is the f-Test, which is utilized to test variance versus the t-test
which tests means (Minitab, 2016). The use of a two-tailed f-test examines whether the variances of
two populations are either equal to each other or not (Nist Sematech, n.d.). For the purposes of
demonstrating an f-test, the “cats” dataset will again be utilized. Unlike the t-test which tested whether
male and female cat samples had the same bodyweight, the f-test will look at the variance in
bodyweight in male and female cats. Figure 5 provides the R-code utilized and results of a two-tailed f-
test. 

<img width="740" alt="Screen Shot 2020-11-16 at 8 17 36 PM" src="https://user-images.githubusercontent.com/66921930/99327869-dfa7bb00-2848-11eb-9217-98fc5cf49ad3.png">

The null hypothesis utilized in this scenario reflects that there is no variance between the body
weights of cats regardless of gender. The alternate hypothesis states that there is a statistically
significant difference. Utilizing an alpha, or significance, of 0.05 and comparing that against the p-value of 0.0001 obtained, the determination is to reject the null hypothesis. There is enough evidence to
support the claim that there is a difference in the variance of body weight between male and female
cats. The ratio variance between the two populations in this example is calculated as 2.91.

# Conclusion

Data analysis is the cornerstone of modern analytics. To analyze data properly and make
determinations from experiments, a solid understanding of the different methods of hypothesis testing
is necessary. There are several criticisms in the environment regarding the use of hypothesis testing.
Many of these criticisms however, come from a lack of understanding that hypothesis testing is meant
as a way to make a determination of a hypothesis and is subject to error, it is not an absolute truth. As
there are many different types of hypothesis testing out there, another component is ensuring the right
test is conducted based on the dataset along with an appropriate null and alternate hypothesis used.
When the wrong test is utilized, or a hypothesis is not appropriately structured, the result can be deeply
flawed, and improper assumptions can be made when identifying what claim to make. One of the most
significant values when making a determination from a hypothesis test is the p-value. As showcased
throughout this report, the p-value and where it fell in regards to the significance value utilized was a
main contributor in determining whether to accept or reject a null hypothesis and it was also an output
value of every single hypothesis test utilized.
Inferential statistics is fundamental to the field through its determination of relationships
between variables and making predictions (Bluman, 2018). This makes hypothesis testing one of the
main tools utilized in this space, validating its necessity to the field of statistics.

# References

Frost, J. (2020). Statistical Hypothesis Testing Overview. Statistics by Jim. Retrieved from:
https://statisticsbyjim.com/hypothesis-testing/statistical-hypothesis-testing-overview/

Bluman, A. (2018). Elementary Statistics: A Step by Step Approach (10th ed.). New York, NY: McGraw-
Hill Education.

Kent State University. (2020). SPSS Tutorials: One Sample T Test. Kent State University. Retrieved from:
https://libguides.library.kent.edu/SPSS/OneSampletTest

Stat Trek. (2020) 1.3.5.3 Two-Sample t-Test. Stat Trek. Retrieved from:
https://www.itl.nist.gov/div898/handbook/eda/section3/eda353.htm

GraphPad. (n.d.). Interpreting a confidence interval of a mean. GraphPad. Retrieved from:
https://www.graphpad.com/guides/prism/7/statistics/stat_more_about_confidence_interval.htm

Gillespie, C. (2018, June). What Does a Negative T-Value Mean? Sciencing. Retrieved from:
https://sciencing.com/negative-tvalue-mean-6921215.html

Penn State. (n.d.). Test of Equal or Given Proportions. Penn State. Retrieved from:
https://astrostatistics.psu.edu/su07/R/html/stats/html/prop.test.html

Nist Sematech. (n.d.). 1.3.5.9. F-Test for Equality of Two Variances. Nist Sematech. Retrieved from:
https://www.itl.nist.gov/div898/handbook/eda/section3/eda359.htm
