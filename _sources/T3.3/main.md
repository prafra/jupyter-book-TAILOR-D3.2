---
title: 'Tailor T3.3 Handbook'
---

\maketitle
Read this first {#read-this-first .unnumbered .unnumbered}
===============

This is a working document for the Version 1 of the chapter on
"Fairness, Equity, and Justice by Design\" of the Tailor WP3 Handbook on
Trustworthy AI. This is a Tailor project deliverable with two versions:
Version 1 (M22) and Version 2 (M46). The Handbook is though to be
organized as an encyclopedia (see e.g., the [Encyclopedia of Machine
Learning and Data
Mining](https://link.springer.com/referencework/10.1007/978-1-4899-7687-1),
2017).

The Version 1 of the Handbook will be delivered as a jupiterbook and
this is the working draft link: [Tailor Handbook
Jupiterbook](https://prafra.github.io/jupyter-book-TAILOR-D3.2/TAILOR.html).

To facilitate the writing of the chapter on "Fairness, Equity, and
Justice by Design\", we will use this Overleaf project, instead of
directly working on the jupiterbook. After the chapter is finalized
here, the contents will be copied into the jupiterbook.\
**Deadline:** this chapter should be finished by end of April 2022.\
**Organization:** the structure of the chapter is as shown in the next
sections. In squared parenthesis, the name of the expected contributors.
If more than one contributor, they are expected to collaborate in
writing. For an example of another chapter see [T3.1 Explainable
AI](https://prafra.github.io/jupyter-book-TAILOR-D3.2/T3.1.html).\
**Contributors (add if needed):**

-   Alejandra Bringas Colmenarejo, University of Southampton,
    <A.Bringas-Colmenarejo@soton.ac.uk>

-   Stefan Buijsman, TUDelft, <S.N.R.Buijsman@tudelft.nl>

-   Miguel Couceiro, U.Lorraine, <miguel.couceiro@loria.fr>

-   Gabriel Gonzalez-Castañé, UCC, <gabriel.castane@insight-centre.org>

-   Resmi Ramachandran Pillai, Liu, <resmi.ramachandran.pillai@liu.se>

-   Salvatore Ruggieri, UNIPI, <salvatore.ruggieri@unipi.it>

-   Fredrik Heintz, Liu, <fredrik.heintz@liu.se>

\newpage
\tableofcontents
Fairness, Equity, and Justice by Design \[Salvatore first pass, then others\]
=============================================================================

In brief
--------

The term fairness is defined as the quality or state of being fair; or a
lack of favoritism towards one side. However, fairness can mean
different concepts to different peoples, different contexts, and
different disciplines [@mulligan2019thing]. An unfair Artificial
Intelligence (AI) model produces results that are biased towards
particular individuals or groups. The most relevant case of bias is
discrimination against protected-by-law social groups. Equity requires
that people are treated according to their needs, which does not mean
all people are treated equally [@10.1162/ajle_a_00019]. Justice is the
"fair and equitable treatment of all individuals under the law\"
[@lehman2004west].

Abstract
--------

We first provide motivations and background on fairness, equity and
justice in AI. This consists of warnings and legal obligations about
potential harms of unscrutinized AI tools, especially in socially
sensitive decision making. A taxonomy of fair-AI algorithms is the
presented, based on the step of the AI development process in which
fairness is checked/controlled for. Next, we summarize the guidelines
and draft standards for fair-AI, and the software frameworks supporting
the dimension. Finally, the main keywords of the dimension are
extensively detailed.

*Provide an abstract about the dimension*

Motivations and background {#sec:1.3}
--------------------------

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
sorting may be biased [@DBLP:journals/widm/NtoutsiFGINVRTP20] for
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
time-dependent non-reproducible conditions [@Kroll2017].

Legal restrictions on automated decision-making are provided by the EU
General Data Protection Regulation, which states (article 22) "the right
not to be subject to a decision based solely on automated processing\".
Moreover, (recital 71) "in order to ensure fair and transparent
processing in respect of the data subject \[\...\] the controller should
use appropriate mathematical or statistical procedures \[\...\] to
prevent, inter alia, discriminatory effects on natural persons\".

Fair algorithms are designed with the purpose of preventing biased
decisions in algorithmic decision making. Quantitative definitions have
been introduced in philosophy, economics, and machine learning in the
last 50 years
[@DBLP:conf/fat/HutchinsonM19; @DBLP:conf/fat/Binns18; @DBLP:journals/ker/RomeiR14],
with more than 20 different definitions of fairness appeared thus far in
the computer science literature
[@DBLP:journals/csur/MehrabiMSLG21; @DBLP:journals/datamine/Zliobaite17].
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

Standards and guidelines
------------------------

Several initiatives have started to audit, standardize and certify
algorithmic fairness, such as the [ICO Draft on AI Auditing
Framework](https://ico.org.uk/about-the-ico/ico-and-stakeholder-consultations/ico-consultation-on-the-draft-ai-auditing-framework-guidance-for-organisations),
the draft [IEEE P7003™ Standard on Algorithmic Bias
Considerations](https://standards.ieee.org/project/7003.html), the [IEEE
Ethics Certification Program for Autonomous and Intelligent
Systems](https://standards.ieee.org/industry-connections/ecpais.html),
and the [ISO/IEC TR 24027:2021 Bias in AI systems and AI aided decision
making](https://www.iso.org/standard/77607.html) (see also the entry on
). Regarding the issue of equality data collection, the European Union
High Level Group on Non-discrimination, Equality and Diversity has set
up "[Guidelines on improving the collection and use of equality
data](https://ec.europa.eu/info/sites/default/files/en-guidelines-improving-collection-and-use-of-equality-data.pdf)\",
and the European Union Agency for Fundamental Rights (FRA) maintains a
list[^1] of promising practices for equality data collection.

Very few scientific works attempt at investigating the practical
applicability of fairness in AI
[@DBLP:journals/sigkdd/MakhloufZP21; @DBLP:conf/aies/BeutelCDQWLKBC19].
This issue is challenging, and likely to require domain-specific
approaches [@DBLP:journals/mima/LeeF21]. On the educational side,
however, there are hundreds of university courses on technology ethics
[@DBLP:conf/sigcse/FieslerGB20], many of which cover fairness in AI.

Software frameworks supporting dimension
----------------------------------------

The landscape of software libraries and tools is very large. Existing
proposals cover almost every step of the data-friven AI development
process (data collection, data processing, model development, model
deployment, model monitoring), every type of AI models (classification,
regression, clustering, ranking, community detection, influence
maximization, distribution/allocation of goods), and every type of data
(tabular, text, images, videos). Reviews and critical discussions of
gaps for a few fairness toolkits can be found in
[@DBLP:journals/corr/abs-2112-05700; @lee2021landscape].

Main keywords
-------------

-   \hyperref[sec:auditing]{Auditing AI}
-   \hyperref[sec:bias]{Bias}
-   \hyperref[sec:diseq]{Discrimination \& equity}
-   \hyperref[fairness]{Fairness notions and metrics}
-   \hyperref[sec:fairml]{Fair Machine Learning}
-   \hyperref[sec:grounds]{Grounds of discrimination}
-   \hyperref[sec:justice]{Justice}
-   \hyperref[sec:segregation]{Segregation}

\
*Sub-section [1.3](#sec:1.3){reference-type="ref" reference="sec:1.3"}
was partly readapted from [@RuggieriFairness] by Salvatore Ruggieri*\
*Salvatore Ruggieri, Dipartimento di Informatica, University of Pisa,
Largo B. Pontecorvo 3, 56127 Pisa, Italy*\

\newpage
Index entries
=============

Auditing AI (final) {#sec:auditing}
-------------------

One of the measures to ensure that AI is used responsibly is the
initiation of auditing practices as they facilitate to verify if the
system works as intended.

Audits can be conducted either in-house or by external parties. The
former requires internal evaluation regarding whether systems are fit,
the human elements involved with the system are appropriate and
monitored, and the technical elements of the system are in perfect
condition and function correctly [@lovelace2020examining; @kazim2021ai].
The latter involves both regulators and third-parties verifying
compliance [@cobbe2021reviewable]. Interestingly, critical external
audits encompasses "disparate methods of journalist, technicians, and
social scientist who have examined the consequences of already-deployed
algorithmic systems and who have no formal relationship which the
institutions designing or integrating the audited systems\"
[@metcalf2021algorithmic p.8]. Well-known examples of these practices
such as the Propublica's examination of Northpoint recivism prediction
API [@larson2016we] or the Gender Shade Project [@buolamwini2017gender],
have played a crucial role pointing out harmful application of algorithm
systems to draw the attention of the society and require companies an
active role setting out governance and accountability mechanism.

As a result of these social demands, internal governance mechanisms
[@metcalf2021algorithmic] have been introduced from within the own
companies that design and deployed the algorithmic systems. The goal is
to propose technical and organisational procedures, among which are
detailed frameworks for algorithm auditing [@raji2020closing], able to
identify and address possible risk and impacts while ensuring robust and
trustful accountability. In essence, precise and well-documented audits
facilitate later scrutiny offering records on the reasons for the audit
to be initiated, the procedures that were followed as well as the
conclusions that were reached and, if carried out, the remedies or
measures that were adopted.

To this regard, more and more voices consider audits as indispensable
accountability mechanism to ensure the compliance of AI systems along
their life-cycle with the different applicable legislation, concerning
in particular privacy and data protection law [@casey2019rethinking].
Moreover, AI auditing can benefit from extensive literature in more
mature disciplines, such as audit studies in social sciences
[@DBLP:conf/eaamo/VecchioneLB21] and empirical economics
[@DBLP:journals/ker/RomeiR14]. Audits facilitate private entities the
provision of documentation when requested by public bodies, favouring a
systematic governance [@kaminski2020algorithmic] of AI systems through a
general transparency and enforcement regime. This joint effort between
public and private institutions would, in turn, result in collaborative
governance scheme [@kaminski2020algorithmic].

The upcoming EU Artificial Intelligence Act can be seen as a proposal to
establish a Europe-wide ecosystem for conducting AI auditing
[@mokander2021conformity] and in line with that idea more and more
research is done on auditing procedures for algorithms (for reviews see
[@koshiyama2021towards; @metaxa2021auditing]). For example,
[@raji2020closing] propose a framework for internal AI auditing which
includes both ethical aspects (a social impact assessment and ethical
risk analysis chart) and technical audits (such as adversarial testing
and a Failure Modes and Effect Analysis). Such audits are often
supported by technical documentation, such as the Datasheets for
Datasets proposal [@gebru2021datasheets] to maintain information on
datasets used to train AI systems. Such documentation can both help to
ensure that AI systems are deployed for tasks in line with the data they
were trained on and help to spot ethical risks stemming from the data
[@boyd2021datasheets], such as *biases* (cf. entry on ).

Ethical risks can also be the sole focus of AI audits, as in
ethics-based auditing (proposed for AI in [@mokander2021ethics]). While
still in development, several options are emerging where: "functionality
audits focus on the rationale behind decisions; code audits entail
reviewing the source code of an algorithm; and impact audits investigate
the types, severity, and prevalence of effects of an algorithm's
outputs.\" [@mokander2021EBA] For these audits in particular determining
what is measured can be a challenge, as it is difficult to define clear
metrics on which ethical aspects of AI systems can be evaluated.
*Fairness metrics* (cf. the entry on ) can certainly help here, but as
discussed there is a difficulty in the selection of the right metric and
even then there are limitations and trade-offs with other metrics. In
addition, for the integration of AI ethics in ESG (Environmental, Social
and Governance) reporting towards investors [@minkkinen2022investors]
such fairness metrics need not give sufficient insights into whether
algorithms are used responsibly at an organisational level. Existing ESG
criteria for organizational audits may help here, as well as work on
KPIs for Responsible Research and Innovation [@kwee2021responsible].
Despite all this work on metrics, it is however still an open question
to what extent ethics can be captured in numbers the way other aspects
of audits are, with some arguing that it is impossible to develop
benchmarks for how ethical an AI system is [@lacroix2022metaethical].
Instead, they argue, the focus should be on values and value trade-offs.

Z-Inspection, another auditing framework proposed based on the European
High Level Expert Group's Guidelines for Trustworthy AI
[@smuha2019ethics], takes values as its starting point [@zicari2021z].
As can also be seen in a case study for the framework involving an
algorithm that recognizes cardiac arrests in emergency calls
[@zicari2021assessing] this framework proceeds from a wide
identification of stakeholders and their values to the analysis of
(socio-)technical scenario's to reach an identification and
(potentially) resolution of ethical, technical and legal issues of an AI
system. Ultimately this still depends on the translation of values into
metrics, and so the main challenge of developing such metrics stands
regardless of one's auditing approach.

Standards represent a natural framework for the proceduralization of
audits. Certification by neutral third party states compliance to
certain standards as the result of auditing. Several draft proposals are
being prepared which include (at least implicitely) elements for
conducting audits, such as the following:

-   [ISO/IEC TR 24027:2021](https://www.iso.org/standard/77607.html) -
    Artificial intelligence (AI) --- Bias in AI systems and AI aided
    decision making.

-   [IEEE 7010-2020](https://standards.ieee.org/ieee/7010/7718/):
    Recommended Practice for Assessing the Impact of Autonomous and
    Intelligent Systems on Human Well-being.

-   [IEEE P2863](https://standards.ieee.org/ieee/2863/10142/) -
    Recommended Practice for Organizational Governance of Artificial
    Intelligence.

-   [IEEE
    CertifAIEd](https://engagestandards.ieee.org/ieeecertifaied.html) --
    Ontological Specification for Ethical Accountability

-   [IEEE
    CertifAIEd](https://engagestandards.ieee.org/ieeecertifaied.html) --
    Ontological Specification for Ethical Algorithmic Bias.

-   [NIST AI Risk Management
    Framework](https://www.nist.gov/itl/ai-risk-management-framework).

However, there is not yet a formal professional standard to guide
auditors of AI systems, yet some guidelines exist[^2].

\
*Alejandra Bringas Colmenarejo, School of Law, University of
Southampton, SO17 1BJ, UK*\
*Stefan Buijsman, Delft University of Technology, Jaffalaan 5, 2628 BX
Delft, NL*\
*Salvatore Ruggieri, Dipartimento di Informatica, University of Pisa,
Largo B. Pontecorvo 3, 56127 Pisa, Italy*\

\newpage
Bias (final) {#sec:bias}
------------

The success of Machine Learning (ML) systems in visual recognition,
online advertising, and recommendation systems have inspired its use in
applications such as employee hiring, legal systems, social systems, and
voice interfaces such as Alexa, Siri, and the like. Along with the
proliferation of these domains, a significant concern regarding the
trustworthiness of decisions has risen due to various biases (or
systematic errors) which may produce skewed results in the automated
decision making. The word 'bias' has an established normative
explanation in legal language, where it refers to 'judgement based on
preconceived notions or prejudices, as opposed to the impartial
evaluation of facts' [@campolo2018ai]. In a more generalized version,
bias refers to an inclination towards or against a particular
individual, group, or sub-groups. The real world is often described as
biased in this sense, and since machine learning techniques simply
imitate observations of the world, it should come as no surprise that
the resulting systems also capture the same bias [@hellstrom2020bias]

Correctional Offender Management Profiling for Alternative Sanctions
(COMPAS) [@brennan2018correctional] software for recidivism prediction,
used by the U.S department courts to decide whether to release a person
or keep them in prison, has discontinued its use after a careful
investigation conducted by the U.S officers as they concluded that the
software is biased against African-Americans. Also, the use of
predictive policing [@alikhademi2021review] software has been ceased due
to the presence of racial biases. Amazon's employment hiring
[@kodiyan2019overview]application realized that it is biased against
women. Content personalization and ad ranking systems have been accused
of filter bubbles and racial and gender profiling. Bidirectional Encoder
Representations from Transformers (BERT), has shown signs of gender
biases in google search as it is observed that the gender-neutral terms
(such as receptionist, doctor, nurse etc.) acquire stereotype and bias
due to the context in which they are present in the corpus
[@nadeem2020stereoset]. In image domain, a latest gender classification
report from the National Institute for Standards and Technology (NIST)
pointed out that image classification algorithms performed worse for
female-labeled faces than male-labeled faces , exhibit gender biases
[@grother2014face]. A bias can exist in different forms and shapes based
on the domain and context of application. The main reasons for the
origin of these biases are manifold. An outline of bias-inducing stages
in the ML pipeline is detailed in [@DBLP:journals/csur/MehrabiMSLG21].
Based on this study, bias definitions can be induced in data,
algorithms, and user interaction feedback loops.

ML systems are primarly based on data-driven approaches; therefore, the
outcome of ML-based decision-making processes depends on the input data
and the interpretation of that data. This decision-making process
involves numerous data analyses, such as uncovering patterns in the
data, finding correlations and trends, missing data imputations, and
data pre-processing. The performance of ML models depends on the data
used to train these models and the analysis performed on the training
data. It is noted that the primary source of biases is from the data and
its processing- involves what data was used for training, how it was
collected, and how the data was generated and pre-processed. A general
definition of dataset bias is that the data is not representative of the
population of study [@tommasi2017deeper]. Nevertheless, in a broader
sense, it also occurs when the data does not contain features for
specific applications we are interested in. Additionally, human
interactions with the data produce bias against a specific group or
individual [@tommasi2017deeper]. Various forms of dataset biases have
been identified in ML systems. Sample/selection biases emerge due to the
non-random sampling of groups and sub-groups. Exclusion bias arises at
the data pre-processing stage when valuable data are omitted thought to
be unnecessary. When the data used for training a model is different
from the data collected from the real world, for example, the training
data is collected using a fixed camera in image training, but the
production data is collected using different cameras, a measurement bias
can be occurred. Recall bias is a kind of measurement bias, and it
occurs when similar data are inconsistently labeled. Observer bias
occurs when we observe data based on what we want to see or expect to
see. Association biases are resultant of the spurious correlations
between features in the data.

Furthermore, algorithmic biases are systematic errors in computer
systems or models that cause certain privileges in outcomes concerning a
particular group or a person \[wiki\]. These biases can emerge in
various ways. Foremost among these are the design of the algorithm or
the way it uses the datasets to be coded, collected, selected, and
processed. Algorithmic errors may lead to biased outcomes even though
the data used for training are unbiased. A clear example is pre-existing
bias, arising as the result of underlying social and institutional
ideologies [@DBLP:journals/corr/abs-1807-00553]. Another algorithmic
bias is caused by technical biases manifested due the technical
limitations of code, its computational resources, its design, and the
constraints on the system. Technical biases are more frequent when we
rely more on the algorithm in other domains or unanticipated contexts.
Moreover, and related to the algorithm internals, correlation biases
materialise when algorithms assume conclusions from the correlations in
data attributes without knowing the specific purpose of those
attributes. Finally, another known bias -- in between the identified
ones -- are feedback loop biases. These arise when there is a recursion
error in the mechanism in which information is processed into the
data-model-experience pipeline.

The skewed outcomes from the biased data or (and) biased algorithms
affect user decisions which may result in a more biased data for future
ML systems. For example, consider a search engine which ranks queries.
The end users interact mostly with the top ranked results, rather than
going down the list, that can affect popularity and user interest of the
upcoming decisions, due to the biased interactions.

As a long term vision to create responsible ML systems, identifying and
mitigating biases throughout the ML development life cycle should be
given paramount importance. In a broader sense, the different ways the
bias could be mitigated are:

1.  Identify and define potential sources

2.  Set up guidelines and rules for data collection as well as a model
    use

3.  Define accurate representative data for training

4.  Properly document and share how the entire data collection process
    has been done

5.  Incorporate ways to measure and mitigate biases as part of the
    standard evaluation procedure.

\
*Resmi Ramachandranpillai, Department of Computer and Information
Sciences, Linkoping University, , 58 183, Sweden*\
*Fredrik Heintz, Department of Computer and Information Sciences,
Linkoping University, , 58 183, Sweden*\
*Miguel Couceiro, University of Lorraine, CNRS, Inria, LORIA, 54000
Nancy, France*\
*Gabriel Gonzalez-Castañé, School of Computer Science and Information
Technology, University College Cork, T12XF62 Cork, Ireland*

\newpage
Discrimination & equity (final) {#sec:diseq}
-------------------------------

Not all forms of *bias* (also known as *statistical discrimination*) are
problematic. Here we use the normative sense of *discrimination*, where
all forms of bias that count as discrimination are considered
problematic and should be avoided. This discrimination can be direct
(where a protected feature is intentionally used in the decision making
procedure). In such a case explainability tools such as feature
importance methods can help to detect whether a model's decisions are
based on the feature, in addition to the fairness metrics in the entry
on . Often, however, protected features are purposely not included among
the input variables, and so no direct discrimination will take place.
Instead, indirect discrimination (where there is direct discrimination
on features that strongly correlate with a protected feature, in such a
way that users with a socially salient value of the feature -- e.g.
women -- are worse off, cf. [@lippert2013born]) is the most common type
of discrimination in machine learning systems. For ways to detect these
cases of indirect discrimination, see the fairness metrics in the entry
on .

This type of indirect discrimination is often unintentional.
Philosophical accounts thus disagree about the degree of intentionality
that is required for bias to count as discrimination: mental state
accounts [@scanlon2009moral] require systematic animosity or preferences
towards a certain group. Such animosity need not be present among the
designers of the system, though it may be part of the reason for the
societal biases that filter through into the data. Other accounts
[@lippert2013born; @Loi2021] opt for weaker notions of intentionality,
where it is sufficient to enable the feature/group membership to play a
role in the decision making procedure. This clearly allows for the
(frequent) scenario where an algorithm has disparate impacts on groups
even when this was not the result of preferences/animosities of the
developers. Yet even then not all types of bias are considered
normatively problematic: a statistical bias that negatively impacts
smokers is not clearly a case of discrimination. So when is a bias a
case of discrimination?

An influential point of departure is the idea that biases should not be
on features outside of people's control
[@lippert2007nothing; @palmer2007insurance]. This might explain why the
paradigmatic cases of discrimination is when there is disparate
treatment based on gender, race, or ethnicity (cf. the entry ), as we
cannot choose these. However, there are more features beyond our
control, as illustrated by the 'other people's choice principle'
[@lippert2007nothing]: statistical patterns resulting from other
people's choices are not in our control either, and thus may lead to
discrimination. Consequently, charging higher premiums to a buyer of a
red car because on average drivers of red cars cause more accidents may
be seen as problematic. It violates the other people's choice principle,
as a buyer has no control over the driving of other car owners. On the
other hand, charging higher premiums to smokers does not violate this
principle, since smoking is a direct cause of higher health risks. In
practice, however, it is difficult to draw a clear border, as e.g.
socio-economic status impacts people's choices. Instead, some authors
[@binns2018s] suggest to consider notions of *justice* (cf. the entry on
) as guiding the distribution of benefits and burdens resulting from the
use of AI. For example, luck egalitarianism would consider it
discriminatory to uphold biases which reflect factors of luck. Still,
while the exact confines of normatively problematic discrimination are
difficult to define, it is clear that gender, race, etc. are protected
features and that such discrimination needs to be detected and tackled.

Following the egalitarian principles of [@Rawls; @Moulin04], some
authors address fairness from a multi-agent perspective
[@JongTV08; @Hao16] in automated decision making. Taking a welfare
perspective [@HeidariFGK18] propose a family of welfare based measures
that can be integrated together with other fairness and performance
constraints. Following the same tracks, [@JabbariJKMR17] considered the
temporal/sequential dimension and addressed fairness in the context of
Markov decision processes and reinforcement learning. Such
multi-objective and welfare approaches not only enforce human
intervention and social criteria to prevent unfair outcomes for some
users or stakeholders, but could be adapted to ensure equity and fair
trade-off between privilege and unprivileged groups.

\
*Stefan Buijsman, Delft University of Technology, Jaffalaan 5, 2628 BX
Delft, NL*\
*Miguel Couceiro, University of Lorraine, CNRS, Inria, LORIA, 54000
Nancy, France*

\newpage
Fairness notions and metrics (final) {#fairness}
------------------------------------

The term fairness is defined as the quality or state of being fair; or a
lack of favoritism towards one side. However, like bias, fairness can
mean different concepts to different peoples, different contexts, and
different disciplines. The definition of fairness in various disciplines
is detailed in [@mulligan2019thing]. An unfair model produces results
that are skewed towards particular individuals or groups. The primary
sources of this unfairness are the presence of biases. There are two
important categories of biases which play crucial role in fairness; (i)
technical bias and (ii) social bias. Technical biases can be traced back
to the sources , but social biases are very difficult to fix as these
are a matter of politics, perspectives, and shifts in prejudices and
preconceptions that can take years to change [@wachter2020bias]. Most of
the state-of-the-art techniques tackle technical errors, but it cannot
resolve the root causes of bias. Based on this observation, Sandra.et.al
[@wachter2020bias] proposed three responses concerning algorithmic bias
and resulting social inequality. The first is not an active choice as it
allows the system to get worse and do nothing to fix biases. Second,
incorporate techniques to fix technical errors and maintain a status quo
to ensure that the system do not make it worse. Much works in fairness
focused on this option, called 'bias preserving fairness', maintains a
status quo as a baseline, aligns with the formal equality of EU
non-discrimination law. Finally, 'bias transforming fairness', the third
response focuses on the substantive equality of EU non-discrimination
which can only be achieved by accounting for historical (social)
inequalities. As argued in [@wachter2020bias], users
(developers,deployers etc.) should give preference to 'bias
transforming' fairness metrics, when a fairness metric is used to make
substantive decisions about people in contexts where significant
disparity has been previously observed.

The notions of fairness fall under individuals, groups and sub-groups.
Individual fairness ensures that similar individuals should be treated
similarly. It accounts for the distance measures to evaluate the
similarity of individuals [@john2020verifying] [@biega2018equity]. On
the other hand, group fairness compares quantities at the group level
primarily identified by protective features such as gender, ethnicity
etc. etc.[@cheng2020group] [@conitzer2019group]. Sub-group fairness is
more rigid than group fairness as this ensures fairness concerning one
or more structured sub-groups defined by sensitive features,
interpolates between individual and group fairness notions
[@kearns2018preventing]. According to [@kleinberg17], it is impossible
to satisfy all of the above notions, leading to conflicts between
fairness definitions. Therefore, one suggestion could be to select
appropriate fairness criteria and use those based on the application and
deployment. Another concern has risen in [@liu2018delayed], temporal
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

**Statistical parity**[@dwork2012fairness] is one of the most commonly
accepted notions of fairness. It requires the prediction to be
statistically independent of the sensitive feature $(\hat{Y}  \perp A)$.
In other words, the predicted acceptance rates for both protected and
unprotected groups should be equal. Statistical parity implies that
$$\displaystyle \frac{TP+FP}{TP+FP+FN+TN}\footnote{$TP,FP,FN,$ and $TN$ stand for: true positives, false positives, false negatives, and true negatives, respectively.}$$
is equal for both groups. A classifier Ŷ satisfies statistical parity
if: $$\label{eq:sp}
P([)\hat{Y} \mid A = 0] = P([)\hat{Y} \mid A = 1].$$

**Conditional statistical parity** [@corbett2017algorithmic] is a
variant of statistical parity obtained by controlling on a set of
resolving features[^3]. The resolving features (we refer to them as $R$)
among $X$ are correlated with the sensitive feature $A$ and give some
factual information about the label at the same time leading to a
*legitimate* discrimination. Conditional statistical parity holds if:
$$\label{eq:csp}
P([)\hat{Y}=1 \mid R=r,A = 0] = P([)\hat{Y}=1 \mid R=r,A = 1] \quad \forall r \in range(R).$$

**Equalized odds** [@hardt2016equality] considers both the predicted and
the actual outcomes. The prediction is conditionally independent from
the protected feature, given the actual outcome
$(\hat{Y} \perp A \mid Y)$. In other words, equalized odds requires that
both sub-populations to have the same true positive rate
$TPR = \frac{TP}{TP+FN}$ and false positive rate
$FPR = \frac{FP}{FP+TN}$: $$\label{eq:eqOdds}
P([)\hat{Y} = 1 \mid Y=y,\; A=0] = P([)\hat{Y}=1 \mid Y= y,\; A=1]  \quad \forall{ y \in \{0,1\}}.$$

Because equalized odds requirement is rarely satisfied in practice, two
variants can be obtained by relaxing its equation. The first one is
called **equal opportunity** [@hardt2016equality] and is obtained by
requiring only TPR equality among groups: $$\label{eq:eqOpp}
P([)\hat{Y}=1 \mid Y=1,A = 0] = P([)\hat{Y}=1\mid Y=1,A = 1].$$ As $TPR$
does not take into consideration $FP$, equal opportunity is completely
insensitive to the number of false positives.

The second relaxed variant of equalized odds is called **predictive
equality** [@corbett2017algorithmic] which requires only the FPR to be
equal in both groups: $$\label{eq:predEq}
P([)\hat{Y}=1 \mid Y=0,A = 0] = P([)\hat{Y}=1\mid Y=0,A = 1].$$ Since
$FPR$ is independent from $FN$, predictive equality is completely
insensitive to false negatives.

**Conditional use accuracy equality** [@berk2018fairness] is achieved
when all population groups have equal positive predictive value
$PPV=\frac{TP}{TP+FP}$ and negative predictive value
$NPV=\frac{TN}{FN+TN}$. In other words, the probability of subjects with
positive predictive value to truly belong to the positive class and the
probability of subjects with negative predictive value to truly belong
to the negative class should be the same. By contrast to equalized odds,
one is conditioning on the algorithm's predicted outcome not the actual
outcome. In other words, the emphasis is on the precision of prediction
rather than its recall: $$\label{eq:condUseAcc}
P([)Y=y\mid \hat{Y}=y ,A = 0] = P([)Y=y\mid \hat{Y}=y,A = 1] \quad \forall{ y \in \{0,1\}}.$$

**Predictive parity** [@chouldechova2017fair] is a relaxation of
conditional use accuracy equality requiring only equal $PPV$ among
groups: $$\label{eq:predPar}
P([)Y=1 \mid \hat{Y} =1,A = 0] = P([)Y=1\mid \hat{Y} =1,A = 1]$$ Like
predictive equality, predictive parity is insensitive to false
negatives.

**Overall accuracy equality** [@berk2018fairness] is achieved when
overall accuracy for both groups is the same. This implies that

$$\label{eq:accuracy}
\frac{TP+TN}{TP+FN+FP+TN}$$

is equal for both groups:

$$\label{eq:ovAcc}
P([)\hat{Y} = Y | A = 0] = P([)\hat{Y} = Y | A = 1]$$

**Treatment equality** [@berk2018fairness] is achieved when the ratio of
FPs and FNs is the same for both protected and unprotected groups:
$$\label{eq:treatEq}
\frac{FN}{FP} \textsubscript{A=0} = \frac {FN}{FP} \textsubscript{A=1}$$

**Total fairness** [@berk2018fairness] holds when all aforementioned
fairness notions are satisfied simultaneously, that is, statistical
parity, equalized odds, conditional use accuracy equality (hence,
overall accuracy equality), and treatment equality. Total fairness is a
very strong notion which is very difficult to hold in practice.

**Balance** [@kleinberg17] uses the score ($S$) from which the outcome
$Y$ is typically derived through thresholding. **Balance for positive
class** focuses on the applicants who constitute positive instances and
is satisfied if the average score $S$ received by those applicants is
the same for both groups: $$\label{eq:balPosclass}
E[S \mid Y =1,A = 0)] = E[S \mid Y =1,A = 1].$$ **Balance of negative
class** focuses instead on the negative class: $$\label{eq:balNegclass}
E[S \mid Y =0,A = 0] = E[S \mid Y =0,A = 1].$$

**Calibration** [@chouldechova2017fair] holds if, for each predicted
probability score $S=s$, individuals in all groups have the same
probability to actually belong to the positive class: $$\label{eq:calib}
P([)Y =1 \mid S =s,A = 0] = P([)Y =1 \mid S =s,A = 1] \quad \forall s \in [0,1].$$

**Well-calibration** [@kleinberg17] is a stronger variant of
calibration. It requires that (1) calibration is satisfied, (2) the
score is interpreted as the probability to truly belong to the positive
class, and (3) for each score $S=s$, the probability to truly belong to
the positive class is equal to that particular score:
$$\label{eq:wellCalib}
P([)Y =1 \mid S =s,A = 0] = P([)Y =1 \mid S =s,A = 1] = s  \quad  \forall \; {s \in [0,1]}.$$

**Fairness through awareness** [@dwork2012fairness] implies that similar
individuals should have similar predictions. Let $i$ and $j$ be two
individuals represented by their attributes values vectors $v_i$ and
$v_j$. Let $d(v_i,v_j)$ represent the similarity distance between
individuals $i$ and $j$. Let $M(v_i)$ represent the probability
distribution over the outcomes of the prediction. For example, if the
outcome is binary ($0$ or $1$), $M(v_i)$ might be $[0.2,0.8]$ which
means that for individual $i$, $P([)\hat{Y}=0]) = 0.2$ and
$P([)\hat{Y}=1] = 0.8$. Let $d_M$ be a distance metric between
probability distributions. Fairness through awareness is achieved iff,
for any pair of individuals $i$ and $j$:
$$d_M(M(v_i), M(v_j))  \leq d(v_i, v_j)$$ In practice, fairness through
awareness assumes that the similarity metric is known for each pair of
individuals [@kim2018fairness]. That is, a challenging aspect of this
approach is the difficulty to determine what is an appropriate metric
function to measure the similarity between two individuals. Typically,
this requires careful human intervention from professionals with domain
expertise [@kusner2017counterfactual].

**Process fairness**  [@Grgic-HlacaZGW18] (or procedural fairness) can
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
performance [@zafar2017fairness].

**Nonstatistical fairness metrics:** Recently, further metrics have been
proposed and that differ from the previous in that they do not fully
rely on statistical considerations, and take into account domain
knowledge, that is not directly observable from data, require expert
input, or reason about hypothetical situations. As they fall out of the
scope of this chapter, we will not further dwell into these and simply
mention a few to the interested reader: *total effect*
[@pearl2009causality] (that is the "causal" version of statistical
parity and measures the effect of changing the value of an attribute,
taking into account a given causal graph), *effect of treatment of the
treated* [@pearl2009causality] (that relies on counterfactuals with
respect to sensitive features and measures the difference between the
probabilities of instances and their counterfactuals), and
*counterfactual fairness* [@kusner2017counterfactual] (which is a
fine-grained variant of the previous but with respect to the set all
features).

**Discussion:** As the above fairness metrics often conflict, and it is
not possible to be fair according to all of these definitions, it is a
challenge to choose the relevant metric to focus on. While still very
much an open research area, some suggestions on how one can deal with
conflicts between fairness metrics can be found in
[@Loi2021; @DBLP:journals/aiethics/LeeFS21]. Indeed, fairness metrics
frequently conflict with other metrics such as accuracy and privacy.
[@kozodoi2022fairness] show that in a credit scoring case enforcing
fairness metrics can lead to significant drops in accuracy and, thus,
maximum profit. This is unavoidable: improvements on fairness often
result in lower accuracy, and research on the Pareto frontier for this
trade-off is now emerging [@wei2020fairness; @liang2021algorithmic].
Similarly, there is a trade-off between fairness and privacy, as
fairness metrics typically require sensitive information in order to be
used. As a result, fairness affects privacy (and vice versa), for
example in facial recognition [@xiang2022being] and medical applications
[@chester2020balancing].

Finally, there is a connection between *fairness* and *justice*, seen in
for example Rawls' work on Justice as Fairness [@rawls2001justice]. And
indeed, a range of theories of (distributive) justice describe how
benefits and burdens should be distributed (cf. the entry on ). As such,
they can be seen as guiding the outcomes of algorithms even if they
describe what these distributions should be in society as a whole. Yet,
as [@kuppler2021distributive] argue at length, there is little overlap
between theories of distributive justice and fairness metrics.
Non-comparative notions of justice are not captured by fairness metrics,
nor are notions such as Rawls' difference principle, on which the right
distribution is the one where the worst off have the highest absolute
level of benefits. Fairness metrics have focused more on
*discrimination* than on *justice*.

\
*Resmi Ramachandranpillai, Department of Computer and Information
Sciences, Linkoping University, , 58 183, Sweden*\
*Fredrik Heintz, Department of Computer and Information Sciences,
Linkoping University, , 58 183, Sweden*\
*Stefan Buijsman, Delft University of Technology, Jaffalaan 5, 2628 BX
Delft, NL*\
*Miguel Couceiro & Guilherme Alves, University of Lorraine, CNRS, Inria,
LORIA, 54000 Nancy, France*\
*Karima Makhlouf & Sami Zhioua, Inria, Ecole Polytechnique, IPP, 91120,
Paris, France*\

\newpage
Fair Machine Learning (final) {#sec:fairml}
-----------------------------

Fairness can be promoted in three different ways in ML as surveyed in
[@caton2020fairness]. This survey provides a clear categorization of
methods under pre-process, in-process and post-process approaches.

Pre-process approaches are the most flexible ones that transforms the
data so that the underlying bias is removed. One advantage of using
pre-process techniques is that it is the most inspectable method, as it
is the earliest opportunity to mitigate biases and measure how it
affects the outcome compared to the other two approaches in fair machine
learning [@d2017conscientious]. Suppression or Fairness Through
Unawareness is a baseline method that accounts for removing the
sensitive features and proxy sensitive features from the dataset
[@gajane2017formalizing]. A recent study [@ruf2020active] proved that
removing sensitive information does not guarantee fair outcomes.
Massaging the dataset (relabeling) method can act in two ways; (1)
identify unfair outcomes and correct them by changing the label to what
ought to have happened. (2) Identify sensitive classes and relabel them
so that the outcome is fair. Reweighting approach has several positive
aspects compared to suppression and relabeling. It works by postulating
that a fair dataset would have no conditional dependence on the outcome
of any of the sensitive attributes. That means it corrects the past
unfair outcomes by giving more weightage to correct cases and less
weightage to incorrect cases. Learning fair representations approach
fairness fundamentally differently by aiming for a middle ground
between-group fairness and individual fairness [@zemel2013learning]. It
turns the pre-process problem into a combined optimization problem that
finds trade-offs between-group fairness, individual fairness, and
accuracy.

In-process approaches modify the learning algorithms to remove biases
during model training by either incorporating fairness into the
optimization equation or imposing a constraint as regularization
[@bellamy2018ai] [@berk2017convex]. The main categories of in-processing
approaches are adversarial debiasing and prejudice removal. The former
involves an adversary to predict the sensitive attributes from a
downstream task (classification or regression), and thus the model
learns a representation independent of sensitive features. Learning fair
representations can be done by adding noise to the predictive power
using the regulation. Adversarial reweighted learning
[@lahoti2020fairness] uses non-sensitive features and labels to measure
unfairness and co-train the adversarial reweighting approach to
improving learning. On the other hand, the prejudice remover approach
has various techniques to mitigate biases during training. Some of the
standard methods are:

1.  Heuristic-based: Use Roony rules [@kuhlman2019fare], which
    effectively rank problems.

2.  Algorithmic Changes: These can be made in every single step of
    calibration, such as input, output, and model structure
    [@fish2016confidence; @beutel2019fairness; @slack2020fairness; @beutel2019putting; @d2017conscientious; @wang2021fair; @dwork2018decoupled; @louizos2015variational; @mehrotra2021mitigating].

3.  Using pre-trained models: It involves combining available
    pre-trained models and transferring them to reduce bias
    [@madras2018learning]

4.  Counterfactual and Causal Reasoning: This considers a model to be
    group or individual fair if its prediction in the real world is
    similar to the counterfactual world, where individuals belong to a
    different protected group. Causal reasoning can be used to caution
    against those counterfactual explanations [@loftus2018causal]
    [@nabi2019learning]. A primary concern on the use and misuse of
    counterfactual fairness has been studied in [@kasirzadeh2021use].

Finally, post-process approaches are the most versatile approaches if
the model is already in the production stage and it does not require
retraining the model. Another advantage of using post-processing is that
the fairness (individual and group) of any downstream tasks can be
easily satisfied concerning the domain and application of the model
[@lohia2019bias]. Also, post-processing is agnostic to the input data,
which makes it easier to implement. However, post-processing procedures
may present weaker results when compare to pre-processing
ones [@kozodoi2022fairness; @pessach2022review].

**Assessment tools**: Tools can assist practitioners or organizations in
documenting the measures, providing guidance, helping formalize
processes, and empowering automated decisions. There are various types
of tools to identify and mitigate the biases. Out of which,
technical/quantitative tools and qualitative tools are primarily used in
real-world applications by engineers and data
scientists.Technical/quantitative tools focus on data or AI pipeline
through technical solutions. One major drawback is that it may miss
essential fairness considerations; for example, it cannot be employed to
mitigate bias in the COMPAS algorithm as the nuances could not be
adequately captured. It lacks methods to understand and mitigate biases
but perpetuates a misleading notion that \"Fair ML\" is not a complex
task to achieve. Some of the standard solutions in this category are:

1.  IBM's AI Fairness 360 Toolkit: It is a python toolkit through the
    lens of technical solutions under fairness metrics.

2.  Google's What-If Tool explores the model's performance on a dataset
    through hypothetical situations. It allows users to explore
    different definitions of fairness constraints under various feature
    intersections.

3.  Microsoft's fairlean.py: It is a python package consisting of
    mitigation algorithms and metrics for model assessment.

On the other hand, Quantitative techniques can delve into the nuances of
fairness. They can enable teams to explore the societal implications,
analyses fairness harms and tradeoffs, and propose plans to find the
potential sources of bias and ways to mitigate them. Two of the most
prominent qualitative techniques are:

1.  Co-designed AI fairness checklist (2020): This checklist is designed
    by a group of Microsoft researchers and academicians, 49 individuals
    from 12 technical organizations. It covers the items included in
    different stages of the AI pipeline, including envision, define,
    prototype, build, launch, and evolve, and is customizable according
    to the deployment.

2.  Fairness Analytic (2019): This analytic tool is developed by
    Mulligan et al. to promote fairness at the earlier stages of product
    development. It enables teams to understand biases from a specific
    application perspective to analyze and document their effects.

While these tools exist to analyze the potential harms, it is the
responsibility of users to understand the after-effects of which tools
they are using, and which types of biases can mitigate. A detailed
review of landscape and gaps in fairness tool kits is given in
[@lee2021landscape].

\
*Resmi Ramachandranpillai, Department of Computer and Information
Sciences, Linkoping University, , 58 183, Sweden*\
*Fredrik Heintz, Department of Computer and Information Sciences,
Linkoping University, , 58 183, Sweden*\
\
*Miguel Couceiro & Guilherme Alves, University of Lorraine, CNRS, Inria,
LORIA, 54000 Nancy, France*

\newpage
Grounds of discrimination (final) {#sec:grounds}
---------------------------------

The Universal Declaration of Human Rights prohibit discrimination in
several grounds[^4]; 1) race, 2) skin colour, 3) sex, 4) language, 5)
religion, 6) political or other opinion, 7) national or social origin,
8) property, or 9) birth [@assembly1948universal Article 2], although
the list is not exhaustive. By directly addressing these grounds, the
Declaration highlights the problematic of considering decisions or
regulations on them while leaves the door open to a more extensive view
by prohibiting as well discrimination based on *other grounds*. By doing
so, the Declaration implies that any difference in treatment or exercise
with respect to the rights encompassed in the Declaration would have
legal implications. Therefore, grounds of discrimination should not be
considered a closed and fixed list but an enumeration opened to debate
and reflection as the circumstances and context require. For example,
the African Charter on Human and People's Rights prohibits
discrimination in grounds of fortune, rather than property
[@africanunion] whereas the American Convention on Human Rights includes
economic status [@Americanconvention] and the Charter of Fundamental
Rights of the European Union (E.U.) adds the association with a national
minority [@charter2007]. ´

To this regard, *grounds of discrimination* encompass three different
motives on which decisions and policies should not be based (see also
the entry ); (1) grounds innate to the individual such as race, gender,
age, disability, (2) grounds intrinsic to the individual freedom and
autonomy that is political belief or religion, and (3) grounds highly
founded on stereotypes or stigma and which are usually irrelevant for
social, economic, or politic interactions, as sexual orientation or
ethnicity) [@gerards2013discrimination p.16]. The use of any of these
grounds is often perceived as a lack of impartiality influenced by
negative and prejudiced reasons and emotions towards certain members of
the society. Prohibiting discrimination on these grounds aims to ensure
that the distribution of social goods and services do not respond to
subjective and irrational feelings, whether that turns out to be an
advantage or a disadvantage for the individual or group concerned.

*Sex* refers to a person's biological status, categorized as male,
female, or intersex; *gender* refers to the attitudes and behaviors that
a culture associates with a person's sex, categorized as masculine,
feminine and transgender (gender identity different from sex assigned at
birth or non-binary); *sexual orientation* refers to the sex of those to
whom one is sexually and romantically attracted, categorized as
homosexual, heterosexual, and bisexual. See [@lgb2011] for a
psychological discussion of the differences between the terms,
[@Case1995] for a discussion with reference to the United States (U.S.)
anti-discrimination law, and [@fra2015protection] for a comparative
analysis on anti-discrimination European Law. A country profile report
on the legal rights of lesbian, gay, bisexual and transgender and (LGBT)
people is published yearly[^5] by Human Rights Watch. Human-Computer
Interaction research is also addressing the extent to which AI systems
"express gender and sexuality explicitly and through relation of
experience and emotions, mimicking the human language on which they are
trained\" [@DBLP:conf/cui/EdwardsCP21].

*Race* is a social construct to categorize people into groups. The term
is controversial, and with little consensus on its actual meaning.
[@Blank04 Chapter 2] summarizes biological and social concepts of race,
and discuss U.S. categorizations of races used for data collection,
e.g., in census data. *Ethnicity* refers to self-identifying groups
based on beliefs concerning shared culture, ancestry and history. The
distinction between *race* and *ethnic* grounds is, nonetheless, a
provocative issue primarily in Europe where after the Second War World
the notion of *race* become some sort of a *taboo*. By consequence, the
lacking of words, academic work, and policies addressing *race
(un)justice* has also resulted on a downplay of race grounds of
discrimination and the indistinct use of *ethnic origin* as *race* with
mislead intentions [@algorithmwatch].

Legislations and research studies have evolved with a different focus on
vulnerable groups, sometimes restricting themselves to specific
settings, including credit and insurance, sale, rental, and financing of
housing, personnel selection and wages, access to public accommodation,
and education. For instance, discrimination against Afro-Americans is
dealt with to a large extent by studies from the U.S., whilst
discrimination against Roma people has been mainly considered by E.U.
studies.

Although the aforementioned grounds for discrimination are typically
considered separately, the interaction of multiple forms of
discrimination has been receiving increasing attention
[@EUMultiple; @multiple44]. An elderly disabled woman for example, could
be discriminated against for being above a certain age, because she is a
woman, because she is disabled, or any combination of these. *Multiple*
discrimination comes into play when a person is discriminated against on
the basis of different characteristics *at different times*: each type
of discrimination works independently, according to distinct
experiences, and multiple discrimination refers to their cumulative
impact. When different grounds operate *at the same time*, then this is
known as *compound* or *intersectional* discrimination. Compound
discrimination (sometimes called *additive multiple discrimination*)
occurs when each ground *adds* to discrimination on other grounds, for
example migrant women experiencing both under-employment (such as
migrants compared to local residents) and lower pay (such as female
workers compared to male workers). Intersectional discrimination occurs
when concurrent acts of discrimination result in a specific and distinct
form of discrimination [@Fredman16]. For example, [@Makkonen02] reports
the case of Afro-American women stereotypes which when taken in
isolation cover neither women nor Afro-Americans.

Grounds of discrimination are key inputs in the design of fair AI
systems: fairness metrics, for instance, rely on comparing models'
performances across protected and unprotected groups. We refer to the
entries on and for details. Here, we concentrate on the problem of
faithfully representing grounds of discrimination in data, by
distinguishing the coding of human identity in raw data (*datafication*)
and the representativeness of grounds of discrimination in data
(*representation bias*).

For instance, if gender is coded with a binary feature (male/female),
then any further discrimination analysis is limited to contrasting only
such two groups, excluding non-binary people. There is then the need for
a more elaborate representation of human identity in raw data, e.g,
using ontologies for concept reasoning [@DBLP:journals/jamia/KronkD20].
Moreover, the categories used to encode grounds of discrimination may
embed forms of structural discrimination, which is hidden when features
are considered in isolation, but made apparent when connected with other
features in a knowledge graph [@DBLP:journals/corr/abs-2111-03687]. The
issue of *source criticism* [@Koch2020], which is central historical and
humanistic disciplines, is still in its infancy in the area of big data
and AI. Source criticism attains at the provenance, authenticity, and
completeness of data collected, especially in social media platforms.
For instance, the mechanisms of social software, such as the option
given to users to identify their gender as binary, result into
functional biases [@DBLP:journals/fdata/Olteanu00K19] of the data
collected. Beyond the complexity of datafication, the representiveness
of grounds of discrimination in datasets
[@DBLP:journals/corr/abs-2203-11852] also affects discrimination and
diversity analyses, and the fairness of AI models trained over those
datasets (see also the entry on ).

Most of the grounds of discrimination fall in the category of sensitive
personal data whose collection and processing is prohibited under
several privacy and data protection laws, unless certain exceptions
apply. For example, the grounds of race, ethnic origin, sexual
orientation, political stances, religious beliefs, and trade union
membership are considered special categories of personal data under the
European General Data Protection Regulation [@GDPR2016]. Likewise, the
California Privacy Rights Act (CPRA) will include as sensitive
attributes, among other, consumer's racial or ethnic origin, religious
or philosophical beliefs [@CPRA], while the Virginia Consumer Data
Protection Act (VCDPA) will add to those attributes, the ground of
mental or physical health, sexual orientation, or citizenship or
immigration status [@VCDPA]. From a regulatory perspective, the
restriction towards the collection and processing of sensitive personal
data intends to minimize the possibilities of algorithmic systems to
discriminate people based on intrinsic or innate attributes of the
individual. However, some criticism have arisen towards this perspective
as more voices defend the need to use sensitive attributes to ensure the
non-discriminatory nature of algorithmic models [@vzliobaite2016using].
The European Proposal for Regulating Artificial Intelligence (Artificial
Intelligence Act) seems to have reflect on this position as it will
introduce a exception allowing, to the extent that it is strictly
necessary for the purposes of ensuring bias monitoring, detection and
correction in relation to the high-risk AI systems, the processing of
special categories of data [@aiact].

Discrimination grounds in datasets can be be the output of an inference.
For instance, gender may be explicitly given (e.g., in a registration
form) with consent to a specific usage (e.g., personalization), or it
can be inferred using supervised learning
[@DBLP:journals/peerj-cs/SantamariaM18]. A growing number of AI
approaches can infer people's personality traits
[@DBLP:journals/taffco/VinciarelliM14], to be used e.g., for
personalization and recommendation purposes. To some extent, even in
cases where the system is blinded to protected attributes, inferences
can lead to discriminatory results as the system finds correlations
directly related to grounds of discriminatory. Inferences can,
therefore, be quite problematic because they can reinforce the
historical disadvantage and inequalities suffered by certain members of
the society [@xenidis2020tuning]. As the current legal protections rest
on the restricted access to data reveling the belonging of an individual
to a protected group or prohibition of use of such data to motivate a
decision, the access and use of such information indirectly creates a
threat to individuals' rights [@barocas2014data]. For this reason, the
correctness of such inferences can be crucial on attributed grounds of
discrimination and, consequently, on decisions and fairness analyses.
Despite inferences offer new possibilities for biased and invasive
decision-making, the legal status of inferred personal, both with
respect to data protection and anti-discrimination laws, is quite
debated [@Wachter2019].

\
*Alejandra Bringas Colmenarejo, School of Law, University of
Southampton, SO17 1BJ, UK*\
*Salvatore Ruggieri, Dipartimento di Informatica, University of Pisa,
Largo B. Pontecorvo 3, 56127 Pisa, Italy*\

\newpage
Justice (final) {#justice}
---------------

[\[sec:justice\]]{#sec:justice label="sec:justice"}

It is commonly accepted that, *justice* entails "the proper
administration of the law; the fair and equitable treatment of all
individuals under the law\" [@lehman2004west]. Therefore, *justice*
encompasses three different perspectives, (1) *fairness* understood as
the fair treatment of people, (2) *rightness* as the quality of being
fair or reasonable, and (3) a legal system, the scheme or system of law,
in which every person receives his/her/its due from the system,
including all rights, both natural and legal [@hill2002people].
Artificial Intelligence (AI) can be a tool for administering justice in
the legal system, or it can itself be subject to the requirements of
fairness and rightness when used for automated decision making (ADM). In
the former case, AI can be adopted at several levels of autonomy
[@Eliot2021Identifying], e.g., from no automation to superhuman
autonomous AI for legal reasoning. For a state of the art of the use of
Machine Learning (ML) in the criminal justice system (mainly in the
United States), see [@Berk2021]. Several books and newspapers
commentaries warn about the risks of using AI for justice administration
[@Forrest21]. In the latter case, the design of AI-based systems can
benefit from discussion and theories of justice in the legal and ethical
disciplines. However, the above conceptualization of *justice* has given
rise to an endless and ongoing debate regarding whether justice is an
inherent component of the law, not separate or distinct from it, or is
simply a moral judgment about law [@d1992connection]. In essence, the
debate considers whether justice understood as fairness and rightness is
independent from the law, or to what extent the *law* includes
considerations of justice and the legal system simply applies justice to
human conflicts. In conclusion, the concept of *justice* is as central
to legal theory as it is difficult to define.

Nevertheless, a range of different components or categories of justice
have been defined, both in the philosophical literature [@sep-justice]
and in the legal literature [@Susskind19]. These can be understood along
several distinctions, starting with one between *substantive* and
*procedural* justice. This is the difference between considering justice
in terms of the outcomes which have to meet certain standard in order to
be just [@rawls2020theory], versus considering justice in terms of a
procedure which meets certain standards (and possibly considering the
outcomes of any such procedure as being just regardless of the resulting
distributions [@nozick1974anarchy]). It is, however, common to consider
procedural justice partly in terms of the results (e.g., a trial
procedure is just if it -- at least -- mostly acquits the innocent and
punishes the guilty). As such, substantive justice is the main notion to
discuss here, although the use of AI in procedures also affects
questions of procedural justice.

Substantive justice in turn can be viewed in different ways. First,
there is a question of whether one focuses on *distributive* justice or
on *corrective* justice. Distributive justice deals with the
distribution of the benefits and burdens of social cooperation
[@rawls2020theory]. These can be *comparative*, such as the theory of
(strict) egalitarianism which requires that resources are distributed to
minimize overall inequality [@hirose2014egalitarianism] and other
versions of egalitarianism. For example, on Luck egalitarianism (and,
closely related, Equality of Opportunity) inequalities in the final
distribution may be allowed only in so far as they are not the result of
luck or a difference of opportunity
[@anderson1999point; @wolff2010fairness]. By far the most influential,
however, has been Rawls' view of Justice as Fairness, which combines a
requirement of equality of opportunity with the difference principle:
unequal distributions have to satisfy a min-max condition where "they
are to be to the greatest benefit of the least advantaged members of
society.\" [@rawls1993political p.6] Alternatively, distributive notions
of justice can be *non-comparative*. Sufficiency principles
[@brock2018sufficiency], requiring that everyone receives a minimally
sufficient amount of resources are a clear example of a distributive
justice notion that doesn't involve comparisons between individuals.
Desert-based principles [@moriarty2018desert], which hold that resources
should be allocated based on what individuals deserve can also be
non-comparative (if they specify absolute amounts based on what one
deserves, as opposed to a share of the total). Views thus differ on what
the right principles are for distributive justice. Furthermore, it is
interesting that most of these principles have only a limited overlap to
*fairness* in ADM [@kuppler2021distributive] (cf. the entry on ).

Where distributive justice focuses on the just distribution of goods,
corrective justice concerns the rectification of wrongs or the undoing
of transactions which can be either voluntary (contract) or involuntary
(when defrauded or a victim of misrepresentation)
[@ripstein2003division; @weinrib2012idea]. This differs from
distributive justice, as corrective justice first requires a wrong that
needs to be corrected, and the correction might violate the ideal
distribution of goods according to distributive justice principles. As
such, disagreements exist over the priority to be placed between these
two principles: is corrective justice merely a way to achieve
distributive justice or is corrective justice normatively prior?
[@walt2006eliminating] However this issue is settled, it is a matter of
fact that corrective justice is an important part of current legal
systems. Similarly, *retributive* justice [@sep-justice-retributive],
which focuses on the compensation of the victim of criminal behaviour
and the punishment of the lawbreaker, is crucial to our current systems.

In all these cases procedures are followed to make decisions on the
distribution of resources, the appropriate corrections and potential
punishments. *Procedural* justice relates to the normative conditions
that these procedures have to meet. As such, it encompasses principles
of legality, proportionality, effective remedy, fair trial, presumption
of innocence and right of defence
[@charter2007; @blader2003four; @meyerson2018procedural; @lee2019procedural].
Procedural justice is also affected by the use of AI, as this changes
procedures and so new standards have to be found for when a procedure
including AI is just. Such standards are also needed for transparency,
and the notion of procedural justice has been used to propose such a
standard by [@loi2021transparency], who argue that what matters to
determine the justness of an algorithm is the goals of the algorithm as
well as how effectively they are met. That is intended to allow an
evaluation of the justness of the procedure, and thus of the use of the
algorithm. For instance, [@Minhao2022] conducted experiments involving
laypeople, that showed a "fairness gap\" between human judges and AI
robot judges. Such a gap is reduced by enhancing the interpretability of
AI decisions.

Part of the question of what procedures are just is that of which
political procedures should be decided on. *Political* justice addresses
the foundational issues of political rights and responsibilities
embedded in constitutional theory and how individuals shall share the
control over the shape of the constitution[^6] [@sobel2015oxford].
*Social* justice, on the other hand, addresses how members should
compare under the basic structure of the society [@sobel2015oxford],
and, its "primary task is not so much to save the computational
infrastructure AI and ICTs rely on but rather to defend society\"
[@DBLP:conf/iconference/TachevaNA22]. This concern decisions about the
broad shape of society and thus cannot readily be solved with fair ML
tools. Yet algorithms can help in the implementation of these decisions.
As such, *justice* can be seen to differ from *fairness*: its scope is
often broader, and it is not restricted to questions of equality between
different groups to which an algorithm is applied. See e.g.,
[@Taylor2017] for a discussion of *data justice*, pertaining to "the way
people are made visible, represented and treated as a result of their
production of digital data\", and the literature on organizational
justice theory [@Bankins22; @DBLP:journals/hhci/RobertPMKA20] for the
notion of *interactional justice* pertaining to how workers are treated
with respect and dignity (*interpersonal justice*) and how they are
provided with explanations of business process and outcomes
(*informational justice*). Still, the design of AI systems intersects
with all of the notions of justice discussed here.

The increased use of AI and ADM reflects a tendency to *solutionism*
[@Morozov13], where technical solutions are offered to solve all social
and economic problems [@zavrvsnik2021algorithmic]. However, unfair,
discriminatory, and unjustified decisions affecting different aspects of
individuals' economy and private life has encouraged a critical
reflection on questions regarding "what, then, do we talk about when we
talk about governing algorithms?\" [@barocas2013]. Likewise, the
proposed *algorithmic justice* [@marjanovic2021theorising] strives to
address these unintentional effects provoked by the use of ADM for the
allocation of welfare services. This novel conception of justice,
founded on Nancy Fraser's *abnormal justice theory*, defends "the need
to expand our collective understanding of justice, beyond issues of
equal access to, and equal distribution of justice\"
\[[@fraser2008abnormal; @fraser2010injustice] as referred in
[@marjanovic2021theorising p.2]\] in order to recognise, debate,
diagnose and address harmful effects of ADM in the allocation of
transformative services [@marjanovic2021theorising]. That being the
case, (un)just ADM are more and more scrutinised under the lens of
*procedural justice* as several studies
[@lind1988social; @colquitt2015measuring; @bussone2015role] "suggest
that people do not only care about whether the outcome of a decision
benefits them, but also whether it meets standards of justice\"
[@binns2018s p.1]. To this regard, AI's *explainability and
transparency* would be crucial to justify and explain the algorithmic
decisions and decision-making process and therefore ensure the
accountability intelligibility of the decisions, and, by extension, of
the process (a principle known as *open justice* when referring to the
judicial system [@Pah2022]).

\
*Alejandra Bringas Colmenarejo, School of Law, University of
Southampton, SO17 1BJ, UK*\
*Stefan Buijsman, Delft University of Technology, Jaffalaan 5, 2628 BX
Delft, NL*\
*Salvatore Ruggieri, Dipartimento di Informatica, University of Pisa,
Largo B. Pontecorvo 3, 56127 Pisa, Italy*\

Segregation (final) {#sec:segregation}
-------------------

*Social segregation* refers to the "*separation of socially defined
groups*" [@massey2016segregation]. People are partitioned into two or
more groups on the grounds of personal or cultural traits that can
foster discrimination, such as gender, age, ethnicity, income, skin
color, language, religion, political opinion, membership of a national
minority, etc. (see entry on ). Contact, communication, or interaction
among groups are limited by their physical, working or socio-economic
distance. Such a separation is observed when dissecting the society into
organizational units (neighborhoods, schools, job types).

\centering
![Racial spatial segregation in New York City, based on Census 2000 data
[@efischer]. One dot for each 500 residents. Red dots are Whites, blue
dots are Blacks, green dots are Asian, orange dots are Hispanic, and
yellow dots are other races.
[\[fig:segregationMap\]]{#fig:segregationMap
label="fig:segregationMap"}](fig/segregationMap.pdf){width="0.65\linewidth"}

Early studies on residential segregation trace back to 1930's
[@denton1988residential]. In this context, social groups are set apart
in neighborhoods where they live in, in schools they attend to, or in
companies they work at. As sharply pointed out in
Figure [\[fig:segregationMap\]](#fig:segregationMap){reference-type="ref"
reference="fig:segregationMap"}, racial segregation (a.k.a. residential
segregation on the grounds of race) very often emerges in cities
characterized by ethnic diversity. Schelling's segregation model
[@Schelling1971; @Clark1991] shows that there is a natural tendency to
spatial segregation, as a collective phenomenon, even if each individual
is relatively tolerant -- in his famous abstract simulation model, Nobel
laureate Schelling assumed that a person changes residence only if less
than 30% of the neighbors are of his/her own race.

[@Massey2009] argued that segregation is shifting from ancient forms on
the grounds of racial, ethnic and gender traits to modern socio-economic
and cultural segregation on the basis of income, job position, and
political-religious opinions. An earlier comparison of ideological
segregation of the American electorate online and offline is offered in
[@gentzkow2010ideological]. The paper found that segregation in news
consumption is higher online than offline, but significantly lower than
the segregation of face-to-face interactions with neighbors, co-workers,
or family members. More recently, it has been warned that the filter
bubble generated by personalization of online social networks may foster
segregation [@flaxman2013ideological], opinion
polarization [@maes2015will], and lack of consensus between different
social groups. Segregation in social network has been investigated in
[@DBLP:journals/jiis/BaroniR18], with experiments on segregation on the
grounds of sex and age for directors in the boards of the companies.
Other works have focused on religious social networks
[@DBLP:journals/epjds/HuZZ19],

A segregation index provides a quantitative measure of the degree of
segregation of social groups (e.g., Blacks, Whites, Hispanics, etc.)
distributed among units of social organization (e.g., schools,
neighborhoods, jobs, etc.). Several indexes have been proposed in the
literature. The surveys [@duncan1955methodological; @JamesTauber85]
represent the earliest attempts to categorize them. Afterward,
[@massey1988dimensions] provided a shared classification with reference
to five key dimensions: evenness, exposure, concentration,
centralization, and clustering. Finally,
[@DBLP:journals/socnet/BojanowskiC14] adapts segregation measure to
graphs representing social networks. In this entry, we will consider
basic evenness and exposure indexes. Other three classes of indexes are
specifically concerned with spatial notions of segregation.
Concentration indexes measure the relative amount of physical space
occupied by social groups in an urban area. Centralization indexes
measure the degree to which a group is spatially located near the center
of an urban area. Clustering indexes measure the degree to which group
members live disproportionately in contiguous areas.

We restrict here to consider binary indexes, which assume a partitioning
of the population into two groups, say majority and minority (but could
be men/women, native/immigrant, White/NonWhite, etc.). Let $T$ be size
of the total population, $0 < M < T$ be the size of the minority group,
and $P = M/T$ be the overall fraction of the minority group. Assume that
there are $n$ organizational units (or simply, units), and that for
$i \in [1, n]$, $t_i$ is the size of the population in unit $i$, $m_i$
is the size of the minority group in unit $i$, and $p_i = m_i/t_i$ is
the fraction of the minority population in unit $i$.

*Evenness indexes.* Evenness indexes measure the difference in the
distributions of social groups among organizational units. The
*dissimilarity index* $D$ is the weighted mean absolute deviation of
every unit's minority proportion from the global minority proportion:
$$D = \frac{1}{2 \cdot P \cdot (1-P)} \sum_{i=1}^n \frac{t_i}{T}
\cdot | p_i - P | \label{equ:dissimilarity}$$ The normalization factor
$2 \cdot P \cdot (1-P)$ is to obtain an index in the range $[0, 1]$.
Since $D$ measures dispersion of minorities over the units, higher
values of the index mean higher segregation. Dissimilarity is minimum
when for all $i \in [1, n]$, $p_i = P$, namely the distribution of the
minority group is uniform over units. It is maximum when for all
$i \in [1, n]$, either $p_i = 1$ or $p_i = 0$, namely every unit
includes members of only one group (complete segregation).

The second widely adopted index is the *information index*, also known
as the *Theil index* in social sciences [@Mora2011] and normalized
mutual information in machine learning [@mitchell1997]. Let the
population entropy be $E = -
P \cdot \log{P}-(1-P) \cdot \log{(1-P)}$, and the entropy of unit $i$ be
$E_i = - p_i \cdot \log{p_i}-(1-p_i) \cdot \log{(1-p_i)}$. The
information index is the weighted mean fractional deviation of every
unit's entropy from the population entropy:
$$H = \sum_{i=1}^n \frac{t_i}{T} \cdot \frac{(E-E_i)}{E}$$ Information
index ranges in $[0, 1]$. Since it denotes a relative reduction in
uncertainty in the distribution of groups after considering units,
higher values mean higher segregation of groups over the units.
Information index reaches the minimum when all the units respect the
global entropy (full integration), and the maximum when every unit
contains only one group (complete segregation).

The third evenness measure is the *Gini index*, defined as the mean
absolute difference between minority proportions weighted across all
pairs of units, and normalized to the maximum weighted mean difference.
In formula: $$\label{eq:Gini}
G = \frac{1}{2 \cdot T^2 \cdot P \cdot (1-P)} \cdot \sum_{i=1}^n
\sum_{j=1}^n t_i \cdot t_j \cdot |p_i - p_j|$$ Here
$\sum_{i=1}^n \sum_{j=1}^n t_i \cdot t_j \cdot |p_i - p_j|$ is the
weighted mean absolute difference. The normalization factor is obtained
by maximizing such a value. The definition of the Gini index stems from
econometrics, where it is used as a measure of the inequality of income
distribution [@gastwirth1971general]. The Gini index ranges in $[0, 1]$
with higher values denoting higher segregation. The maximum and minimum
values are reached in the same cases of the dissimilarity index.

*Exposure indexes.* Exposure indexes measure the degree of potential
contact, or possibility of interaction, between members of social
groups. The most used measure of exposure is the *isolation index*
[@bell1954probability], defined as the likelihood that a member of the
minority group is exposed to another member of the same group in a unit.
For a unit $i$, this can be estimated as the product of the likelihood
that a member of the minority group is in the unit ($m_i/M$) by the
likelihood that she is exposed to another minority member in the unit
($m_i/t_i$, or $p_i$) -- assuming that the two events are independent.
In formula: $$I = \frac{1}{M} \cdot \sum_{i=1}^n m_i \cdot p_i$$

The right hand-side formula can be read as the minority-weighted average
of minority proportions in units. The isolation index ranges over
$[P, 1]$, with higher values denoting higher segregation. The minimum
value is reached when for $i \in [1, n]$, $p_i = P$, namely the
distribution of the minority group is uniform over the units. The
maximum value is reached when there is only one $k \in [1, n]$ such that
$m_k = t_k = M$, namely there is a unit containing all minority members
and no majority member.

A dual measure is the *interaction index*, which is the likelihood that
a member of the minority group is exposed to a member of the majority
group in a unit. By reasoning as above, this leads to the formula:
$$\mathit{Int} = \frac{1}{M} \cdot \sum_{i=1}^n m_i \cdot (1-p_i)$$ It
clearly holds that $I + \mathit{Int} = 1$. Hence, lower values denote
higher segregation. A more general definition of interaction index
occurs when more than two groups are considered in the analysis, so that
the exposure of the minority group to one of the other groups is worth
to be considered [@massey1988dimensions].

The key problem of assessing social segregation has been investigated by
hypothesis testing, i.e., by formulating one or more possible contexts
of segregation against a certain social group, and then in empirically
testing such hypotheses. Such an approach is currently supported by
statistical tools, such as the R packages *OasisR*[^7] and *seg*[^8]
[@seg2014], or by GIS tools such as the *Geo-Segregation Analyzer*[^9]
[@geosa2014]. A tool for multidimensional exploration of segregation
index has been proposed[^10] in [@DBLP:conf/edbt/0001R19].

\
*This entry was readapted from [@DBLP:journals/jiis/BaroniR18] by
Salvatore Ruggieri*

[^1]: <https://fra.europa.eu/en/promising-practices-list>

[^2]: <https://ec.europa.eu/futurium/en/system/files/ged/auditing-artificial-intelligence.pdf>

[^3]: Called explanatory features in [@kamiran2013quantifying].

[^4]: Protected group, protected grounds and prohibited grounds are also
    used as synonymous of grounds of discrimination.

[^5]: For 2021, see
    <https://www.hrw.org/video-photos/interactive/2021/04/23/country-profiles-sexual-orientation-and-gender-identity>

[^6]: See
    <https://www.europeansocialsurvey.org/data/themes.html?t=justfair>
    for a survey on perceptions of political justice in Europe.

[^7]: [cran.r-project.org/package=OasisR](https://cran.r-project.org/package=OasisR)

[^8]: [cran.r-project.org/package=seg](https://cran.r-project.org/package=seg)

[^9]: [geoseganalyzer.ucs.inrs.ca](http://geoseganalyzer.ucs.inrs.ca)

[^10]: [github.com/ruggieris/SCube](https://github.com/ruggieris/SCube)
