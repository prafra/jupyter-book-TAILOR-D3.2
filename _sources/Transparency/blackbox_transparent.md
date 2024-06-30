# Black Box Explanation vs Explanation by Design

*Synonyms*: Post-hoc vs Ante-hoc Explanations, Explainable vs Interpretable Artificial Intelligence

## In brief
The difference between **Black Box Explanation** (or **Post-hoc Explanations**) and **Explanation by Design** (or **Ante-hoc Explanations**) regards the ability to know and exploit the behaviour of the AI model. With a black box explanation, we pair the black box model with an interpretation the black box decisions or model, while in the second case, the strategy is to rely, by design, on a transparent model.


## More in detail

The precise definitions of the core concepts in these fields -- such as transparency, interpretability and explainability -- remain elusive, in part because these notions tend to be domain-specific {cite}`sokol2021explainability`.

When we talk about **Black Box Explanation**, the strategy is to couple an AI with a black box model with an explanation method able to interpret the black box decisions. Usually, this situation is associated with systems that are *proprietary* -- hence inaccessible -- or *too complicated* to understand {cite}`rudin2019stop`.

In the case of **Explanation by Design** (aka **Transparency**), the idea is to substitute the obscure model with a transparent model in which the decision process is accessible by design, i.e., explainability is inserted into a model from the very beginning.
Interpretability presupposes an observer who appraises the intelligibility of the model in question.
This indicates that **interpretability** is not a binary property, but it is rather determined by the degree to which one can understand the system's operations, and thus resides on a *spectrum of opaqueness* {cite}`sokol2023reasonable`.

In view of this fluidity, the distinction between **ante-hoc interpretability** and **post-hoc explainability** techniques commonly made in the literature becomes blurred.
**Post-hoc explainability** offers insights into the behaviour of a predictive system by building an additional *explanatory model* that interfaces between it and human explainees (i.e., explanation recipients).
This is the only approach compatible with black-box systems, with which we can interact exclusively by manipulating their inputs and observing their outputs.
Such an operationalisation is nonetheless unsuitable for high stakes domains since the resulting explanations are not guaranteed to be reliable and truthful with respect to the underlying model {cite}`rudin2019stop`.
**Ante-hoc explainability**, in contrast, often refers to data-driven systems whose model form adheres (in practice) to application- and domain-specific constraints -- a *functional* definition -- which allows their designers to judge their trustworthiness and communicate how they operate to others {cite}`rudin2019stop`.
While the **post-hoc** moniker is, in general, used consistently across the literature, the same is not true for the *ante-hoc* label;
the *interpretability* and *explainability* terms are also often mixed and used interchangeably, adding to the confusion.
**Ante-hoc** sometimes refers to, among other things, transparent models that are self-explanatory, systems that are inherently interpretable, scenarios where the explanation and the prediction come from the same model, and situations where the model itself (or its part) constitutes an explanation, which are vague terms that are often incompatible with the *functional* definition of ante-hoc interpretability {cite}`sokol2023reasonable`.
Nonetheless, all of these notions presuppose an observer to whom the model is interpretable and who understands its functioning, which brings us back to the issue of accounting for an audience and its background.


Figure {numref}`{number} <post-hoc>` depicts this distinction. 

```{figure} ./post.png
---
name: post-hoc
width: 600px
align: center
---
(Top) Black box explanation pipeline. (Bottom) Explanation by design pipeline. {cite}`Guidotti2021`.
```

Starting from a dataset *X*, the **black box explanation** idea is to maintain the high performance of the obscure model *b* used by the AI, which is allowed to be trained normally, and to use an explanation method *f* to retrieve an explanation *e* by reasoning over *b* and *X*. In such a way, we aim to reach both accuracy and the ability to gain some {doc}`XAI_kinds`. This kind of approach is the one more addressed nowadays in the XAI research field {cite}`ribeiro2016should` {cite}`craven1996extracting` {cite}`lundberg2017unified`. 

On the other hand, the **explanation by design** consists of directly designing a comprehensible model *c* over the dataset *X*, which is interpretable by design and returns an explanation *e* besides the prediction *y*. Thus, the idea is to use this transparent model directly in the AI system {cite}`rudin2019stop` {cite}`rudin2019we`. 
In the literature, there are various models recognized to be interpretable. Examples include decision trees, decision rules, and linear models {cite}`freitas2014comprehensible`. These models are considered easily understandable and interpretable for humans. However, nearly all of them sacrifice performance in favor of interpretability. In addition, they cannot be applied effectively on data types such as images or text, but only on tabular, relational data, i.e., tables.

The *functional* definition of ante-hoc interpretability concerns the engineering aspects of information modelling and its adherence to domain-specific knowledge and constraints.
A *transparent* model may be *ante-hoc interpretable* to its engineers and domain experts with relevant technical knowledge, yet it may not engender understanding in explainees outside this milieu.
For example, a decision tree is transparent, but its interpretability presupposes its small size as well as technical understanding of its operation and familiarity with the underlying data domain;
one way to restore interpretability to a large tree is to process its structure to extract [decision rules](./rules.md), [exemplars](./prototypes.md) and [counterfactuals](./counterfactual.md).

<!--
:filter: docname in docnames
:filter: blackbox_transparent in docnames
:filter: {"blackbox_transparent"} & docnames
 -->

## Bibliography

```{bibliography} ./biblioXAI.bib
:style: unsrt
:filter: ./biblioXAI.bib in docnames
```

> This entry was partially readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi, Riccardo Guidotti, and Kacper Sokol.
