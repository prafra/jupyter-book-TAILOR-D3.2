# Rules

## In brief

## More in detail

A decision rule is generally formed by a set of conditions and by a
consequent, e.g., \*if conditions, then consequent\*. **"Given a record,
a decision rule assigns to the record the outcome specified in the
consequent if the conditions are verified [@agrawalVLDB]". The most
common rules are *if-then rules*** that take into consideration rules
with clauses in conjunction. On the other hand, for *m-of-n* rules given
a set of *n* conditions, if *m* of them are verified, then the
consequence of the rule is applied [@murphy1991id2_51]. When a set of rules is
used, then there are different strategies to select the outcome. For
*list of rules* the order of the list is considered and the model
returns the outcome of the first rule that verifies the conditions
[@yinICDM]. For instance, *falling rule lists* are if-then rules ordered
with respect to the probability of a specific outcome [@rudin75]. On
the other hand, *decision sets* are unordered lists of rules. Basically
each rule is an independent classifier that can assign its outcome
without regard for any other rules [@lakkaraju39]. Voting strategies are
used to select the final outcome. \[style\]

List of rules and set of rules are adopted as explanation both from
explanation methods but also from transparent classifiers. In both cases
the reference context is tabular data. In [@augasta8] the explanation
method [rxren]{.smallcaps} unveil with rules list the logic behind a
trained neural network. First, [rxren]{.smallcaps} prunes the
insignificant input neurons and identifies the data range necessary to
classify the given test instance with a specific class. Second,
[rxren]{.smallcaps} generates the classification rules for each class
label exploiting the data ranges previously identified, and improve the
initial list of rules by a process that prunes and updates the rules.
Figure [\[fig:rules\_rxren\]](#fig:rules_rxren){reference-type="ref"
reference="fig:rules_rxren"} shows an example of rules returned by
[rxren]{.smallcaps}. A survey on techniques extracting rules from neural
networks is [@Andrews4]. All the approaches in [@Andrews4], including
[rxren]{.smallcaps} are model-specific explainers. \[style\]

\centering
![Example of list of rules explanation returned by
[rxren]{.smallcaps}](TAILOR_T31_rules1.png){width="300px"}

[\[fig:rules\_rxren\]]{#fig:rules_rxren label="fig:rules_rxren"}

As previously mentioned, an alternative line of research to black box
explanation is the design of transparent models for the AI systems. The
[corels]{.smallcaps} method [@angelino5] is a technique for building
rule lists for discretized tabular datasets. [corels]{.smallcaps}
provides an optimal and certifiable solution in terms of rule lists. An
example of rules list returned by [corels]{.smallcaps} is reported in
Figure [\[fig:rules\_corels\]](#fig:rules_corels){reference-type="ref"
reference="fig:rules_corels"}. The rules are read one after the other,
and the AI would take the decision of the first rule for which the
conditions are verified. Decision sets are built by the method presented
in [@lakkaraju39]. The if-then rules extracted for each set are
accurate, non-overlapping, and independent. Since each rule is
independently applicable, decision sets are simple, succinct, and easily
to be interpreted. A decision set is extracted by jointly maximizing the
interpretability and predictive accuracy by means of a two step approach
using frequent itemset mining and a learning method to select the rules.
The method proposed in [@setzu63] merges local explanation rules into a
unique global weighted rule list by using a scoring system. \[style\]

\centering
![Example of list of rules explanation returned by
[corels]{.smallcaps}](TAILOR_T31_rules2.png){width="300px"}

[\[fig:rules\_corels\]]{#fig:rules_corels label="fig:rules_corels"}

> This entry was readapted from \*Guidotti, Monreale, Pedreschi,
> Giannotti. Principles of Explainable Artificial Intelligence. Springer
> International Publish- ing (2021)\* by Francesca Pratesi and Riccardo
> Guidotti.
