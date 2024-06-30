# Transparency

<!--- This is a comment -->

<!-- 

TODO: add ./T3.1_taxonomy.jpg to github!!! 
+ add pyramid.jpeg
+ add reference to Open the Black-Box Problem in introduction


-->

## In Brief

The **transparency** requirement is closely linked with the principle of explicability and encompasses transparency of elements
relevant to an AI system: the data, the system and the business models.

In Machine Learning domains, the problem of transparency is often called the *"Open the Black-Box Problem"* (see below).

<!-- **Explainable AI** (often shortened to **XAI**) is one of the ethical dimensions that is studied in the <a href="https://tailor-network.eu/" target=_blank>TAILOR project</a>.
The origin of XAI dates back to the entering into force of the General Data Protection Regulation (GDPR).
The GDPR {cite}`gdpr`, in its <a href="https://gdpr-info.eu/recitals/no-71/" target=_blank>Recital 71</a>, also mentions the right to explanation, as a suitable safeguard to ensure fair and transparent processing in respect of data subjects. It is defined as the right "to obtain an explanation of the decision reached after profiling". 
According to NIST report {cite}`nist`, an explanation is the evidence, support, or reasoning related to a system’s output or process, where the output of a system differs by task, and the process refers to the procedures, design, and system workflow which underlie the system.
--> <!-- TODO: add link to profiling -->


## Abstract

While other aspects of ethics and trustworthiness, such as [Respect for Privacy](../Privacy_and_Data_Governance/Privacy_and_Data_Governance), are not novel concepts, and a lot of scientific literature has been explored on these topics, the study of transpacency is a relatively new challenge.

In this part, we will cover the main elements that define the explanation of AI systems. First, we will try to survey briefly the main guidelines related to transparency.
Then, we summarize a taxonomy that can be used to classify possible explanations. 
We will define the possible  {doc}`./XAI_dimensions` (e.g., we can discriminate between {doc}`./model_specific`).
Next, we will describe the requirements to provide good explanations and some of the problems related to the Transparency topic. 
Finally, we will give some examples of possible solutions we can adopt to provide explanations describing the reasoning behind an ML/AI model.

## Motivation and Background 

So far, the usage of black boxes in AI and ML processes has implied the possibility of inadvertently making wrong decisions due to a systematic bias in training data collection. Several practical examples have been provided, highlighting the “bias in, bias out” concept. One of the most famous examples of this concept regards a classification task: the algorithm's goal was to distinguish between photos of Wolves and Eskimo Dogs (huskies) {cite}`ribeiro`. Here, the training phase of the process was done with 20 images, hand-selected such that all pictures of wolves had snow in the background, while pictures of huskies did not. This choice was intentional because it was part of a social experiment. In any case, on a collection of additional 60 images, the classifier predicts “Wolf” if there is snow (or light background at the bottom), and “Husky” otherwise, regardless of animal color, position, pose, etc (see an example in Fig. {numref}`{number} <husky>`).


```{figure} ./husky3.png
---
name: husky
width: 600px
align: center
---
Raw data and explanation of a bad model's prediction in the "Husky vs Wolf" task {cite}`ribeiro`. On the left, there is the original image; on the right, there is the explanation of the classification.
```

However, one of the most worrisome cases was discovered and published by ProPublica, an independent, nonprofit newsroom that produces investigative journalism with moral force. In {cite}`propublica`, the authors showed how software can actually be racist. In a nutshell, the authors analyzed a tool called COMPAS (which stands for Correctional Offender Management Profiling for Alternative Sanctions). COMPAS tries to predict, among other indexes, the recidivism of defendants, who are ranked low, medium, or high risk. It was used in many US states (such as New York and Wisconsin) to suggest to judges an appropriate probation or treatment plan for individuals being sentenced. Indeed, the tool was quite accurate (around 70 percent overall with 16,000 probationers), but ProPublica journalists found that black defendants were far more likely than white defendants to be incorrectly judged to be at a higher risk of recidivism, while white defendants were more likely than black defendants to be incorrectly flagged as low risk.

From the above examples, it appears evident that explanation technologies can help companies for creating safer, more trustable products, and better managing any possible liability they may have.

### The three elements of Transparency

According to the <a href="https://wayback.archive-it.org/12090/20201227221227/https://ec.europa.eu/digital-single-market/en/news/ethics-guidelines-trustworthy-ai" target=_blank>High-Level Expert Group on Artificial Intelligence report</a>, the transparency dimension is related to three different but related aspects: traceability, explainability, and communication (as we report as follows) {cite}`hleg`.

<!--
explainability concerns the ability to explain both the technical processes of an AI system and the related human decisions (e.g., application areas of a system). Following the GDPR interpretation, in -->

*Traceability.* The data sets and the processes that yield the AI system’s decision, including those of data gathering and data labelling as well as the algorithms used, should be documented to the best possible standard to allow for traceability and an increase in transparency. This also applies to the decisions made by the AI system. This enables
identification of the reasons why an AI-decision was erroneous which, in turn, could help prevent future mistakes.
Traceability facilitates [auditability](../Diversity_Non-Discrimination_and_Fairness/auditing.md) as well as [explainability](./XAI.md).

*Explainability.* Explainability concerns the ability to explain both the technical processes of an AI system and the related human decisions (e.g., application areas of a system). Technical explainability requires that the decisions made by an AI system can be understood and traced by human beings. Moreover, trade-offs might have to be made between enhancing a system's explainability (which may reduce its accuracy) or increasing its accuracy (at the cost of explainability). Whenever an AI system has a significant impact on people’s lives, it should be possible to demand a suitable explanation of the AI system’s decision-making process. Such explanation should be timely and adapted to the expertise of the stakeholder concerned (e.g., layperson, regulator or researcher). In addition, explanations of the degree to which an AI system influences and shapes the organisational decision-making process, design choices of the system, and the rationale for deploying it, should be available (hence ensuring business model transparency).

*Communication.* AI systems should not represent themselves as humans to users; humans have the right to be informed that they are interacting with an AI system (this transparency obbligation is guaranteed by the [AI Act](../main/Ethical_Legal_Framework/AI_ACT). This entails that AI systems must be identifiable as such. In addition, the option to decide against this interaction in favour of human interaction should be provided where needed to ensure compliance with fundamental rights. Beyond this, the AI system's capabilities and limitations should be communicated to AI practitioners or end-users in a manner appropriate to the use case at hand. This could encompass communication of the AI system's level of accuracy, as well as its limitations.


<!-- **Explainable AI** (often shortened to **XAI**) is one of the ethical dimensions that is studied in the <a href="https://tailor-network.eu/" target=_blank>TAILOR project</a>.
The origin of XAI dates back to the entering into force of the General Data Protection Regulation (GDPR).
The GDPR {cite}`gdpr`, in its <a href="https://gdpr-info.eu/recitals/no-71/" target=_blank>Recital 71</a>, also mentions the right to explanation, as a suitable safeguard to ensure fair and transparent processing in respect of data subjects. It is defined as the right "to obtain an explanation of the decision reached after profiling". 
According to NIST report {cite}`nist`, an explanation is the evidence, support, or reasoning related to a system’s output or process, where the output of a system differs by task, and the process refers to the procedures, design, and system workflow which underlie the system.
--> <!-- TODO: add link to profiling -->


## Open the Black-Box Problem

The *Open the Black Box Problems* for understanding how a black box works can be summarized in the taxonomy proposed in {cite}`guidotti_survey` and reported in Fig. {numref}`{number} <T3.1taxonomy31>`. The Open the Black Box Problems can be separated from one side as the problem of explaining how the decision system returned certain outcomes (*Black Box Explanation*) and on the other side as the problem of directly designing a transparent classifier that solves the same classification problem (*Transparent Box Design*). Moreover, the Black Box Explanation problem can be further divided among *Model Explanation* when the explanation involves the whole logic of the obscure classifier, *Outcome Explanation* when the target is to understand the reasons for the decisions on a given object, and *Model Inspection* when the target to understand how internally the black box behaves changing the input.

```{figure} ./T3.1_taxonomy.jpg
---
name: T3.1taxonomy31
width: 600px
align: center
---
A possible taxonomy about solutions to the Open the Black-Box problem {cite}`guidotti_survey`.
```

<!-- TODO: report the chosen paragraph from XAI -->
On a different dimension, a lot of effort has been put into defining what are the possible techniques {doc}`./XAI_dimensions` (e.g., we can discriminate between {doc}`./model_specific`), the requirements to provide good explanations (see <!-- TODO: add anchor {ref}`guidelines` --> guidelines), how to <!-- TODO: add link [evaluate explanations](./evaluating_explanations.md) --> evaluate explanations, and to understand the {doc}`./feature_importance`. Then, it is important to note that a variety of different kinds of explanations can be provided, such as {doc}`./single_tree`, {doc}`./feature_importance`, {doc}`./saliency_maps`, [Factual and Counterfactual](./counterfactual.md), [Exemplars and Counter-Exemplars](./prototypes.md), and [Rules List and Rules Sets](./rules.md).<!--, exemplars and counter-exemplars, .-->

## Guidelines

Given the relative novelty of the topic, a lot of guidelines have been developed in recent years.

However, the most authoritative guideline is the <a href="https://wayback.archive-it.org/12090/20201227221227/https://ec.europa.eu/digital-single-market/en/news/ethics-guidelines-trustworthy-ai" target=_blank>High-Level Expert Group on Artificial Intelligence - Ethics Guidelines for Trustworthy AI</a>. Here, the explainability topic is included in the broader [transparency](./blackbox_transparent.md). Following the GDPR interpretation, in {cite}`hleg`, it is stated that whenever an AI system has a significant impact on people’s lives, it should be possible to demand a suitable explanation of the AI system’s decision-making process. Such explanation should be timely and adapted to the expertise of the stakeholder concerned (e.g., layperson, regulator, or researcher). In addition, explanations of the degree to which an AI system influences and shapes the organizational decision-making process, design choices of the system, and the rationale for deploying it, should be available (hence ensuring business model transparency).

Another distinguished authority that has been worked on ethical guidance is **the Alan Turing Institute**, the UK’s national institute for data science and artificial intelligence, where David Leslie {cite}`leslie` summarized the risks due to the lack of transparency or the absence of a valid explanation, and he advocates the use of <!-- TODO: add link {doc}`./counterfactuals`--> counterfactuals for contrasting unfair decisions. Together with the Information Commissioner’s Office (ICO), which is responsible for overseeing data protection in the UK, it has been published more recent and complete guidance {cite}`ico`. Here, six steps are recommended to develop a system:
1. Select priority explanations by considering the domain, use case, and impact on the individual.
2. Collect and pre-process data in an explanation-aware manner, stressing the fact that the way in which data is collected and pre-processed may affect the quality of the explanation.
3. Build systems to ensure to being able to extract relevant information for a range of explanation types.
4. Translate the rationale of your system’s results into useable and easily understandable reasons, e.g., transforming the model’s logic from quantitative rationale into intuitive reasons or using everyday language that can be understood by non-technical stakeholders.
5. Prepare implementers to deploy the AI system, through appropriate training.
6. Consider how to build and present the explanation, particularly keeping in mind the context and contextual factors (domain, impact, data, urgency, audience) to deliver appropriate information to the individual.

Nevertheless, the attention on this theme is not relegated to the European border. Indeed, as an example of US effort in dealing with Explainability and Ethics, **NIST, the National Institute of Standards and Technology of Maryland**, developed some guidelines, and a white paper {cite}`nist` was published after a first draft[^nist_draft] was published in 2020, a variety of comments[^nist_comments] was collected, and a workshop[^nist_workshop] involving different stakeholders was held. The white paper {cite}`nist` analyzes the multidisciplinary nature of explainable AI and acknowledges the existence of different users who requires different kinds of explanations, stating that one-size-fits-all explanations do not exist. The fundamental properties of explanations contained in the report are: 
* *Meaningfulness*, i.e., explanations must be understandable to the intended consumer(s). This means that there is the need to consider the intended audience and some characteristics they can have, such as prior knowledge or the overall psychological differences between people. Moreover, the explanation’s purpose is relevant too. Indeed, different scenarios and needs impact on what is important and useful in a given context. This implies understanding the audience's needs, level of expertise, and relevancy to the question or query.
* *Accuracy*, i.e., explanations correctly reflect a system's process for generating its output. Explanation accuracy is a distinct concept from decision accuracy. Explanation accuracy needs to account for the level of detail in the explanation. This second principle might be in contrast with the previous one: a detailed explanation may accurately reflect the system’s processing but sacrifice how useful and accessible it is to certain audiences, while  a brief, simple explanation may be highly understandable but would not fully characterize the system. 
* *Knowledge limits*, i.e., characterizing the fact that a system only operates under conditions for which it was designed and when it reaches sufficient confidence in its output. This practice safeguard answers so that a judgment is not provided when it may be inappropriate to do so. This principle can increase trust in a system by preventing misleading, dangerous, or unjust outputs.


## Software Frameworks Supporting Dimension

Within the European Research Council (ERC) <a href="https://xai-project.eu/" target=_blank>XAI project</a> and the European Union's Horizon 2020 <a href="http://project.sobigdata.eu/" target=_blank> SoBigData++ project</a>, we are developing an infrastructure for sharing experimental datasets and explanation algorithms with the research community, creating a common ground for researchers working on explanations of black boxes from different domains. 
All resources, provided they are not prohibited by specific legal/ethical constraints, will be collected and described in a <a href="https://sobigdata.d4science.org/catalogue-sobigdata" target=_blank>findable catalogue</a>.
A dedicated virtual research environment will be activated, so that a variety of relevant resources, such as data, methods, experimental workflows, platforms, and literature, will be managed through the SoBigData++ e-infrastructure services and made available to the research community through a variety of regulated access policies.
We will provide a link to the libraries and framework as soon as they be will fully published.


## Main Keywords
- {doc}`./XAI_dimensions`: **Dimensions of explanations** are useful to analyze the interpretability of AI systems and to classify the explanation method.
- {doc}`./blackbox_transparent`: The difference between **Black Box Explanation** (or **Post-hoc Explanations**) and **Explanation by Design** (or **Ante-hoc Explanations**) regards the ability to know and exploit the behaviour of the AI model. With a black box explanation, we pair the black box model with an interpretation the black box decisions or model, while in the second case, the strategy is to rely, by design, on a transparent model.
- {doc}`./model_specific`: We distinguish between **model-specific** or **model-agnostic** explanation method depending on whether the technique adopted to retrieve the explanation acts on a particular model adopted by an AI system, or can be used on any type of AI. 
- {doc}`./global_local`: We distinguish between a **global** or **local** explanation depending on whether the explanation allows understanding the whole logic of a model used by an AI system or the explanation refers to a specific case, i.e., only a single decision is interpretable.
- {doc}`./XAI`: **Explainable AI** (often shortened to **XAI**) is one of the ethical dimensions described in the General Data Protection Regulation (GDPR).
Indeed, the GDPR mentions the right to explanation, as a suitable safeguard to ensure fair and transparent processing in respect of data subjects. It is defined as the right "to obtain an explanation of the decision reached after profiling".
- {doc}`./XAI_kinds`: Explanations returned by an AI system depend on various factors (such as the task or the available data); generally speaking, each kind of explanations serves better a specific context.
- {doc}`./counterfactual`: A **counterfactual explanation** shows what should have been different to change the decision of an AI system. For example, a counterfactual explanation could be a local explaination of a certain istance by providing the nearest istances that lead to a different decision or describing a small change in the input of the model that lead to a change in the outcome of the model.
- {doc}`./feature_importance`: The **feature importance** technique provides a score, representing the “importance”, for all the input features for a given AI model, i.e., a higher importance means that the corresponding feature will have a larger effect on the model.
- {doc}`./lore`: **Local Rule-based Explanation** aims to extract a rule that provides a local explaination for a certain instance of the model.
- {doc}`./prototypes`: **Prototype-based explanation** methods return as explanation a selection of particular instances of the dataset for locally explaining the behavior of the AI system.
- {doc}`./rules`: A **decision rule** is generally formed by a set of conditions and by a consequent, e.g., if conditions, then consequent.
- {doc}`./saliency_maps`: Saliency maps are explanations used on image classification tasks. A **saliency map** is an image where each pixel's color represents a value modeling the importance of that pixel in the original image (i.e., the one given in input to the explainer) for the prediction.
- {doc}`./single_tree`: The **single tree appoximation** is an approach that aims at building a decision tree to approximate the behavior of a black box, typically a neural network.


## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography} ./references.bib
:style: unsrt
:filter: docname in docnames
```

> This entry was readapted from *Pratesi, Trasarti, Giannotti. Ethics in Smart Information Systems. Policy Press* and from *Guidotti, Monreale, Ruggieri, Turini, Giannotti, Pedreschi. A survey of methods for explaining black box models. ACM Computing Surveys, Volume 51 Issue 5 (2019)* by Francesca Pratesi.

[^nist_draft]: https://doi.org/10.6028/NIST.IR.8312-draft
[^nist_comments]: https://www.nist.gov/artificial-intelligence/comments-received-four-principles-explainable-artificial-intelligence-nistir
[^nist_workshop]: https://www.nist.gov/system/files/documents/2021/09/24/XAI_Workshop_Summary_Final_20210922.pdf

