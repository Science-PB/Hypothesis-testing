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


Reviewing the results of the test in Figure 2, a relatively high t-value is seen paired with a near
zero probability value. Since the p-value is well below the alpha, or significance value, of 0.05 the
determination is to reject the null hypothesis, stating that there is not enough evidence to support the
claim that male and female cats have the same body weight.
The final t-test being performed is a paired t-test. For this case, the dataset “shoes”, again from
R package “MASS” will be utilized, which provides the wear of shoes for material A and B for each foot
of 10 boys. In this experiment, the intent is to determine whether material A wore better than material
B. Overall, there is limited information on this particular dataset so the following assumptions are made:a higher value means more wear and when assessing if material A wore better, the assumption is that
less wear equates to wearing better. The R-code applied, and results can be seen in Figure 3.


In this experiment the intent is to find if material A wore better, i.e. had less wear, than material
B, so the null hypothesis is set up as the materials having the same wear or material B wearing better,
and the alternate hypothesis is set up as material A having less wear than material B. As seen in Figure
3, a negative t-value is achieved. A negative t-value simply indicates a reversal in directionality and has
no bearing on the significance (Gillespie, 2018). As in the other t-tests, again a larger t-value and low p-
value are attained. With these results, the decision can be made to reject the null hypothesis and
express that there is enough evidence to support the claim that material A wore better than material B.

# Test of Equal or Given Proportions
