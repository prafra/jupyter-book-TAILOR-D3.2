# Fair Machine Learning

<!-- TODO: fairlean.py is recognized as a link... -->

## In brief

**Fair Machine Learning models** take into account the issues of bias and fairness. Approaches can be categorized as pre-processig, which transform the
input data, as in-processing, which modify the learning algorithm, and post-processing, which alter models' internals or their decisions.

## More in Detail

Fairness can be promoted in three different ways in ML as surveyed in {cite}`caton2020fairness`. This survey provides a clear categorization of methods under pre-process, in-process and post-process approaches. 

*Pre-process approaches* are the most flexible ones that transforms the data so that the underlying bias is removed. One advantage of using pre-process techniques is that it is the most inspectable method, as it is the earliest opportunity to mitigate biases and measure how it affects the outcome compared to the other two approaches in fair machine learning {cite}`d2017conscientious`. Suppression or  Fairness Through Unawareness is a baseline method that accounts for removing the sensitive features and proxy sensitive features from the dataset {cite}`gajane2017formalizing`. A recent study {cite}`ruf2020active` proved that removing sensitive information does not guarantee fair outcomes. 
Massaging the dataset (relabeling) method can act in two ways:
1. Identify unfair outcomes and correct them by changing the label to what ought to have happened. 
2. Identify sensitive classes and relabel them so that the outcome is fair. 
Reweighting approach has several positive aspects compared to suppression and relabeling. It works by postulating that a fair dataset would have no conditional dependence on the outcome of any of the sensitive attributes. That means it corrects the past unfair outcomes by giving more weightage to correct cases and less weightage to incorrect cases. Learning fair representations approach fairness fundamentally differently by aiming for a middle ground between-group fairness and individual fairness {cite}`zemel2013learning`. It turns the pre-process problem into a combined optimization problem that finds trade-offs between-group fairness, individual fairness, and accuracy.


*In-process approaches* modify the learning algorithms to remove biases during model training by either incorporating fairness into the optimization equation or imposing a constraint as regularization {cite}`bellamy2018ai,berk2017convex`. The main categories of in-processing approaches are adversarial debiasing and prejudice removal. The former involves an adversary to predict the sensitive attributes from a downstream task (classification or regression), and thus the model learns a representation independent of sensitive features. Learning fair representations can be done by adding noise to the predictive power using the regulation. Adversarial reweighted learning {cite}`lahoti2020fairness` uses non-sensitive features and labels to measure unfairness and co-train the adversarial reweighting approach to improving learning. On the other hand, the prejudice remover approach has various techniques to mitigate biases during training. 
Some of the standard methods are:

1. Heuristic-based: Use Roony rules {cite}`kuhlman2019fare`, which effectively rank problems.
2. Algorithmic Changes: These can be made in every single step of calibration, such as input, output, and model structure {cite}`fish2016confidence,beutel2019fairness,slack2020fairness,beutel2019putting,d2017conscientious,wang2021fair,dwork2018decoupled,louizos2015variational,mehrotra2021mitigating`.
3. Using pre-trained models: It involves combining available pre-trained models and transferring them to reduce bias {cite}`madras2018learning`.
4. Counterfactual and Causal Reasoning: This considers a model to be group or individual fair if its prediction in the real world is similar to the counterfactual world, where individuals belong to a different protected group. Causal reasoning can be used to caution against those counterfactual explanations {cite}`loftus2018causal,nabi2019learning`. A primary concern on the use and misuse of counterfactual fairness has been studied in{cite}`kasirzadeh2021use`.

Finally, *post-process approaches* are the most versatile approaches if the model is already in the production stage and it does not require retraining the model. Another advantage of using post-processing is that the fairness (individual and group) of any downstream tasks can be easily satisfied concerning the domain and application of the model {cite}`lohia2019bias`. Also, post-processing is agnostic to the input data, which makes it easier to implement. However, post-processing procedures may present weaker results when compare to pre-processing ones {cite}`kozodoi2022fairness,pessach2022review`. 

**Assessment tools**: Tools can assist practitioners or organizations in documenting the measures, providing guidance, helping formalize processes, and empowering automated decisions. There are various types of tools to identify and mitigate the biases. Out of which, technical/quantitative tools and qualitative tools are primarily used in real-world applications by engineers and data scientists.Technical/quantitative tools focus on data or AI pipeline through technical solutions. One major drawback is that it may miss essential fairness considerations; for example, it cannot be employed to mitigate bias in the COMPAS algorithm as the nuances could not be adequately captured. It lacks methods to understand and mitigate biases but perpetuates a misleading notion that "Fair ML" is not a complex task to achieve. Some of the standard solutions in this category are:
1. IBM's AI Fairness 360 Toolkit: It is a python toolkit through the lens of technical solutions under fairness metrics.
2. Google's What-If Tool explores the model's performance on a dataset through hypothetical situations. It allows users to explore different definitions of fairness constraints under various feature intersections.
3. Microsoft's fairlean.py: It is a python package consisting of mitigation algorithms and metrics for model assessment. 

On the other hand, Quantitative techniques can delve into the nuances of fairness. They can enable teams to explore the societal implications, analyses fairness harms and tradeoffs, and propose plans to find the potential sources of bias and ways to mitigate them. Two of the most prominent qualitative techniques are:
1. Co-designed AI fairness checklist (2020): This checklist is designed by a group of Microsoft researchers and academicians, 49 individuals from 12 technical organizations. It covers the items included in different stages of the AI pipeline, including envision, define, prototype, build, launch, and evolve, and is customizable according to the deployment. 
2. Fairness Analytic (2019): This analytic tool is developed by Mulligan et al. to promote fairness at the earlier stages of product development. It enables teams to understand biases from a specific application perspective to analyze and document their effects.
 
While these tools exist to analyze the potential harms, it is the responsibility of users to understand the after-effects of which tools they are using, and which types of biases can mitigate. A detailed review of landscape and gaps in fairness tool kits is given in {cite}`lee2021landscape`.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Resmi Ramachandran Pillai, Fredrik Heintz, Miguel Couceiro, and Guilherme Alves.
