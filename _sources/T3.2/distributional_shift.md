# Distributional shift

*Synonyms*: Data shift.

## In brief

Once trained, most machine learning systems operate on static
models of the world that have been built from historical data which have
become fixed in the systems' parameters. This freezing of the model
before it is released 'into the wild' makes its accuracy and reliability
especially vulnerable to changes in the underlying distribution of data.
When the historical data that have crystallised into the trained model's
architecture cease to reflect the population concerned, the model's
mapping function will no longer be able to accurately and reliably
transform its inputs into its target output values. These systems can
quickly become prone to error in unexpected and harmful ways. In all
cases, the system and the operators must remain vigilant to the
potentially rapid concept drifts that may occur in the complex, dynamic,
and evolving environments in which your AI project will intervene.
Remaining aware of these transformations in the data is crucial for safe AI. [^def]


## More in detail

A common use case of machine learning in real world settings is to learn
a model from historical data and then deploy the model on future unseen
examples. When the data distribution for the future examples differs
from the historical data distribution (i.e., the joint distribution of
inputs and outputs differs between training and test o deployment
stages), machine learning techniques that depend precariously on the
i.i.d. assumption tend to fail. This phenomena is call distributional
shift and is a very common problem {cite}`quinonero2008dataset`. Note that a
particular case of distributional shift occurs when only the input
distribution changes (covariate shift) or there is a shift in the target
variable (prior probability shift).

The problem of distributional shift is of relevance not only to academic
researchers, but to the machine learning community at large.
Distributional shift is present in most practical applications, for
reasons ranging from the bias introduced by experimental design to the
irreproducibility of the testing conditions at training time. An example
is email spam filtering, which may fail to recognise spam that differs
in form from the spam the automatic filter has been built on
{cite}`ben2006analysis`, yet often the model being highly confident in its
erroneous classifications. This issue is especially important in
high-risk applications of machine learning, such as finance, medicine,
and autonomous vehicles, where a mistake may incur financial or
reputational loss, or possible loss of life. It is therefore important
to assess both a model's robustness to distribution shift and its
estimates of predictive uncertainty, which enable it to detect
distributional shifts {cite}`amodei2016,gal2016dropout`.

In general, the greater the degree of shift, the poorer the model's
performance is. The performance of learned models tend to drop
significantly even with a tiny amount of distribution shift between
training and test {cite}`recht2019imagenet,szegedy2013intriguing`, which
makes it challenging to reliably deploy machine learning in real world
applications. Although one can always increase training coverage by
adding more sources of data {cite}`devlin2018bert`, data augmentation
{cite}`madry2017towards,shorten2019survey`, or injecting structural bias
into models
{cite}`fukushima1982neocognitron,hochreiter1997long,vaswani2017attention`
for generalisation to any potential input for the learned model, it is
unrealistic to expect a learned model to predict accurately under any
form of distribution shift due to the combinatorial nature of real world
data and tasks.

On the other hand, adapting a model to a specific type of distribution
shift might be more approachable than adapting to any potential
distribution shift scenarios, under appropriate assumptions and with
appropriate modifications. By knowing where the model can predict well,
one can use the model to make conservative predictions or decisions, and
to guide future active data collection to covered shifted distributions.
Therefore, in addition to improving the generalisation performance of
models in general, methods that explicitly deal with the presence of
distribution shift are also desirable for machine learning to be used in
practice {cite}`wu2021learning`.

In terms of assessment, the robustness of learning models to
distributional shift is typically assessed via metrics of predictive
performance on a particular task: given two (or more) evaluation sets,
where one is considered matched to the training data and the other(s)
shifted, models which have a smaller degradation in performance on the
shifted data are considered more robust. The quality of uncertainty
estimates is often assessed via the ability to classify whether an
example came from the "in-domain" dataset or a shifted dataset using
measures of uncertainty.

For its part, concept shift (or concept drift) is different from
distributional shift in that it is not related to the input data or the
class distribution but instead is related to the relationship between
two or more dependent variables. An example may be the customer
purchasing behavior over time in a particular online shop. This
behaviour may be influenced by the strength of the economy, this being
not explicitly specified in the data. In this case, the concept of
interest (consumer behaviour) depends on some hidden context, not known
a priori, and not given explicitly in the form of predictive features,
making the learning task more complicated {cite}`tsymbal2004problem`. 
In this sense, concept shift can be categorised into 3 types: 
1) *sudden, abrupt or instantaneous concept shift* (e.g., following the previous example, the COVID-19 lockdowns significantly changed customer behaviour); 
2) *gradual concept shift* (e.g., customers are influenced by wider economic issues, unemployment rates or other trends) which can be divided further into moderate and slow drifts, depending on the rate of the changes {cite}`stanley2003learning`; 
3) *cyclic concept drifts*, where hidden contexts may be expected to recur due to cyclic phenomena, such as seasons of the year or may be associated with irregular phenomena, such as inflation rates or market mood {cite}`harries1998extracting`.

Concept drift may be present on supervised learning problems where
predictions are made and data is collected over time. These are
traditionally called online or incremental learning problems
{cite}`ditzler2012incremental`, given the change expected in the data over
time. For its part, the common methods for detecting concept drift in
machine learning generally include ongoing monitoring of the performance
(e.g., accuracy) and confidence scores of a learning model. If average
performance or confidence deteriorates over time, concept shift could be
occurring


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

[^def]: Definition taken from {cite}`david2019understanding` under Creative Commons Attribution License 4.0.
