# The TAILOR Handbook of Trustworthy AI

**An encyclopedia of the major scientific and technical terms related to Trustworthy Artificial Intelligence**

<!--**TAILOR: Foundations of Trustworthy AI – Integrating Reasoning, Learning and Optimization**

Add an introduction to the first page.
Add an Executive summary to the first page. This should be stand-alone, so that we can use it in formal reporting, for websites, social media etc.
-->

This book (to be consolidated in the second phase of the project) represents the first period deliverable of the TAILOR project, providing an encyclopedia of the major terms related to trustworthiness.

## About the TAILOR Handbook

This is a working document for the Version 1 of the *D3.3 Handbook on Trustworthy AI*, the TAILOR WP3 Handbook on Trustworthy AI. This
is a <a href="https://tailor-network.eu" target=_blank>TAILOR</a> project deliverable with two versions: Version 1 (M22) and Version 2 (M46).

The Handbook on Trustworthy AI assumes an encyclopedia-like structure and is presented in the form of a publically accessible WIKI. 
To do so, the Jupiter Book framework has been used.
In the long term, the Handbook is meant to become a point of reference for resources (key concepts, tools, documentation, tutorials, teaching material, etc.) related to Trustworthy AI.

Here, you can find information about the topics of each of the task of WP3, summarizing one of the aspects of Trustworthy AI; the order of the chapters that are in this Handbook simply reflects the order of the task in the workpackage. 
In particolar, in this Encyclopedia you can find definition related to:
- {doc}`../T3.1/T3.1`. In this part of the Handbook, we will provide an overview of the main properties that an explanation should have and of the several methods to provide multimodal explanations; moreover, our focus will be also on overcome the need of expaining opaque model and, instead, move towards the use of transparent models. 
- {doc}`../T3.2/T3.2`. In this section of the Encyclopedia, we will analyze the challenges in developing AI systems that are safe, reliable, and robust; we will also provide a way to evaluate this aspects in practice, and we will promote the dynamic evaluation in managing risk during the normal use of AI systems.
- {doc}`../T3.3/T3.3`. In this chapter, we will start recalling what the grounds of discrimination are, how we can define a bias or segregation; then, we will make a step in defining what fair machine learning could be, and what are the metrics we can adopt to measure (un)fairness.
- {doc}`../T3.4/L1.Accountability_and_Reproducibility`. Here, we analyze the two souls of this topic, i.e., the two interrelated concepts of {doc}`../T3.4/L2.Accountability` and {doc}`../T3.4/L2.Reproducibility`: the former term is more related to responsability, blameworthiness, liability, and prevent misuse, where the latter term is more related to measures, quality standards, and procedures to model the development of learning methods for AI.
- {doc}`../T3.5/T3.5`. This section will provide an overview of the main attack that can put at risk individual privacy, we will explain the difference between pseudonymization and actual anonymization, and we will describe the main family of privacy models.
- {doc}`../T3.6/T3.6`. The last chapter of the Handbook is focus of one of the newest challenge that our society is facing, in particular, our focus is to provide solutions for optimizing both the resources used in AI systems and the computation itself.

Finally, we report a final chapter, where you can find an {doc}`main/AnalyticaIndex`, which lists all entries in alphabetical order; in each term you can find a reference to a short definition of the entry and where it is used within the Handbook, with the link to go more in dept with the definition. Potential synonyms have their own entries in this index.

### Related work

Respect to other encyclopedias or handbooks, the TAILOR Handbook of Trustworthy AI is characterized by:
- A choice of terms which is directly related to the experience of the TAILOR consortium, i.e., all the entries were chosen by the TAILOR partners in a bottom-up way, and inserted in the Handbook if they are relevant with the research pursued in the project development.
- The fact that, given the living-document nature of the Handbook and the attitude of openess of the TAILOR network of excellence, we are ready to correct, integrate, and update information, and receptive to (even external) suggestions.
- The wiki structure will permit to take advantage of hyperlinks to jump directly to correlated terms.
- Unlike other encyclopedias (such as {cite}`ElgarEncyclopedia,encyclopediaAI`), it is freely acessible.
- We are not focused on general and omni-comprehensive machine learning or artificial intelligence resources (for this, other work {cite}`EncyclopediaML` can be more exhaustive), or very specific ethical aspects on very specific topic (e.g., privacy in mobile data {cite}`Handbook_mobile_data_privacy`), but, starting from the work done in the HLEG report, which is one of the leading work in the EU, we specificly focus on the operative aspects of trustworthy AI.


## Executive Summary

WP3 management and task leaders decided to transform one of the deliverable of the TAILOR EU project in a encyclopedia-like document and present it in the form of a publically accessible WIKI. To do so, the <a href="https://jupyterbook.org/en/stable/intro.html" target=_blank>Jupiter Book framework</a> has been used, which is an open source project, supported by an open community of contributors, many of whom come from the <a href="https://executablebooks.org/" target=_blank>Executable Books Community</a> and the <a href="https://jupyter.org/community" target=_blank>Jupyter community</a>.

The main goal of the Handbook of Trustworthy AI is to provide to non experts, especially researchers and students, an overview of the problem related to the developing of ethical and trustworty AI systems. In particular, we want to provide an overview of the main dimensions of trustworthiness, starting with a understandable explaination of the dimension itsleves, and then presenting the characterization of the problems (staring with a brief summary and the explaination of the importance of the dimension, presenting a taxonomy and some guidelines, if they are available and consolidated), summarizing what are the major challenges and solutions in the field, as well as what are the lastest research developments.

However, each entry will be correlated with a bibliography, allowing the reader to go more in depth with a specific topic. 

All the entries have a list of authors that have directly contributed to the writing (some of them are already external to the TAILOR consortium), while the complete list of contributors can be found [here](./authors.md).

<!--The plan will be to integrate it into the TAILOR web page and to make a Wikipedia entry (by v2 of the handbook). A final paper book is also planned by then.-->

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```


