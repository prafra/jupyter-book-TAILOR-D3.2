# Fairness, Equity, and Justice by Design --> Diversity, Non-Discrimination, and Fairness

## In brief

The term fairness is defined as the quality or state of being fair; or a
lack of favoritism towards one side. However, fairness can mean
different concepts to different peoples, different contexts, and
different disciplines {cite}`mulligan2019thing`. An unfair Artificial
Intelligence (AI) model produces results that are biased towards
particular individuals or groups. The most relevant case of bias is
discrimination against protected-by-law social groups. Equity requires
that people are treated according to their needs, which does not mean
all people are treated equally {cite}`10.1162/ajle_a_00019`. Justice is the
"fair and equitable treatment of all individuals under the law\"
{cite}`lehman2004west`.

## Abstract

We first provide motivations and background on fairness, equity and
justice in AI. This consists of warnings and legal obligations about
potential harms of unscrutinized AI tools, especially in socially
sensitive decision making. A taxonomy of fair-AI algorithms is then
presented, based on the step of the AI development process in which
fairness is checked/controlled for. Next, we summarize the guidelines
and draft standards for fair-AI, and the software frameworks supporting
the dimension. Finally, the main keywords of the dimension are
extensively detailed.

## Motivations and background [^readapt]

Increasingly sophisticated algorithms from AI and Machine Learning (ML)
support knowledge discovery from big data of human activity. They enable
the extraction of patterns and profiles of human behavior which are able
to make extremely accurate predictions. Decisions are then being partly
or fully delegated to such algorithms for a wide range of socially
sensitive tasks: personnel selection and wages, credit scoring, criminal
justice, assisted diagnosis in medicine, personalization in schooling,
sentiment analysis in texts and images, people monitoring through facial
recognition, news recommendation, community bulding in social networks,
dynamic pricing of services and products.

The benefits of algorithmic-based decision making cannot be neglected,
e.g., procedural regularity -- same procedure applied to each data
subject. However, automated decisions based on profiling or social
sorting may be biased {cite}`DBLP:journals/widm/NtoutsiFGINVRTP20` for
several reasons. Historical data may contain human (cognitive) bias and
discriminatory practices that are endemic, to which the algorithms
assign the status of general rules. Also, the usage of AI/ML models
reinforces such practices because data about model's decisions become
inputs in subsequent model construction (feedback loops). Algorithms may
wrongly interpret spurious correlations in data as causation, making
predictions based on ungrounded reasons. Moreover, algorithms pursue the
optimization of quality metrics, such as accuracy of predictions, that
favor precision over the majority of people against small groups.
Finally, the technical process of designing and deploying algorithms is
not yet mature and standardized. Rather, it is full of small and big
decisions (sometimes, trial and error steps) that may hide bias, such as
selecting non-representative data, performing overspecialization of the
models, ignoring socio-technical impacts, or using models in deployment
contexts they are not tested for. These risks are exacerbated by the
fact that the AI/ML models are complex for human understanding, or not
even intelligible, sometimes they are based on randomness or
time-dependent non-reproducible conditions {cite}`Kroll2017`.

Legal restrictions on automated decision-making are provided by the EU
General Data Protection Regulation, which states (<a href="https://gdpr-info.eu/art-22-gdpr/" target=_blank>Article 22</a>) "the right
not to be subject to a decision based solely on automated processing\".
Moreover, (<a href="https://gdpr-info.eu/recitals/no-71/" target=_blank>Recital 71</a>) "in order to ensure fair and transparent
processing in respect of the data subject [...] the controller should
use appropriate mathematical or statistical procedures [...] to
prevent, inter alia, discriminatory effects on natural persons".

Fair algorithms are designed with the purpose of preventing biased
decisions in algorithmic decision making. Quantitative definitions have
been introduced in philosophy, economics, and machine learning in the
last 50 years
{cite}`DBLP:conf/fat/HutchinsonM19,DBLP:conf/fat/Binns18,DBLP:journals/ker/RomeiR14`,
with more than 20 different definitions of fairness appeared thus far in
the computer science literature
{cite}`DBLP:journals/csur/MehrabiMSLG21,DBLP:journals/datamine/Zliobaite17`.
Four non-mutually exclusive strategies can be devised for
fairness-by-design of AI/ML models.

*Pre-processing approaches.* They consists of a controlled sanitization
of the data used to train an AI/ML model with respect to specific
biases. Pre-processing approaches allow for obtaining less biased data,
which can be used for training AI/ML models. An advantage of
pre-processing approaches is that they are independent of the AI/ML
model and algorithm at hand.

*In-processing approaches.* The second strategy is to modify the AI/ML
algorithm, by incorporating fairness criteria in model construction,
such as regularizing the optimization objective with a fairness measure.
There is a fast growing adoption of in-processing approaches in many
AI/ML problems other than in the original setting of classification,
including ranking, clustering, community detection, influence
maximization, distribution/allocation of goods, and models on
non-structured data such as natural language texts and images. An area
somehow in the middle between pre-processing and in-processing
approaches is fair representation learning, where the model inferred
from data is not used directly for decision making, but rather as
intermediate knowledge.

*Post-processing approaches.* This strategy consists of post-processing
an AI/ML model once it has been computed, so to identify and remove
unfair decision paths. This can be achieved also by involving human
experts in the exploration and interpretation of the model or of the
model's decisions. Post-processing approaches consist of altering the
model's internals, for instance by correcting the confidence of
classification rules, or the probabilities of Bayesian models.
Post-processing becomes necessary for tasks for which there is no
in-processing approach explicitly designed for the fairness requirement
at hand.

*Prediction-time approaches.* The last strategy assumes no change in the
construction of AI/ML models, but rather correcting their predictions at
run-time. Proposed approaches include promoting, demoting or rejecting
predictions close to the decision boundary, differentiating the decision
boundary itself over different social groups, or wrapping a fair
classifier on top of a black-box base classifier. Such approaches may be
applied to legacy software, including non-AI/ML algorithms, that cannot
be replaced by in-processing approaches or changed by post-processing
approaches.

## Standards and guidelines

Several initiatives have started to audit, standardize and certify
algorithmic fairness, such as the [ICO Draft on AI Auditing
Framework](https://ico.org.uk/about-the-ico/ico-and-stakeholder-consultations/ico-consultation-on-the-draft-ai-auditing-framework-guidance-for-organisations),
the draft [IEEE P7003™ Standard on Algorithmic Bias
Considerations](https://standards.ieee.org/project/7003.html), the [IEEE
Ethics Certification Program for Autonomous and Intelligent
Systems](https://standards.ieee.org/industry-connections/ecpais.html),
and the [ISO/IEC TR 24027:2021 Bias in AI systems and AI aided decision
making](https://www.iso.org/standard/77607.html) (see also the entry on
{doc}`./auditing`). Regarding the issue of equality data collection, the European Union
High Level Group on Non-discrimination, Equality and Diversity has set
up "[Guidelines on improving the collection and use of equality
data](https://ec.europa.eu/info/sites/default/files/en-guidelines-improving-collection-and-use-of-equality-data.pdf)\",
and the European Union Agency for Fundamental Rights (FRA) maintains <a href="https://fra.europa.eu/en/promising-practices-list" target=_blank>a
list</a> of promising practices for equality data collection.

Very few scientific works attempt at investigating the practical
applicability of fairness in AI
{cite}`DBLP:journals/sigkdd/MakhloufZP21,DBLP:conf/aies/BeutelCDQWLKBC19`.
This issue is challenging, and likely to require domain-specific
approaches {cite}`DBLP:journals/mima/LeeF21`. On the educational side,
however, there are hundreds of university courses on technology ethics
{cite}`DBLP:conf/sigcse/FieslerGB20`, many of which cover fairness in AI.

## Software frameworks supporting dimension

The landscape of software libraries and tools is very large. Existing
proposals cover almost every step of the data-friven AI development
process (data collection, data processing, model development, model
deployment, model monitoring), every type of AI models (classification,
regression, clustering, ranking, community detection, influence
maximization, distribution/allocation of goods), and every type of data
(tabular, text, images, videos). Reviews and critical discussions of
gaps for a few fairness toolkits can be found in
{cite}`lee2021landscape,DBLP:journals/corr/abs-2112-05700`.

## Main keywords

- {doc}`./auditing`: **Auditing AI** aims to identify and address possible risks and impacts while ensuring robust and trustworthy (see {doc}`../Accountability/L2.Accountability`).
- {doc}`./bias`: **Bias** refers to an inclination towards or against a particular individual, group, or sub-groups. AI models may inherit biases from training data or introduce new forms of bias.
- {doc}`./equity`: Forms of bias that count as discrimination against social groups or individuals should be avoided, both from legal and ethical perspectives. Discrimination can be direct or indirect, intentional or unintentional.
- {doc}`./fairness`: The term **fairness** is defined as the quality or state of being fair; or a lack of favoritism towards one side. The notions of fairness, and quantitative measures of them (fairness metrics), can be distinguished based on the focus on individuals, groups and sub-groups.
- {doc}`./fair_ML`: **Fair Machine Learning** models take into account the issues of bias and fairness. Approaches can be categorized as pre-processig, which transform the input data, as in-processing, which modify the learning algorithm, and post-processing, which alter models’ internals or their decisions.
- {doc}`./discrimination`: International and national laws prohibit **discriminating on some explicitly defined grounds**, such as race, sex, religion, etc. They can be considered in isolation, or interacting, giving rise to multiple discrimination and intersectional discrimination.
- {doc}`./justice`: **Justice** encompasses three different perspectives: (1) *fairness* understood as the fair treatment of people, (2) *rightness* as the quality of being fair or reasonable, and (3) a legal system, the scheme or system of law. Justice can be distinguished between *substantive* and *procedural*.
- {doc}`./segregation`: **Social segregation** refers to the separation of groups on the grounds of personal or cultural traits. Separation can be physical (e.g., in schools or neighborhoods) or virtual (e.g., in social networks). 


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Salvatore Ruggieri.

[^readapt]: This Section was readapted from {cite}`RuggieriFairness`.

