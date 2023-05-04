Download Link: https://assignmentchef.com/product/solved-cs698x-assignment-1
<br>
(When You Integrate Out..) Suppose <em>x </em>is a scalar random variable drawn from a univariate Gaussian <em>p</em>(<em>x</em>|<em>η</em>) = N(<em>x</em>|0<em>,η</em>). The variance <em>η </em>itself is drawn from an exponential distribution: <em>p</em>(<em>η</em>|<em>γ</em>) = Exp(<em>η</em>|<em>γ</em><sup>2</sup><em>/</em>2), where <em>γ &gt; </em>0. Note that the exponential distribution is defined as Exp(<em>x</em>|<em>λ</em>) = <em>λ</em>exp(−<em>λx</em>). Derive the expression of the marginal distribution of <em>x</em>, i.e., <em>p</em>(<em>x</em>|<em>γ</em>) = <sup>R </sup><em>p</em>(<em>x</em>|<em>η</em>)<em>p</em>(<em>η</em>|<em>γ</em>)<em>dη </em>after integrating out <em>η</em>. What does the marginal distribution <em>p</em>(<em>x</em>|<em>γ</em>) mean?

Plot both <em>p</em>(<em>x</em>|<em>η</em>) and <em>p</em>(<em>x</em>|<em>γ</em>) and include in the writeup PDF itself. What difference do you see between the shapes of these two distributions? Note: You don’t need to submit the code used to generate the plots. Just the plots (appropriately labeled) are fine.

Hint: You will notice that <sup>R </sup><em>p</em>(<em>x</em>|<em>η</em>)<em>p</em>(<em>η</em>|<em>γ</em>)<em>dη </em>is a hard to compute integral. However, the solution does have a closed form expression. One way to get the result is to compute the moment generating function (MGF)<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>of <sup>R </sup><em>p</em>(<em>x</em>|<em>η</em>)<em>p</em>(<em>η</em>|<em>γ</em>)<em>dη </em>(note that this is a p.d.f.) and compare the obtained MGF expression with the MGFs of various p.d.f.s given in the table on the following Wikipedia page: <a href="https://en.wikipedia.org/wiki/Moment-generating_function">https://en.wikipedia.org/wiki/ </a><a href="https://en.wikipedia.org/wiki/Moment-generating_function">Moment-generating_function</a><a href="https://en.wikipedia.org/wiki/Moment-generating_function">,</a> and identify which p.d.f.’s MGF it matches with. That will give you the form of distribution <em>p</em>(<em>x</em>|<em>γ</em>). Specifically, name this distribution and identify its parameters.

<h1>Problem 2</h1>

(It Gets Better..) Recall that, for a Bayesian linear regression model with likelihood <em>p</em>(<em>y</em>|<em>x</em><em>,w</em>) = N(<em>w</em><sup>&gt;</sup><em>x</em><em>,β</em><sup>−1</sup>) and prior <em>p</em>(<em>w</em>) = N<em>or</em>(0<em>,λ</em><sup>−1</sup><strong>I</strong>), the <em>predictive posterior </em>

N(<em>µ</em><sup>&gt;</sup><em><sub>N</sub></em><em>x</em><sub>∗</sub><em><sup>,σ</sup></em><em><sub>N</sub></em><sup>2 </sup>(<em>x</em><sub>∗</sub>)), where we have definedand Σ<em><sub>N </sub></em>are the mean and covariance matrix of the Gaussian posterior on <em>w</em>, s.t., and .

Here, we have used the subscript <em>N </em>to denote that the model is learned using <em>N </em>training examples. As the training set size <em>N </em>increases, what happens to the variance of the predictive posterior? Does it increase or decrease or remain the same? You must also prove your answer formally. You might find the following identity useful: You may make use the following matrix identity:

&gt; −1                           −1 − (<strong>M</strong>−1<em>v</em>)(<em>v</em>&gt;<strong>M</strong>−1)

(<strong>M </strong>+ <em>vv </em>)          = <strong>M            </strong>

1 + <em>v</em>&gt;<strong>M</strong>−1<em>v</em>

Where <strong>M </strong>denotes a square matrix and <em>v </em>denotes a column vector.

<h1>Problem 3</h1>

(Distribution of Empirical Mean of Gaussian Observations) Consider <em>N </em>scalar-valued observations <em>x</em><sub>1</sub><em>,…,x<sub>N </sub></em>drawn i.i.d. from N(<em>µ,σ</em><sup>2</sup>). Consider their empirical mean. Representing the empirical mean as a linear transformation of a random variable, derive the probability distribution of <em>x</em>¯. Briefly explain why the result makes intuitive sense.

<h1>Problem 4</h1>

(Benefits of Probabilistic Joint Modeling-1) Consider a dataset of test-scores of students from <em>M </em>schools in a district: <em>x</em>, where <em>N<sub>m </sub></em>denotes the number of students in school <em>m</em>.

Assume the scores of students in school <em>m </em>are drawn independently as where the Gaussian’s mean <em>µ<sub>m </sub></em>is unknown and the variance <em>σ</em><sup>2 </sup>is same for all schools and known (for simplicity). Assume the means <em>µ</em><sub>1</sub><em>,…,µ<sub>M </sub></em>of the <em>M </em>Gaussians to also be Gaussian distributed where <em>µ</em><sub>0 </sub>and are hyperparameters.

<ol>

 <li>Assume the hyperparameters <em>µ</em><sub>0 </sub>and to be known. Derive the posterior distribution of <em>µ<sub>m </sub></em>and write down the mean and variance of this posterior distribution. Note: While you can derive it the usual way, the derivation will be much more compact if you use the result of Problem 2 and think of each school’s data as a <em>single </em>observation (the empirical mean of observations) having the distribution derived in Problem 3.</li>

 <li>Assume the hyperparameter <em>µ</em><sub>0 </sub>to be unknown (but still keep as fixed for simplicity). Derive the marginal likelihood and use MLE-II to estimate <em>µ</em><sub>0 </sub>(note again that <em>σ</em><sup>2 </sup>and are known here). Note: Looking at the form/expression of the marginal likelihood, if the MLE-II result looks obvious to you, you may skip the derivation and directly write the result.</li>

 <li>Consider using this MLE-II estimate of <em>µ</em><sub>0 </sub>from part (2) in the posteriors of each <em>µ<sub>m </sub></em>you derived in part (1). Do you see any benefit in using the MLE-II estimate of <em>µ</em><sub>0 </sub>as opposed to using a known value of <em>µ</em><sub>0</sub>?</li>

</ol>

<h1>Problem 5</h1>

(Benefits of Probabilistic Joint Modeling-2) Suppose we have student data from <em>M </em>schools where <em>N<sub>m </sub></em>denotes the number of students in school <em>m</em>. The data for each school <em>m </em>= 1<em>,…,M </em>is in the following form: For student <em>n </em>in school <em>m</em>, there is a response variable (e.g., score in some exam) and a feature vector

<em>x</em>.

Assume a linear regression model for these scores, i.e.,, where <em>w</em><em><sub>m </sub></em>∈ R<em><sup>D </sup></em>denotes the regression weight vector for school <em>m</em>, and <em>β </em>is known. Note that this can also be denoted as <em>p</em>(<em>y</em><sup>(<em>m</em>)</sup>|<strong>X</strong><sup>(<em>m</em>)</sup><em>,</em><em>w</em><em><sub>m</sub></em>) = N(<em>y</em><sup>(<em>m</em>)</sup>|<strong>X</strong><sup>(<em>m</em>)</sup><em>w</em><em><sub>m</sub></em><em>,β</em><sup>−1</sup><strong>I</strong><em><sub>N</sub></em>), where <em>y</em><sup>(<em>m</em>) </sup>is <em>N<sub>m </sub></em>× 1 and <strong>X</strong><sup>(<em>m</em>) </sup>is <em>N<sub>m </sub></em>× <em>D</em>. Assume a prior <em>p</em>(<em>w</em><em><sub>m</sub></em>) = N(<em>w</em><em><sub>m</sub></em>|<em>w</em><sub>0</sub><em>,λ</em><sup>−1</sup><strong>I</strong><em><sub>D</sub></em>), <em>λ </em>to be known and <em>w</em><sub>0 </sub>to be unknown.

Derive the expression for the log of the MLE-II objective for estimating <em>w</em><sub>0</sub>. You do not need to optimize this objective w.r.t. <em>w</em><sub>0</sub>; just writing down the final expression of objective function is fine. Also state what is the benefit of this approach as opposed to fixing <em>w</em><sub>0 </sub>to some value, if our goal is to learn the school-specific weight vectors <em>w</em><sub>1</sub><em>,…,w</em><em><sub>M</sub></em>? (Feel free to make direct use of properties of Gaussian distributions).

<h1>Problem 6 : Programming Assignment</h1>

(Bayesian Linear Regression) Consider a toy data set consisting of 10 training examples with each input <em>x<sub>n </sub></em>as well as the output <em>y<sub>n </sub></em>being scalars. The data is given below.

<em>x </em>= [−2<em>.</em>23<em>,</em>−1<em>.</em>30<em>,</em>−0<em>.</em>42<em>,</em>0<em>.</em>30<em>,</em>0<em>.</em>33<em>,</em>0<em>.</em>52<em>,</em>0<em>.</em>87<em>,</em>1<em>.</em>80<em>,</em>2<em>.</em>74<em>,</em>3<em>.</em>62]; <em>y </em>= [1<em>.</em>01<em>,</em>0<em>.</em>69<em>,</em>−0<em>.</em>66<em>,</em>−1<em>.</em>34<em>,</em>−1<em>.</em>75<em>,</em>−0<em>.</em>98<em>,</em>0<em>.</em>25<em>,</em>1<em>.</em>57<em>,</em>1<em>.</em>65<em>,</em>1<em>.</em>51]

We would like to learn a Bayesian linear regression model using this data, assuming a Gaussian likelihood model for the outputs with fixed noise precision <em>β </em>= 4. However, instead of working with the original scalar-valued inputs, we will map each input <em>x </em>using a degree-<em>k </em>polynomial as <em>φ<sub>k</sub></em>(<em>x</em>) = [1<em>,x,x</em><sup>2</sup><em>,…,x<sup>k</sup></em>]<sup>&gt;</sup>. Note that, when using the mapping <em>φ<sub>k</sub></em>, each original input becomes <em>k </em>+ 1 dimensional. Denote the entire set of mapped inputs as <em>φ<sub>k</sub></em>(<em>x</em>), a 10 × (<em>k </em>+ 1) matrix. Consider <em>k </em>= 1<em>,</em>2<em>,</em>3 and 4, and learn a Bayesian linear regression model for each case. Assume the following prior on the regression weights: <em>p</em>(<em>w</em>) = N(<em>w</em>|<strong>0</strong><em>,</em>I) with <em>w </em>∈ R<em><sup>k</sup></em><sup>+1</sup>.

<ol>

 <li>For each <em>k</em>, compute the posterior of <em>w </em>and show a plot with 10 random functions drawn from the inferred posterior (show the functions for the input range <em>x </em>∈ [−4<em>,</em>4]). Also show the original training examples on the same plot to illustrate how well the functions fit the training data.</li>

 <li>For each <em>k</em>, compute and plot the mean of the posterior predictive <em>p</em>(<em>y</em><sub>∗</sub>|<em>φ<sub>k</sub></em>(<em>x</em><sub>∗</sub>)<em>,φ<sub>k</sub></em>(<em>x</em>)<em>,</em><em>y</em><em>,β</em>) on the interval <em>x</em><sub>∗ </sub>∈ [−4<em>,</em>4]. On the same plot, also show the predictive posterior mean plus-and-minus two times the predictive posterior standard deviation.</li>

 <li>Compute the log marginal likelihood log<em>p</em>(<em>y </em>| <em>φ<sub>k</sub></em>(<em>x</em>)<em>,β</em>) of the training data for each of the 4 mappings <em>k </em>= 1<em>,</em>2<em>,</em>3<em>,</em>4. Which of these 4 “models” seems to explain the data the best?</li>

 <li>Using the MAP estimate <em>w</em><em><sub>MAP</sub></em>, Compute the log likelihood log<em>p</em>(<em>y</em>|<em>w</em><em><sub>MAP</sub></em><em>,φ<sub>k</sub></em>(<em>x</em>)<em>,β</em>) for each <em>k</em>. Which of these 4 models seems to have the highest log likelihood? Is your answer the same as that based on the log marginal likelihood (part 3)? Which of these two criteria (highest log likelihood or highest log marginal likelihood) do you think is more reasonable to select the best model and why?</li>

 <li>For your best model, suppose you could include an additional training input <em>x</em><sup>0 </sup>(along with its output <em>y</em><sup>0</sup>) to “improve” your learned model using this additional example. Where in the region <em>x </em>∈ [−4<em>,</em>4] would you like the chosen <em>x</em><sup>0 </sup>to be? Explain your answer briefly,</li>

</ol>

Your implementation should be in Python notebook (and should not use an existing implementation of Bayesian linear regression from any library).

Submit the plots as well as the code in a single zip file (named yourrollnumber.zip).

<a href="#_ftnref1" name="_ftn1">[1]</a> MGF of a p.d.f. <em>p</em>(<em>x</em>) is defined as