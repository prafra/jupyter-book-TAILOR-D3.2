# The TAILOR Handbook of Trustworthy AI

**An encyclopedia of the major scientific and technical terms related to Trustworthy Artificial Intelligence**

<!--**TAILOR: Foundations of Trustworthy AI – Integrating Reasoning, Learning and Optimization**

Add an introduction to the first page.
Add an Executive summary to the first page. This should be stand-alone, so that we can use it in formal reporting, for websites, social media etc.


This book (to be consolidated in the second phase of the project) represents the first period deliverable of the TAILOR project, providing an encyclopedia of the major terms related to trustworthiness.
-->

## Executive Abstract

The main goal of the *Handbook of Trustworthy AI* (HTAI) is to provide to non-experts, researchers and students, an overview of the problem related to the developing of ethical and trustworthy AI systems. In particular, the HTAI aims at providing an overview of the main dimensions of trustworthiness, starting with a understandable explanation of the dimension itself, and then presenting the characterization of the problems (starting with a brief summary and the explanation of the importance of the dimension, presenting a taxonomy and some guidelines, if they are available and consolidated), summarizing what are the major challenges and solutions in the field, and concluding with what are the latest research developments.

Each entry will be correlated with a bibliography, allowing the reader to go more in depth with a specific topic if interested knowing more about it.

All the entries have a list of authors that have directly contributed to the writing of the HTAI (some of them are already external to the TAILOR consortium), while the complete list of contributors can be found [here](../authors.md).


## About the TAILOR Handbook

The HTAI assumes an encyclopedia-like structure and is presented in the form of a publicly accessible WIKI. To do so, the Jupiter Book framework has been used. In the long term, the Handbook is meant to become a point of reference for resources (key concepts, tools, documentation, tutorials, teaching material, etc.) related to Trustworthy AI.

Here, you can find the {doc}`./main/Ethical_Legal_Framework/Ethical_Legal_Framework` we are referring to, to have the context of the current European context.

<!-- {doc}`../T3.4/L1.Accountability_and_Reproducibility`. -->

Moreover, you can find information about the topics of each of the task of the <a href="https://tailor-network.eu" target=_blank>TAILOR WP3</a>, summarizing one of the aspects of Trustworthy AI. The organization of the chapters is based on the seven principles described in the Ethics Guidelines for Trustworthy AI of the High-Level Expert Group on Artificial Intelligence {cite}`HLEG`. In particular, in this Encyclopedia, you can find definitions related to:
- [Human Agency and Oversight](./Human_Agency_and_Oversight/Human_Agency_and_Oversight.md). This section of the Encyclopedia defines Human agency, i.e., the necessity of knowledge and tools to comprehend and interact properly with AI systems, and Human oversight in different phases of AI processes.
- [Technical Robustness and Safety](./Technical_Robustness_and_Safety/Technical_Robustness_and_Safety.md). In this section of the Encyclopedia, we analyze the challenges in developing AI systems that are safe, reliable, and robust; we also provide a way to evaluate these aspects in practice, and we promote the dynamic evaluation in managing risk during the normal use of AI systems.
- [Privacy and Data Governance](./Privacy_and_Data_Governance/Privacy_and_Data_Governance.md). This section will focus mostly on the Respect for Privacy side. Here, we provide an overview of the main attacks that can threaten individual privacy, explain the difference between pseudonymization and actual anonymization, and describe the main family of privacy models.
- [Transparency](./Transparency/Transparency.md). In this part of the Handbook, we will first provide the distinction between a transparent model and an explainable one (indeed, in the ML context, a commonly study problem is related to the Explainable AI). In this section, we provide an overview of the main properties that an explanation should have and of the several methods to provide multi-modal explanations; moreover, our focus will also be on overcoming the need to explain the opaque model and, instead, move toward the use of transparent models.
- [Accountability](./Accountability/Accountability_and_Reproducibility.md). Here, we analyze the two souls of this topic, the two interrelated concepts of Accountability and Reproducibility: the former term is more related to responsibility, blameworthiness, liability, and preventing misuse, while the latter term is more related to measures, quality standards, and procedures to model the development of learning methods for AI.
- [Diversity, Non-Discrimination, and Fairness](./Diversity_Non-Discrimination_and_Fairness/Diversity_Non-Discrimination_and_Fairness.md). In this chapter, we will start recalling what the grounds of discrimination are, how we can define a bias or segregation; then, we will make a step in determining what fair machine learning could be, what are the metrics we can adopt to measure (un)fairness, and, more generally, how we could move towards Justice by Design systems.
- [Societal and Environmental Wellbeing](./Societal_and_Environmental_Wellbeing/Societal_and_Environmental_Wellbeing.md). The last chapter of the Handbook is focus of one of the newest challenge that our society is facing. In particular, our focus is on environmental wellbeing (aka sustainability) and on providing solutions to optimize both the resources used in AI systems and the computation itself.

As one can see, we mapped one of the seven requirements for Trustworthy AI, as defined by the High-Level Expert Group on AI {cite}`HLEG`, in a chapter of this Handbook. However, there are some differences in emphasis, as the <a href="https://tailor-network.eu" target=_blank>TAILOR project</a> is more focused on specific aspects, e.g., more on privacy than on data governance, more on the sustainability of AI than on societal wellbeing, and more on [post-hoc explanations](./Transparency/blackbox_transparent.md) than on [transparency](./Transparency/Transparency.md).

Finally, we report a final chapter, where you can find an [Index](./main/AnalyticalIndex.md) that lists all entries in alphabetical order. In each term, you can find a reference to a short definition of the entry and where it is used within the Handbook, with a link to go more in-depth with the definition. Potential synonyms have their own entries in this index.

## Related work

With respect to other encyclopedias or handbooks, the TAILOR HTAI is characterized by: 
- A choice of terms directly related to the experience of the [TAILOR](./main/TAILOR.md) consortium; i.e., all the entries were chosen by the TAILOR partners in a bottom-up way and inserted in the Handbook if they are relevant to the research pursued in the project development.
- The fact that, given the living-document nature of the Handbook and the attitude of oneness of the TAILOR network of excellence, we are ready to correct, integrate, and update information, and receptive to (even external) suggestions.
- The wiki structure will permit to take advantage of hyperlinks to jump directly to correlated terms.
- Unlike other encyclopedias (such as {cite}`ElgarEncyclopedia,encyclopediaAI`), it is freely accessible.
- We are not focused on general and omni-comprehensive machine learning or artificial intelligence resources (for this, other work {cite}`EncyclopediaML` can be more exhaustive), or very specific ethical aspects on very specific topics (e.g., privacy in mobile data {cite}`Handbook_mobile_data_privacy`), but, starting from the work done in the High-Level Expert Group report {cite}`HLEG`, which is one of the leading work in the EU, we specifically focus on the operative aspects of trustworthy AI.



<!--The plan will be to integrate it into the TAILOR web page and to make a Wikipedia entry (by v2 of the handbook). A final paper book is also planned by then.-->

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Francesca Pratesi and Umberto Straccia.

> This research was partially supported by TAILOR, a project funded by EU Horizon 2020 research and innovation programme under GA No 952215
