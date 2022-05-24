# Single Tree Approximation

## In brief

The *Single Tree Appoximation* is an approach that aims at building a decision trees to approximate the behavior of a black box, typically a neural network.

## More in detail

Decision trees are the simplest example of [transparent techniques](./blackbox_transparent.md). Moreover, they can be built to provide [post-hoc explanations](./blackbox_transparent.md) of black-boxes.
One of the first approaches introduced to explain neural networks is <span style="font-variant:small-caps;">trepan</span> {cite}`Craven20`.
<span style="font-variant:small-caps;">trepan</span> is a [global explanation method](./global_local.md) that is able to model the whole logic of a
neural network working on tabular data with a **single decision tree** {cite}`kumar`. The decision tree
returned by <span style="font-variant:small-caps;">trepan</span> as an explanation is a *global transparent surrogate*. Indeed, every
path from the root of the tree to a leaf explains the reasons for the final decision that is
reported in the leaf itself. An example of a decision tree returned by <span style="font-variant:small-caps;">trepan</span> is illustrated
in Fig. {numref}`{number} <xai-tree>`.

```{figure} ./tree.png
---
name: xai-tree
width: 600px
align: center
---
Example of global tree-based explanation returned by <span style="font-variant:small-caps;">trepan</span> {cite}`Guidotti2021`.
```


This global explanation reveals that the black box first focuses on the
value of the feature *rest ECG*; Depending on its degree (abnormal, normal,
hypertrophy), tha black box takes different decisions depending on additional factors such as sex or
cholesterol. 
In particular, <span style="font-variant:small-caps;">trepan</span> queries the neural network to induce the decision
tree by maximizing the *gain ratio* {cite}`kumar` on the data with respect to the neural network's predictions.

A weakness of common decision trees like ID3 or C4.5 {cite}`quinlan1993c4_57` is
that the amount of data to find the splits near to the leaves is much lower than those
used initially. 
Thus, in order to retrieve how a neural network works in detail,
<span style="font-variant:small-caps;">trepan</span> adopts a synthetic generation of data that respects the path of each node before
performing the splitting such that the same amount of data is used for every split. In
addition, it allows flexibility by using *"m-of-n" rules* where only *m* conditions out
of *n* are required to be satisfied to classify a record. Therefore, <span style="font-variant:small-caps;">trepan</span> maximizes
the fidelity of the single tree explanation with respect to the black box decision. 

It is worth noting that, even though <span style="font-variant:small-caps;">trepan</span> is proposed to explain neural networks, in reality it
is [model-agnostic](./model_specific.md) because it does not exploit any internal characteristic of neural
networks to retrieve the explanation tree. Moreover, it does not place any requirements on either the architecture of the network or its training method. Thus, it can be theoretically employed to
provide explanations to every kind of classifier.

In {cite}`boz16` is presented an extension of <span style="font-variant:small-caps;">trepan</span> that aims to keep the tree explanation
simple and compact by introducing four splitting approaches in order to find the
most relevant features during the tree construction. 
In {cite}`johansson2009evolving_36`, genetic programming is used for building a single decision tree that approximates the behavior of a neural
network ensemble by considering additional genetic features obtained as combinations of the original data and the novel data annotated by the black box models. Both
methods described in {cite}`boz16`, {cite}`johansson2009evolving_36`, like <span style="font-variant:small-caps;">trepan</span>, return explanations in the form of a global decision
tree.

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi and Riccardo Guidotti.
