# Uncertainty

## In brief

**Uncertainty** is the lack of information to fully determine the value or characteristics of something. In the context of Artificial Intelligence, it is commonly divided into at least two types: (1) *epistemic uncertainty* which can be reduced by additional knowledge, and (2) *aleatoric uncertainty* which can not be reduced by other means. *Uncertainty* can originate from multiple sources in an Artificial Intelligence (AI) system. The identification of its source and understanding of its nature is crucial to reduce the impact when making informed decisions.

## More in detail

Artificial Intelligence (AI) solutions are commonly used to solve tasks that are too complex to define perfectly or which have high computational complexity to be solved with an exact solution. For this reason, most AI methods rely on simplifications, making assumptions about the potential set of solutions, some times incorporate imprecisions in their definition, and are based in heuristics, which add up uncertainties in their solutions. In order to capture those uncertainties, some AI methods provide the capability of incorporating uncertainty quantisation in the form of probabilities, possibilities, or variability, among others. This is of particular importance on critical applications and optimal decision making to minimise the impact of wrong decisions.
The design of an AI solution for a given problem potentially requires a long pipeline of tasks, each of which can incorporate some types of uncertainties that can add up; from the initial collection of data to the final model interpretation. Some of the possible sources of uncertainty that can be present in an AI solution are: uncertainty in the values of the collected data (e.g. imprecision of physical measurements, random noise, imperfect annotations), uncertainty on the population distributions (e.g. biases in the sampling process, dataset shift), uncertainty in the model predictions (e.g. non-calibrated class posterior probabilities {cite:p}`silva2023classifier`, expected variance of a regression model), uncertainty about the model parameters (e.g. the estimated weights of a linear regression).
A common and useful way to caracterize the different types of uncertainties is to accept that some uncertainties are intrinsic to the problem and can not be reduced. The two types are (1) epistemic uncertainty, which referest to uncertainty due to lack of knowledge and which can be reduced by plausible means. For example, in some cases the collection of additional examples, or the aclquisition of other features can reduce the uncertainty of new predictions {cite:p}`hullermeier2021aleatoric`. On the other hand, *aleatoric uncertainty* refers to uncertainty that is intrinsic and can not be reduced by realistic means. For example, by collecting additional tosses of a six sided dice we can better approximate its true probability of landing on six. However, it is almost impossible to predict with certainty which side will land (even if the dice is biased), as we would require perfect knowledge representation of the physics of the dice, the environment and the time and space interactions with the dice and the environment. We accept that there are some limitations of possible knowledge that escape from our capabilities and can not be reduced. The following figure illustrates another example of the two types of uncertainty.


```{figure} ./epistemic.png
---
name: fig:epistemic
width: 600px
align: center
---
Illustration of the difference between aleatoric (on the left) and epistemic uncertainty (on the right).
The example consists on two predictive events, each one with two possible outcomes.
Left: A fair coin that is tossed will have equal probability of landing on any side. Given that there is no additional information to determine its outcome, this is referred to as irreducible or aleatoric uncertainty.
Right: The word "vostojn" means heads or tails, with no additional knowledge the probability of each outcome should be equal. However, knowing that the word is from Esperanto, which is derived primarily from Romance languages, in particular Germanic languages, could remove some of the uncertainty. This type of uncertainty that is reducible by additional knowledge is referred as epistemic.
```

Several methods have been proposed to address and quantify uncertainty in AI. One of the first approaches to incorporate uncertainty in logic programming was the concept of fuzzy logic {cite:p}`zadeh1965fuzzy`, which allowed the representation of boolean logic with degrees of membership. Similarly, possibilistic logic {cite:p}`dubois2004,dubois2014possibilistic` allowed the definition of first-order classigcal logic with lower bounds of necessity and possibility. The concept of imprecise probabilities was suggested by {cite:t}`walley1991statistical` to quantify the uncertainty in the typical Bayesian setting, augmenting predicted class probabilities with upper and lowerbounds. The use of upper and lowerbounds has been used for cautious classification, allowing models to abstain from making a prediction in uncertain situations {cite:p}`ferri2004cautious`. Conformal predictions {cite:p}`vovk2005` is a frequentist approach based on statistical tests that calculates lower and upperbounds for each instance to belong to one class within a pre-specified probability. The concept of safe probability {cite:p}`grunwald2018safe` is another idea to quantify the uncertainty in distributions of probabilities for a prediction, which may differ from actual beliefs or even the ground truth.
There is no unique procedure to handle *uncertainty* in AI, as the sources and types are varied. A specific analysis and understanding of each case is necessary to reduce the impact that the uncertainty could have in an AI solution.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Miquel Perello Nieto and Peter Flach.
