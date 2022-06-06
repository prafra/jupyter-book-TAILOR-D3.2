# Bias

## In brief

## More in Detail

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
evaluation of facts' {cite}`campolo2018ai`. In a more generalized version,
bias refers to an inclination towards or against a particular
individual, group, or sub-groups. The real world is often described as
biased in this sense, and since machine learning techniques simply
imitate observations of the world, it should come as no surprise that
the resulting systems also capture the same bias {cite}`hellstrom2020bias`.

Correctional Offender Management Profiling for Alternative Sanctions
(COMPAS) {cite}`brennan2018correctional` software for recidivism prediction,
used by the U.S department courts to decide whether to release a person
or keep them in prison, has discontinued its use after a careful
investigation conducted by the U.S officers as they concluded that the
software is biased against African-Americans. Also, the use of
predictive policing {cite}`alikhademi2021review` software has been ceased due
to the presence of racial biases. Amazon's employment hiring
{cite}`kodiyan2019overview` application realized that it is biased against
women. Content personalization and ad ranking systems have been accused
of filter bubbles and racial and gender profiling. Bidirectional Encoder
Representations from Transformers (BERT), has shown signs of gender
biases in google search as it is observed that the gender-neutral terms
(such as receptionist, doctor, nurse etc.) acquire stereotype and bias
due to the context in which they are present in the corpus
{cite}`nadeem2020stereoset`. In image domain, a latest gender classification
report from the National Institute for Standards and Technology (NIST)
pointed out that image classification algorithms performed worse for
female-labeled faces than male-labeled faces , exhibit gender biases
{cite}`grother2014face`. A bias can exist in different forms and shapes based
on the domain and context of application. The main reasons for the
origin of these biases are manifold. An outline of bias-inducing stages
in the ML pipeline is detailed in {cite}`DBLP:journals/csur/MehrabiMSLG21`.
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
population of study {cite}`tommasi2017deeper`. Nevertheless, in a broader
sense, it also occurs when the data does not contain features for
specific applications we are interested in. Additionally, human
interactions with the data produce bias against a specific group or
individual {cite}`tommasi2017deeper`. Various forms of dataset biases have
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
ideologies {cite}`DBLP:journals/corr/abs-1807-00553`. Another algorithmic
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

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---

This entry was written by Resmi Ramachandranpillai, Fredrik Heintz, Miguel Couceiro, and Gabriel Gonzalez-Castañé.


