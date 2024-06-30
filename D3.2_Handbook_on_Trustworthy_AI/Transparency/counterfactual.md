# Counterfactuals

<!-- TODO: add resources or remove duplicate paragraph! -->

## In Brief

A **counterfactual explanation** shows what should have been different to change the decision of an AI system. For example, a counterfactual explanation could be a local explaination of a certain istance by providing the nearest istances that lead to a different decision or describing a small change in the input of the model that lead to a change in the outcome of the model.
<!--
## More in details

A counterfactual explanation shows what should have been different to change the decision of an AI system. Counterfactual explanations are becoming an essential component in XAI methods and applications {cite}`apicella6` because they help people in reasoing on the cause-effect relations between analyzed instances and AI decision {cite}`byrne17`.
Indeed, while direct explanations such as features importance, decision rules, and saliency maps are important for understanding the reasons for a certain decision, a counterfactual explanation reveals what should be different in a given instance to obtain an alternative decision {cite}`wachter2017right_73`. Thinking in terms of “counterfactuals” requires the ability to figure a hypothetical causal situation that contradicts the observed one {cite}`molnar2020interpretable_50`.
The “cause” of the situation are the features describing the under investigation and that “caused” a certain decision, the "event" models the decision.

The most used types of counterfactual explanations are indeed prototype-based counterfactuals. In {cite}`wachter2017counterfactual_74`, counterfactual explanations are provided by an explanation method that solves an optimization problem that given an instance under analysis, a training dataset, and a black box function, returns an instance similar to the input one and with minimum changes, i.e., minimum distance, but that revert the black box outcome. The counterfactual explanation describes the smallest change that can be made in that particular case to obtain a different decision from the AI.
In {cite}`ustun2019actionable_72` the generation of diverse counterfactuals using mixed integer programming for linear models is proposed. As previously mentioned, <span style="font-variant:small-caps;">ABELE</span> {cite}`guidotti2019latent_31` also returns synthetic counter-exemplar images that highlights the similarities and differences between images leading to the same decision and images leading to other decisions.

Another modeling for counterfactual explanations consists of the logical form that describes a causal situation like: *"If X had not occurred, Y would not have occurred"* {cite}`molnar2020interpretable_50`. 
The local model-agnostic <span style="font-variant:small-caps;">LORE</span> explanation method {cite}`guidotti2019factual_30`, besides a factual explanation rule, also provides a set of counterfactual rules that illustrate tho logic used by the AI to obtain a different decision with minimum changes. For example, in Figure {numref}`{number} <fig:counterfactual>`, the set of counterfactual rules is highlighted in purple and shows that *if income > 900 then grant, or if race = white then grant*, clarifying which particular changes would revert the decision. In {cite}`laugel2017inverse_41`, authors proposed a local neighborhood generation method based on a Growing Spheres algorithm that can be used for both finding counterfactual instances, but also as a base for extracting counterfactual rules.


```{figure} ./counterfactual.png
---
name: fig:counterfactual
width: 600px
align: center
---
Example of local factual and counter-factual explanation returned by <span style="font-variant:small-caps;">LORE</span> {cite}`Guidotti2021`.
```


-->

## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography}
:style: unsrt
:filter: docname in docnames
```
> This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi.

