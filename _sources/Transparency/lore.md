# Local Rule-based Explanation

<!-- TODO: add resources or remove duplicate paragraph! -->

## In Brief

**Local Rule-based Explanation** aims to extract a rule that provides a local explaination for a certain instance of the model.

## More in details

Despite being useful, global explanations can be inaccurate because interpreting a whole model can be complex. On the other hand, even though the overall decision boundary is difficult to explain, locally, in the surrounding of a specific instance, it can be easier. Therefore, a local explanation rule can reveal the *factual* reasons for the decision taken by the black box of an AI system for a specific instance. The  <span style="font-variant:small-caps;">LORE</span> method is able to return a local rule-based explanation.  <span style="font-variant:small-caps;">LORE</span> builds a local decision tree in the neighborhood of the instance analyzed {cite}`guidotti2019factual_30` generated with a genetic procedure to account for both similarity and differences with the instance analyzed.
Then, it extracts from the tree a local rule revealing the reasons for the decision on the specific instance (see the green path in Figure {numref}`{number} <fig:counterfactual>`). For instance, the explanation of  <span style="font-variant:small-caps;">LORE</span> for the denied request of a loan from a customer with <br>"age=22, race=black, and income=800"<br> to a bank that uses an AI could be the factual rule <br>*if age ≤ 25 and race = black and income ≤ 900 then deny*.

<span style="font-variant:small-caps;">anchor</span> {cite}`ribeiro2018anchors_59` is another XAI approach for locally explaining black box models with decision rules called anchors. An *anchor* is a set of features with thresholds indicating the values which are fundamental for obtaining a certain decision of the AI. anchor efficiently explores the black box behavior by generating random instances exploiting a multi-armed bandit formulation.

```{figure} ./counterfactual.png
---
name: fig:counterfactual
width: 600px
align: center
---
Example of local factual and counter-factual explanation returned by <span style="font-variant:small-caps;">LORE</span> {cite}`Guidotti2021`.
```




## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi.

