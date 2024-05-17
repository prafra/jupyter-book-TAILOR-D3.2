# Respect for Privacy

## In Brief

Respect for Privacy is an ethical aspect studied in the <a href="https://tailor-network.eu/" target=_blank>TAILOR project</a> for ensuring personal data protection that is at the core of the General
Data Protection Regulation (GDPR) {cite}`gdpr`. GDPR, in its <a href="https://gdpr-info.eu/art-5-gdpr/" target=_blank>Article 5</a>, promote *privacy by design* in the form of a certain number of general principles for ensuring *privacy as the default* in the whole chain of data processing for a given task. We outline the challenges and solutions for enforcing privacy by design approaches.

## Abstract 

When protecting personal data, we are faced to the dilemma of disclosing no sensitive data while learning useful information about a population.
One approach for solving this tension between privacy and utility is based on *data encryption* and consists in developping secure computation protocols able to learn models or to compute statistics on encrypted data. A lot of scientific literature {cite}`CastellucciaCMT09` {cite}`ToNP16` {cite}`MirvalBP21` {cite}`CGLY18` has been exploring this security-based approach depending on the target computational task.
Another approach consists in conducting data analysis tasks on datasets made anonymous by the application of some {doc}`./L1.privacy_mechanisms`.
according to some {doc}`./L1.privacy_model`. Anonymization must no be reduced to {doc}`./L2.pseudonymization` (see also {doc}`./L2.reidentification`), which is defined in GDPR <a href="https://gdpr-info.eu/art-4-gdpr/" target=_blank>Article 4</a> as "the processing
of personal data in such a way that the data cannot be attributed to a specific data subject without the use of additional information."
Anonymization, as defined in GDPR (see <a href="https://gdpr-info.eu/recitals/no-26/" target=_blank>Recital 26</a>), refers to a process that removes any possibility of identifying a person even with additional information. In the resulting anonymized data, the connection should be completely lost between data and the individuals. Based on such a definition, anonymization is very difficult to model formally and to verify algorithmically. We will briefly survey the main privacy models and their properties, as well as the main privacy mechanisms which can be applied for enforcing the corresponding privacy properties or for providing strong guarantees of robustness to attacks.

## Motivation and Background

Publishing datasets plays an essential role in open data research and in promoting transparency of government agencies. Unfortunately, the process of data publication can be highly risky as it may disclose individuals' sensitive information. Hence, an essential step before publishing datasets is to remove any uniquely identifiable information from them. This is called {doc}`./L2.pseudonymization` and consists in masking or replacing by pseudonyms values of properties that directly identify persons such as their name, address, postcode, telephone number, photograph or image, or some other unique personal characteristic.

{doc}`./L2.pseudonymization` is not sufficient however for preserving the privacy of users. Adversaries can re-identify individuals in datasets based on common attributes called quasi-identifiers or may have prior knowledge about the users. Such side information enables them to reveal sensitive information that can cause physical, financial, and reputational harms to people.

Therefore, it is crucial to assess carefully *privacy risks* before the publication of datasets. Detection of privacy breaches should come with [explanations](../Transparency/Transparency.md) that can then be used to guide the choice of the appropriate [anonymization mechanisms](./L1.privacy_mechanisms.md) to mitigate the detected privacy risks. *Anonymization* should provide provable guarantees for privacy properties induced by some {doc}`./L1.privacy_model`. {doc}`./L2.differential_privacy` and {doc}`./L2.k_anonymity` are the two main privacy models for which {doc}`./L1.privacy_mechanisms` have been designed. They enjoy different properties based on the type of perturbations or transfomations applied on the data to anonymize.

The strength of {doc}`./L2.pseudonymization` and anonymization techniques can be assessed by their robustness to [privacy attacks](./L1.attacks.md) that aim at re-identifying individuals in datasets based on common attributes called quasi-identifiers or on prior knowledge.

## Guidelines 

*EDBP* has published several guidelines. The EDPB <a href="https://ec.europa.eu/newsroom/article29/items/611236" target=_blank>Guidelines on Data Protection Impact Assessment</a>
focus on determining whether a processing operation is likely to result in a high risk to the data subject or not. It provides guidance on how to assess data protection risks and how to carry out a data protection risk assessment.

*Data minimisation* is a strong recommendation to limit the collection of personal information to what is directly relevant and necessary to accomplish a specified purpose, and to retain the data only for as long as is necessary to fulfil that purpose.

The most authoritative guideline on <a href="https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-42019-article-25-data-protection-design-and" target=_blank>data protection "by design and by default"</a> outlines the data subject's rights and freedoms and the data protection principles that are illustrated through examples of practical cases. It emphasizes the obligation for controllers to stay up to date on technological advances on handling data protection risks, and to implement and update the measures and safeguards taking into account the evolving technological landscape.

## Software Frameworks Supporting Dimension

There are some practical tools that help in enanching respect for privacy and awareness, in particular definining and mitigating potential privacy risks.
This is compliant with the <a href="https://gdpr-info.eu/art-35-gdpr/" target=_blank>Data Protection Impact Assessment</a> introduced in the GDPR.

Risks can be identified and addressed at an early stage by analyzing how the proposed uses of personal information and technology will work in practice. We should identify the privacy and related risks, evaluate the privacy solutions and integrate them into the project plan. <!-- missing citation: Information Commissioner’s Office. Conducting privacy impact assessments code
of practice, 2017. https://ico.org.uk/media/for-organisations/documents/1595/pia-code-of-practice.pdf -->

Currently, a lot of frameworks have implemented to manage this task. University of British Colombia provides a <a href="https://privacymatters.ubc.ca/privacy-impact-assessment" target=_blank>tool</a> for determining a project's privacy and security risk classification. <a href="https://trustarc.com/" target=_blank>TrustArc</a> offers a consulting service for analyzing personally identifiable information, looking at risk factors and assisting in the development of policies and training programs. Information Commissioner's Office provides a <a href="https://ico.org.uk/for-organisations/sme-web-hub/checklists/data-protection-self-assessment/" target=_blank>handy step by step guide</a> through the process of deciding whether to share personal data[^ICO1][^ICO2]. Also the US Department of Homeland Security implemented such <a href="https://www.dhs.gov/privacy-impact-assessments" target=_blank>decision tool</a>.

A (non-exhaustive) list of more practical tools includes:
* <a href="https://amnesia.openaire.eu/" target=_blank>Amnesia</a>, a tool for anonymize tabular data relying on {doc}`./L2.k_anonymity` paradigm;
* <a href="https://arx.deidentifier.org/anonymization-tool/" target=_blank>AXR</a>, a tool that incorporates different {doc}`./L1.privacy_model`;
* <a href="https://github.com/scikit-mobility/scikit-mobility" target=_blank>Scikit-mobility</a>, a Python library for mobility analysis that includes the computation of privacy risks in such setting, based on the work presented in {cite}`scikit-mobility` {cite}`prudence`.


[^ICO1]: https://ico.org.uk/for-organisations/sme-web-hub/checklists/data-protection-self-assessment/data-sharing-and-subject-access-checklist/
[^ICO2]: https://ico.org.uk/for-organisations/guide-to-data-protection/ico-codes-of-practice/data-sharing-a-code-of-practice/

## Taxonomic Organisation of Terms

The *Respect for Privacy* dimension mainly regards the Data Protection. The Assessment of Privacy Risks can be performed, and two diffent strategies are available two protect the data privacy. The first one regards the application of [Anonymization Mechanisms](./L1.privacy_mechanisms.md), such as {doc}`./L2.pseudonymization`, {doc}`./L2.k_anonymity`, or {doc}`./L2.differential_privacy`. The second strategy is Data Encryption, which is strictly related with the [Security Dimension](../Technical Robustness and Safety/Technical Robustness and Safety.md).
In Fig. {numref}`{number} <T3.5taxonomy35>`, one can find the taxonomy proposed here. In blue, there are highlighted the possible attacks related to the various strategies, i.e., {doc}`./L2.reidentification`, {doc}`./L2.membership`, and Security Attacks.

```{figure} ./TAILOR_fig_privacy_blue.png
---
name: T3.5taxonomy35
width: 800px
align: center
---
A possible taxonomy about solutions to the Respect for Privacy dimension.
```




## Main Keywords (TBA)

- {doc}`./L1.anonymization`: A data subject is considered anonymous if it is *reasonably* hard to attribute his personal data to him/her.
- {doc}`./L2.pseudonymization`: **Pseudonymisation** aims to substitute one or more identifiers that link(s) the identity of an individual to its data with a surrogate value, called **pseudonym** or **token**.
- {doc}`./L1.privacy_model`: There are essentially two families of models, based on different goals and mechanisms: anonymity by randomization (where the most recent paradigm is Differential Privacy) and anonymity by indistinguishability (whose most famous example is k-anonymity).
- {doc}`./L2.differential_privacy`: **Differential privacy** implies that adding or deleting a single record does not significantly affect the result of any analysis.
- {doc}`./L3.epsilon_DP`: **$\epsilon$-Differential Privacy** is the simpler form of {doc}`./L2.differential_privacy`, where $\epsilon$ represents the level of privacy guarantee.
- {doc}`./L3.epsilon_delta_DP`: A relaxed version of {doc}`./L2.differential_privacy`, named **($\epsilon$,$\delta$)-Differential Privacy**, allows a little privacy loss ($\delta$) due to a variation in the output distribution for the privacy mechanism.
- {doc}`./L2.perturbation_mechanisms`: Differential privacy guarantees can be provided by perturbation mechanisms aim at randomizing the output distributions of functions in order to provide privacy guarantees.
- {doc}`./L2.k_anonymity`: **k-anonimity** (and the whole family of **anonymity by indistinguishability** models) is based on comparison among individuals present in data, and it aims to make each individual so similar as to be indistinguishable from at least *k-1* others.
- {doc}`./L1.attacks`: There are a variety of attacks that involve data privacy. Some of them are very context-specific (for example, there exists attacks on partition-based algorithms, such as deFinetti Attack or Minimality Attack), while other are more general.
- {doc}`./L2.reidentification`: **Re-identification attack** aims to link a certain set of data related to an individual in a dataset (which does not contain direct identifiers) to a real identity, relying on additional information.

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Marie-Christine Rousset, Tristan Allard, and Francesca Pratesi.

