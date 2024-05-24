# Trustworthy AI
In the last years, several definition on what Trustworthy AI is are given by the scientific communities. Each definition can vary on the dimension where they focus more, but there is a general consensus in Europe to use as official definition the one given by the High Level Expert Group on AI in its Ethical Guidelines for Trustworthy AI {cite}`HLEG`.

Indeed, according to this document, Trustworthy AI has three components, which should be met throughout the system's entire life cycle. Indeed, it should be:

1. **lawful**, complying with all applicable laws and regulations; 
2. **ethical**, ensuring adherence to ethical principles and values; 
3. **robust**, both from a technical and social perspective since, even with good intentions, AI systems can cause unintentional harm. 

Each component in itself is necessary but not sufficient for the achievement of Trustworthy AI.  <!--Ideally, all three components work in harmony and overlap in their operation. If, in practice, tensions arise between these components, society should endeavour to align them.--><br>
We will provide some additional details on what it is intended for each of these three components.

### Lawful AI
AI systems do not operate in a lawless world. A number of legally binding rules at European, national, and international levels already apply or are relevant to the development, deployment, and use of AI systems today. 
Legal sources include, but are not limited to: EU primary law (the <a href="https://european-union.europa.eu/principles-countries-history/principles-and-values/founding-agreements\_en" target=_blank>Treaties of the European Union</a> and its <a href="https://www.europarl.europa.eu/charter/pdf/text\_en.pdf" target=_blank>Charter of Fundamental Rights</a>), EU secondary law (such as the <a href="https://gdpr-info.eu/" target=_blank>General Data Protection Regulation</a> {cite}`gdpr`, the <a href="https://single-market-economy.ec.europa.eu/single-market/goods/free-movement-sectors/liability-defective-products\_en" target=_blank>Product Liability Directive</a>, the <a href="https://digital-strategy.ec.europa.eu/en/policies/non-personal-data" target=_blank>Regulation on the Free Flow of Non-Personal Data</a>, <a href="https://commission.europa.eu/aid-development-cooperation-fundamental-rights/your-rights-eu/know-your-rights/equality/non-discrimination\_en" target=_blank>anti-discrimination Directives</a>, consumer law and <a href="https://osha.europa.eu/en/safety-and-health-legislation/european-directives" target=_blank>Safety and Health at Work Directives</a>, the <a href="https://www.un.org/en/about-us/universal-declaration-of-human-rights" target=_blank>UN Human Rights treaties</a> and the Council of Europe conventions (such as the <a href="https://www.coe.int/en/web/human-rights-convention/the-convention-in-1950" target=_blank>European Convention on Human Rights</a>), and numerous EU Member State laws. Besides horizontally applicable rules, various domain-specific rules exist that apply to particular AI applications (such as, for instance, the Medical Device Regulation in the healthcare sector).

The law provides both positive and negative obligations, which means that it should not only be interpreted with reference to what cannot be done, but also with reference to what should be done and what may be done. The law not only prohibits certain actions but also enables others. In this regard, it can be noted that the EU Charter contains articles on the ''freedom to conduct a business'' and the ''freedom of the arts and sciences'', alongside articles addressing areas that we are more familiar with when looking to ensure AI's trustworthiness, such as for instance data protection and non-discrimination.

### Ethical AI
Achieving Trustworthy AI requires not only compliance with the law, which is but one of its three components. Laws are not always up to speed with technological developments, can at times be out of step with ethical norms or may simply not be well suited to addressing certain issues. For AI systems to be trustworthy, they should hence also be ethical, ensuring alignment with ethical norms.
Regarding ethics, some philosophical currents (such as Floridi's work {cite}`Floridi`) have been discriminating between hard and soft ethics. 

**Hard ethics** is what we usually have in mind when discussing values, rights, duties, and responsibilities— or, more broadly, what is morally right or wrong, and what ought or ought not to be done—in the course of formulating new regulations or challenging existing ones. In short, hard ethics is what makes or shapes the law. %Thus, in the best scenario, lobbying in favour of some good legislation or to improve that which already exists can be a case of hard ethics. For example, hard ethics helped to dismantle apartheid in South Africa and supported the approval of legislation in Iceland that requires public and private businesses to prove that they offer equal pay to employees, irrespective of their gender (the gender pay gap continues to be a scandal in most countries).

**Soft ethics** covers the same normative ground as hard ethics, but it does so by considering what ought and ought not to be done over and above the existing regulation, not against it, or despite its scope, or to change it, or to by-pass it (e.g. in terms of self-regulation). In other words, soft ethics is post-compliance ethics: in this case, ''ought implies may''.

### Robust AI
Even if an ethical purpose is ensured, individuals and society must also be confident that AI systems will not cause any unintentional harm. Such systems should perform in a safe, secure and reliable manner, and safeguards should be foreseen to prevent any unintended adverse impacts. It is therefore important to ensure that AI systems are robust. This is needed both from a technical perspective (ensuring the system's technical robustness as appropriate in a given context, such as the application domain or life cycle phase), and from a social perspective (in due consideration of the context and environment in which the system operates).
<!--https://www.cohubicol.com/blog/robust-ai-and-robust-law-part-i-robust-ai/-->

## The European Legal Framework

In these pages, we focus on the European framework only, mostly relying on two main sources, which are described below and in the linked pages.

The first document, at least chronologically speaking, we refer to is the [Ethical Guidelines for Trustworthy AI](./Ethical_Legal_Framwework/HLEG) {cite}`HLEG`, which, as the name itself suggests is not a law or a legal obligation. Nevertheless, it is commonly recognized as the most relevant document in the field of Trustworthy AI.
Here, as we already mentioned, there are listed a definition of Trustworthy AI, the foundation of Trustworthy AI, the seven key requirements that AI systems should implement and meet throughout their entire life cycle, and a concrete assessment list to operationalize the requirements.

Then, the other fundamental source is the world's first comprehensive law on Artificial Intelligence (AI): the [EU AI Act](./Ethical_Legal_Framwework/AIACT.md) {cite}`AIACT`. The text provides a classification of AI systems using a [risk-based approach](./Ethical_Legal_Framework/AI_ACT:prova}; four levels of risk were identified, and different obligations are listed for the different categories of AI systems to be compliant with this law. 

## The TAILOR Handbook of Trustworthy AI
In order to provide a better understanding on Trustworthy AI, within the [TAILOR project](../TAILOR_project.md) we have been developing an [Handbook on Trustworthy AI](../TAILOR.md). Here, you can find an overview of all the ethical dimensions highlighted in the [Ethical Guidelines for Trustworthy AI](./Ethical_Legal_Framwework/HLEG) {cite}`HLEG` and a deeper analysis of concepts that are related to and are going to contribute to each dimension.

## Bibliography

```{bibliography} ../references.bib
:style: unsrt
:filter: docname in docnames
```

> This entry was re-adapted from the Ethics guidelines for Trustworthy AI of the High-Level Expert Group on Artificial Intelligence by Francesca Pratesi and Umberto Straccia.

