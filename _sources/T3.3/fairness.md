# Fairness notions and metrics

## In brief

## More in Detail

The term fairness is defined as the quality or state of being fair; or a
lack of favoritism towards one side. However, like {doc}`bias`, fairness can
mean different concepts to different peoples, different contexts, and
different disciplines. The definition of fairness in various disciplines
is detailed in {cite}`mulligan2019thing`. An unfair model produces results
that are skewed towards particular individuals or groups. The primary
sources of this unfairness are the presence of biases. There are two
important categories of biases which play crucial role in fairness; (i)
technical bias and (ii) social bias. Technical biases can be traced back
to the sources , but social biases are very difficult to fix as these
are a matter of politics, perspectives, and shifts in prejudices and
preconceptions that can take years to change {cite}`wachter2020bias`. Most of
the state-of-the-art techniques tackle technical errors, but it cannot
resolve the root causes of bias. Based on this observation, Sandra et al.
{cite}`wachter2020bias` proposed three responses concerning algorithmic bias
and resulting social inequality. The first is not an active choice as it
allows the system to get worse and do nothing to fix biases. Second,
incorporate techniques to fix technical errors and maintain a status quo
to ensure that the system do not make it worse. Much works in fairness
focused on this option, called 'bias preserving fairness', maintains a
status quo as a baseline, aligns with the formal equality of EU
non-discrimination law. Finally, 'bias transforming fairness', the third
response focuses on the substantive equality of EU non-discrimination
which can only be achieved by accounting for historical (social)
inequalities. As argued in {cite}`wachter2020bias`, users
(developers,deployers etc.) should give preference to 'bias
transforming' fairness metrics, when a fairness metric is used to make
substantive decisions about people in contexts where significant
disparity has been previously observed.

The notions of fairness fall under individuals, groups and sub-groups.
Individual fairness ensures that similar individuals should be treated
similarly. It accounts for the distance measures to evaluate the
similarity of individuals {cite}`john2020verifying,biega2018equity`. On
the other hand, group fairness compares quantities at the group level
primarily identified by protective features such as gender, ethnicity
etc. etc. {cite}`cheng2020group,conitzer2019group`. Sub-group fairness is
more rigid than group fairness as this ensures fairness concerning one
or more structured sub-groups defined by sensitive features,
interpolates between individual and group fairness notions
{cite}`kearns2018preventing`. According to {cite}`kleinberg17`, it is impossible
to satisfy all of the above notions, leading to conflicts between
fairness definitions. Therefore, one suggestion could be to select
appropriate fairness criteria and use those based on the application and
deployment. Another concern has risen in {cite}`liu2018delayed`, temporal
aspects of fairness notions may harm the sensitive groups over time if
not updated.

**Some widely used fairness metrics:** In order to recall some widely
used fairness metrics we need to introduce some notation. Let $V$, $A$,
and $X$ be three random variables representing, respectively, the total
set of features, the sensitive features, and the remaining features
describing an individual such that $V=(X,A)$ and $P(V=v_i)$ represents
the probability of drawing an individual with a vector of values $v_i$
from the population. For simplicity, we focus on the case where $A$ is a
binary random variable where $A=0$ designates the protected group, while
$A=1$ designates the non-protected group. Let $Y$ represent the actual
outcome and $\hat{Y}$ represent the outcome returned by the prediction
algorithm. Without loss of generality, assume that $Y$ and $\hat{Y}$ are
binary random variables where $Y=1$ designates a positive instance,
while $Y=0$ a negative one. Typically, the predicted outcome $\hat{Y}$
is derived from a score represented by a random variable $S$ where
$P([)S = s]$ is the probability that the score value is equal to $s$.

**Statistical parity** {cite}`dwork2012fairness` is one of the most commonly
accepted notions of fairness. It requires the prediction to be
statistically independent of the sensitive feature $(\hat{Y}  \perp A)$.
In other words, the predicted acceptance rates for both protected and
unprotected groups should be equal. Statistical parity implies that<br>
$\displaystyle \frac{TP+FP}{TP+FP+FN+TN}$ [^statistical] <br>
is equal for both groups. A classifier Ŷ satisfies statistical parity
if:<br> 
$\label{eq:sp} P([)\hat{Y} \mid A = 0] = P([)\hat{Y} \mid A = 1].$ <br>

**Conditional statistical parity** {cite}`corbett2017algorithmic` is a
variant of statistical parity obtained by controlling on a set of
resolving features[^parity]. The resolving features (we refer to them as $R$)
among $X$ are correlated with the sensitive feature $A$ and give some
factual information about the label at the same time leading to a
*legitimate* discrimination. Conditional statistical parity holds if: <br>
$\label{eq:csp}
P([)\hat{Y}=1 \mid R=r,A = 0] = P([)\hat{Y}=1 \mid R=r,A = 1] \quad \forall r \in range(R).$

**Equalized odds** {cite}`hardt2016equality` considers both the predicted and
the actual outcomes. The prediction is conditionally independent from
the protected feature, given the actual outcome
$(\hat{Y} \perp A \mid Y)$. In other words, equalized odds requires that
both sub-populations to have the same true positive rate
$TPR = \frac{TP}{TP+FN}$ and false positive rate
$FPR = \frac{FP}{FP+TN}$: <br>
$\label{eq:eqOdds}
P([)\hat{Y} = 1 \mid Y=y,\; A=0] = P([)\hat{Y}=1 \mid Y= y,\; A=1]  \quad \forall{ y \in \{0,1\}}.$

Because equalized odds requirement is rarely satisfied in practice, two
variants can be obtained by relaxing its equation. The first one is
called **equal opportunity** {cite}`hardt2016equality` and is obtained by
requiring only TPR equality among groups: <br>
$\label{eq:eqOpp}
P([)\hat{Y}=1 \mid Y=1,A = 0] = P([)\hat{Y}=1\mid Y=1,A = 1].$ <br>
As $TPR$
does not take into consideration $FP$, equal opportunity is completely
insensitive to the number of false positives.

The second relaxed variant of equalized odds is called **predictive
equality** {cite}`corbett2017algorithmic` which requires only the FPR to be
equal in both groups: <br>
$\label{eq:predEq}
P([)\hat{Y}=1 \mid Y=0,A = 0] = P([)\hat{Y}=1\mid Y=0,A = 1].$ <br> 
Since $FPR$ is independent from $FN$, predictive equality is completely
insensitive to false negatives.

**Conditional use accuracy equality** {cite}`berk2018fairness` is achieved
when all population groups have equal positive predictive value
$PPV=\frac{TP}{TP+FP}$ and negative predictive value
$NPV=\frac{TN}{FN+TN}$. In other words, the probability of subjects with
positive predictive value to truly belong to the positive class and the
probability of subjects with negative predictive value to truly belong
to the negative class should be the same. By contrast to equalized odds,
one is conditioning on the algorithm's predicted outcome not the actual
outcome. In other words, the emphasis is on the precision of prediction
rather than its recall: <br>
$\label{eq:condUseAcc}
P([)Y=y\mid \hat{Y}=y ,A = 0] = P([)Y=y\mid \hat{Y}=y,A = 1] \quad \forall{ y \in \{0,1\}}.$

**Predictive parity** {cite}`chouldechova2017fair` is a relaxation of
conditional use accuracy equality requiring only equal $PPV$ among
groups: $$\label{eq:predPar}
P([)Y=1 \mid \hat{Y} =1,A = 0] = P([)Y=1\mid \hat{Y} =1,A = 1]$$ Like
predictive equality, predictive parity is insensitive to false
negatives.

**Overall accuracy equality** {cite}`berk2018fairness` is achieved when
overall accuracy for both groups is the same. This implies that

$$\label{eq:accuracy}
\frac{TP+TN}{TP+FN+FP+TN}$$

is equal for both groups:

$$\label{eq:ovAcc}
P([)\hat{Y} = Y | A = 0] = P([)\hat{Y} = Y | A = 1]$$

**Treatment equality** {cite}`berk2018fairness` is achieved when the ratio of
FPs and FNs is the same for both protected and unprotected groups: <br>
$\label{eq:treatEq}
\frac{FN}{FP}$<sub>A=0</sub> $= \frac {FN}{FP}$<sub>A=1</sub>

**Total fairness** {cite}`berk2018fairness` holds when all aforementioned
fairness notions are satisfied simultaneously, that is, statistical
parity, equalized odds, conditional use accuracy equality (hence,
overall accuracy equality), and treatment equality. Total fairness is a
very strong notion which is very difficult to hold in practice.

**Balance** {cite}`kleinberg17` uses the score ($S$) from which the outcome
$Y$ is typically derived through thresholding. <br>
**Balance for positive
class** focuses on the applicants who constitute positive instances and
is satisfied if the average score $S$ received by those applicants is
the same for both groups: <br>
$\label{eq:balPosclass}
E[S \mid Y =1,A = 0)] = E[S \mid Y =1,A = 1].$ <br>
**Balance of negative
class** focuses instead on the negative class: <br>
$\label{eq:balNegclass}
E[S \mid Y =0,A = 0] = E[S \mid Y =0,A = 1].$

**Calibration** {cite}`chouldechova2017fair` holds if, for each predicted
probability score $S=s$, individuals in all groups have the same
probability to actually belong to the positive class: <br>
$\label{eq:calib}
P([)Y =1 \mid S =s,A = 0] = P([)Y =1 \mid S =s,A = 1] \quad \forall s \in [0,1].$

**Well-calibration** {cite}`kleinberg17` is a stronger variant of
calibration. It requires that (1) calibration is satisfied, (2) the
score is interpreted as the probability to truly belong to the positive
class, and (3) for each score $S=s$, the probability to truly belong to
the positive class is equal to that particular score: <br>
$\label{eq:wellCalib}
P([)Y =1 \mid S =s,A = 0] = P([)Y =1 \mid S =s,A = 1] = s  \quad  \forall \; {s \in [0,1]}.$

**Fairness through awareness** {cite}`dwork2012fairness` implies that similar
individuals should have similar predictions. Let $i$ and $j$ be two
individuals represented by their attributes values vectors $v_i$ and
$v_j$. Let $d(v_i,v_j)$ represent the similarity distance between
individuals $i$ and $j$. Let $M(v_i)$ represent the probability
distribution over the outcomes of the prediction. For example, if the
outcome is binary ($0$ or $1$), $M(v_i)$ might be $[0.2,0.8]$ which
means that for individual $i$, $P([)\hat{Y}=0]) = 0.2$ and
$P([)\hat{Y}=1] = 0.8$. Let $d_M$ be a distance metric between
probability distributions. Fairness through awareness is achieved iff,
for any pair of individuals $i$ and $j$: <br>
$d_M(M(v_i), M(v_j))  \leq d(v_i, v_j)$ <br>
In practice, fairness through
awareness assumes that the similarity metric is known for each pair of
individuals {cite}`kim2018fairness`. That is, a challenging aspect of this
approach is the difficulty to determine what is an appropriate metric
function to measure the similarity between two individuals. Typically,
this requires careful human intervention from professionals with domain
expertise {cite}`kusner2017counterfactual`.

**Process fairness**  {cite}`Grgic-HlacaZGW18` (or procedural fairness) can
be described as a set of subjective fairness notions that are centered
on the process that leads to outcomes. These notions are not focused on
the fairness of the outcomes, instead they quantify the fraction of
users that consider fair the use of a particular set of features. They
are subjective as they depend on user judgments which may be obtained by
subjective reasoning.

A natural approach to improve process fairness is to remove all
sensitive (protected or salient) features before training classifiers.
This simple approach connects process fairness to *fairness through
unawareness*. However, there is a trade-off to manage since dropping out
sensitive features may impact negatively classification
performance {cite}`zafar2017fairness`.

**Nonstatistical fairness metrics:** Recently, further metrics have been
proposed and that differ from the previous in that they do not fully
rely on statistical considerations, and take into account domain
knowledge, that is not directly observable from data, require expert
input, or reason about hypothetical situations. As they fall out of the
scope of this chapter, we will not further dwell into these and simply
mention a few to the interested reader: *total effect*
{cite}`pearl2009causality` (that is the "causal" version of statistical
parity and measures the effect of changing the value of an attribute,
taking into account a given causal graph), *effect of treatment of the
treated* {cite}`pearl2009causality` (that relies on counterfactuals with
respect to sensitive features and measures the difference between the
probabilities of instances and their counterfactuals), and
*counterfactual fairness* {cite}`kusner2017counterfactual` (which is a
fine-grained variant of the previous but with respect to the set all
features).

**Discussion:** As the above fairness metrics often conflict, and it is
not possible to be fair according to all of these definitions, it is a
challenge to choose the relevant metric to focus on. While still very
much an open research area, some suggestions on how one can deal with
conflicts between fairness metrics can be found in
{cite}`Loi2021,DBLP:journals/aiethics/LeeFS21`. Indeed, fairness metrics
frequently conflict with other metrics such as accuracy and privacy.
{cite}`kozodoi2022fairness` show that in a credit scoring case enforcing
fairness metrics can lead to significant drops in accuracy and, thus,
maximum profit. This is unavoidable: improvements on fairness often
result in lower accuracy, and research on the Pareto frontier for this
trade-off is now emerging {cite}`wei2020fairness,liang2021algorithmic`.
Similarly, there is a trade-off between fairness and privacy, as
fairness metrics typically require sensitive information in order to be
used. As a result, fairness affects privacy (and vice versa), for
example in facial recognition {cite}`xiang2022being` and medical applications
{cite}`chester2020balancing`.

Finally, there is a connection between *fairness* and {doc}`justice`, seen in
for example Rawls' work on Justice as Fairness {cite}`rawls2001justice`. And
indeed, a range of theories of (distributive) justice describe how
benefits and burdens should be distributed (cf. the entry on ). As such,
they can be seen as guiding the outcomes of algorithms even if they
describe what these distributions should be in society as a whole. Yet,
as {cite}`kuppler2021distributive` argue at length, there is little overlap
between theories of distributive justice and fairness metrics.
Non-comparative notions of justice are not captured by fairness metrics,
nor are notions such as Rawls' difference principle, on which the right
distribution is the one where the worst off have the highest absolute
level of benefits. Fairness metrics have focused more on
[discrimination](./discrimination.md) than on *justice*.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---

This entry was written by Resmi Ramachandranpillai, Fredrik Heintz, Stefan Buijsman, Miguel Couceiro, Guilherme Alves, Karima Makhlouf, and Sami Zhioua.

---

[^statistical]: $TP,FP,FN,$ and $TN$ stand for: true positives, false positives, false negatives, and true negatives, respectively.
[^parity]: Called explanatory features in {cite}`kamiran2013quantifying`.
