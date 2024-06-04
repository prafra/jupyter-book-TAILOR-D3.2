# Explainable AI

<!-- TODO: add resources or remove duplicate paragraph! -->

## In Brief

**Explainable AI** (often shortened to **XAI**) is one of the ethical dimensions that is studied in the <a href="https://tailor-network.eu/" target=_blank>TAILOR project</a>.
The origin of XAI dates back to the entering into force of the General Data Protection Regulation (GDPR).
The GDPR {cite}`gdpr`, in its <a href="https://gdpr-info.eu/recitals/no-71/" target=_blank>Recital 71</a>, also mentions the right to explanation, as a suitable safeguard to ensure fair and transparent processing in respect of data subjects. It is defined as the right "to obtain an explanation of the decision reached after profiling". <!-- TODO: add link to profiling -->

## More in details

According to the <a href="https://wayback.archive-it.org/12090/20201227221227/https://ec.europa.eu/digital-single-market/en/news/ethics-guidelines-trustworthy-ai" target=_blank>High-Level Expert Group on Artificial Intelligence - Ethics Guidelines for Trustworthy AI</a>, explainability topic is included in the broader [transparency](./Transparency.md) dimension. Explainability concerns the ability to explain both the technical processes of an AI system and the related human (e.g., application areas of a system).
This aspect is analyzed also in the {doc}`blackbox_transparent` entry. <!-- {doc}`./XAI_dimensions`-->

The goal of this task is explaining how the decision system returned certain outcomes (the so-called *Black Box Explanation*). Moreover, the Black Box Explanation problem can be further divided among *Model Explanation* when the explanation involves the whole logic of the obscure classifier, *Outcome Explanation* when the target is to understand the reasons for the decisions on a given object, and *Model Inspection* when the target to understand how internally the black box behaves changing the input.

<!-- TODO: prendere solo un pezzo della figura -->
```{figure} ./T3.1_taxonomy.jpg
---
name: T3.1taxonomy31
width: 600px
align: center
---
A possible taxonomy about solutions to the Open the Black-Box problem {cite}`guidotti_survey`.
```

On a different dimension, a lot of effort has been put into defining what are the possible techniques (e.g., we can discriminate between {doc}`./model_specific`), what is the explained outcome (i.e., {doc}`./global_local`), and to understand the {doc}`./feature_importance`. Then, it is important to note that a variety of different kinds of explanations can be provided, such as {doc}`./single_tree`, {doc}`./feature_importance`, {doc}`./saliency_maps`, Factual and Counterfactual, Exemplars and Counter-Exemplars, and Rules List and Rules Sets.<!--[Factual and Counterfactual](./counterfactuals.md), exemplars and counter-exemplars, [Rules List and Rules Sets](./rules.md).-->

<!-- TODO: Togliere!!! -->
On a different dimension, a lot of effort has been put into defining what are the possible techniques (e.g., we can discriminate between {doc}`./model_specific`), the requirements to provide good explanations (see <!-- TODO: add anchor {ref}`guidelines` --> guidelines), how to <!-- TODO: add link [evaluate explanations](./evaluating_explanations.md) --> evaluate explanations, and to understand the {doc}`./feature_importance`. Then, it is important to note that a variety of different kinds of explanations can be provided, such as {doc}`./single_tree`, {doc}`./feature_importance`, {doc}`./saliency_maps`, Factual and Counterfactual, Exemplars and Counter-Exemplars, and Rules List and Rules Sets.<!--[Factual and Counterfactual](./counterfactuals.md), exemplars and counter-exemplars, [Rules List and Rules Sets](./rules.md).-->


Transparency
	Dimensions of Explanations
	        Black Box Explanation vs Explanation by Design
	        Model-Specific vs Model-Agnostic Explainers
	        Global vs Local Explanations
	XAI
		Kinds of (Post-Hoc) Explanations --> cambiare il link a "Increasing research on XAI"
			Feature Importance
			Saliency Maps
			Single Tree Approximation


## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Francesca Pratesi.

