# Rules List and Rules Set

<!-- TODO: add resources or remove duplicate paragraph! -->

## In Brief

A **decision rule** is generally formed by a set of conditions and by a consequent, e.g., *if conditions, then consequent*.

## More in details

Given a record, a decision rule assigns to the record the outcome specified in the consequent if the conditions are verified {cite}`agrawal2`. The most common rules are *if-then rules* that take into consideration rules with clauses in conjunction. On the other hand, for *m-of-n rules* given a set of *n* conditions, if *m* of them are verified, then the consequence of the rule is applied {cite}`murphy1991id2_51`. When a set of rules is used, then there are different strategies to select the outcome. 

For *list of rules* the order of the list is considered and the model returns the outcome of the first rule that verifies the conditions {cite}`yin2003cpar_76`. For instance, *falling rule lists* are if-then rules ordered with respect to the probability of a specific outcome {cite}`wang2015falling_75`. On the other hand, *decision sets* are unordered lists of rules. Basically each rule is an independent classifier that can assign its outcome without regard for any other rules {cite}`lakkaraju2016interpretable_39`. Voting strategies are used to select the final outcome.

List of rules and set of rules are adopted as explanation both from explanation methods but also from transparent classifiers. In both cases the reference context is tabular data. In {cite}`augasta_8` the explanation method <span style="font-variant:small-caps;">rxren</span> unveil with rules list the logic behind a trained neural network. First, <span style="font-variant:small-caps;">rxren</span> prunes the insignificant input neurons and identifies the data range necessary to classify the given test instance with a specific class. Second, <span style="font-variant:small-caps;">rxren</span> generates the classification rules for each class label exploiting the data ranges previously identified, and improve the initial list of rules by a process that prunes and updates the rules. Figure {numref}`{number} <fig:rules_rxren>` shows an example of rules returned by <span style="font-variant:small-caps;">rxren</span>. A survey on techniques extracting rules from neural networks is {cite}`Andrews4`. All the approaches in {cite}`Andrews4`, including <span style="font-variant:small-caps;">rxren</span> are model-specific explainers.


As previously mentioned, an alternative line of research to black box explanation is the design of transparent models for the AI systems. The <span style="font-variant:small-caps;">corels</span> method {cite}`angelino_5` is a technique for building rule lists for discretized tabular datasets. <span style="font-variant:small-caps;">corels</span> provides an optimal and certifiable solution in terms of rule lists. An example of rules list returned by <span style="font-variant:small-caps;">corels</span> is reported in Figure {numref}`{number} <fig:rules_corels>`. The rules are read one after the other, and the AI would take the decision of the first rule for which the conditions are verified. Decision sets are built by the method presented in {cite}`lakkaraju2016interpretable_39`. The if-then rules extracted for each set are accurate, non-overlapping, and independent. Since each rule is independently applicable, decision sets are simple, succinct, and easily to be interpreted. A decision set is extracted by jointly maximizing the interpretability and predictive accuracy by means of a two step approach using frequent itemset mining and a learning method to select the rules. The method proposed in {cite}`setzu63` merges local explanation rules into a unique global weighted rule list by using a scoring system.


```{figure} ./rules_rxren.png
---
name: fig:rules_rxren
width: 600px
align: center
---
Example of local factual and counter-factual explanation returned by <span style="font-variant:small-caps;">rxren</span> {cite}`Guidotti2021`.
```

<!--
<span style="font-variant:small-caps;">corels</span>
-->


## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi.

