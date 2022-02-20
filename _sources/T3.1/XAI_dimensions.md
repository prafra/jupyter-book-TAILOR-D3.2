# Dimensions of Explanations

## Definition
Dimensions of Explanations are useful to analyze the interpretability of AI systems and to classify the explanation method. 

## More in detail

The goal of {doc}`../T3.1` is to *interpret* AI reasoning. According to Merriam-webster, to *interpret* means to give or provide the meaning or to explain and present in understandable terms some concepts.
Therefore, in AI, *interpretability* is defined as the ability to *explain* or to provide the meaning in understandable terms to a human {cite}`arrietaXAItassonomy`,{cite}`doshi_rigorous`. These definitions assume that the concepts composing an explanation and expressed in the understandable terms are self-contained and do not need further explanations. An explanation is an “interface” between a human and an AI, and it is at the same time both human understandable and an accurate proxy of the AI.

We can identify a set of dimensions to analyze the interpretability of AI systems that, in turn, reflect on existing different types of explanations {cite}`guidotti_survey`. 
Some of these dimensions are related to *functional requirements* of explainable artificial intelligence, i.e., requirements that identify the algorithmic adequacy of a particular approach for a specific application, while others to the *operational requirements*, i.e., requirements that take into consideration how users interact with an explainable system and what is the expectation. 
Some dimensions instead derive from the need of *usability criteria* from a user perspective, while other derive from the need of guarantees against any vulnerability issues. 

Recently, all these requirements have been analyzed {cite}`flach_fat` to provide a framework allowing the systematic comparison of explainability methods. In particular, in {cite}`flach_fat` authors propose *Explainability Fact Sheets* which enable researchers and practitioners to assess capabilities and limitations of a particular explainable method. 
As an example, given an explanation method *m*, we can consider the following functional requirements. 
*(i)* Even though *m* is designed to explain regressors, can we use it to explain probabilistic classifiers?
*(ii)* Can we employ *m* on categorical features even though it only works on numerical features? On the other hand, as an operational requirement, can we consider which is the *function of the explanation*? Provide transparency, assess the fairness, etc.

Besides the detailed requirements illustrated in {cite}`flach_fat`, in the literature it is recognized a categorization of explanation methods among fundamental pillars {cite}`adadi`,{cite}`guidotti_survey`: *(i)* black box explanation vs explanation by design *(link TBA)*, *(ii)* global vs local explanations *(link TBA)*, *(iii)* {doc}`model_specific`. <!---In the following we present details of these distinctions and other important features characterizing XAI methods.--> 

Fig. {numref}`{number} <xai-tax>` illustrates a summarized ontology of the taxonomy used to classify XAI methods.

```{figure} ./xai_taxonomy.png
---
name: xai-tax
width: 600px
align: center
---
A summarized ontology of the taxonomy of XAI methods {cite}`Guidotti2021`.
```



```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi and Riccardo Guidotti.
