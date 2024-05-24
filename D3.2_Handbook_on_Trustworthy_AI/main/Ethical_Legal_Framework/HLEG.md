# Ethics Guidelines for Trustworthy AI by High-Level Expert Group on Artificial Intelligence

<!--

point the link
[many different interpretations of fairness](../../Diversity_Non-Discrimination_and_Fairness/Diversity_Non-Discrimination_and_Fairness), possibly at the point "Quantitative definitions have been introduced in philosophy, economics, and machine learning in the last 50 years"}

+
\link{``black box''}\footnote{XAI, possibly to 'the Open the Black-Box problem' section}

-->


On 8 April 2019, the High-Level Expert Group on AI presented the *''Ethics Guidelines for Trustworthy Artificial Intelligence''* {cite}`HLEG`, an influential document that set the stage for Trustworthy AI.

## In brief
The guidance in this document is provided in three chapters, from the most abstract in Chapter I to the most concrete in Chapter III:

- *Chapter I – Foundations of Trustworthy AI*: sets out the foundations of Trustworthy AI by laying out its fundamental-rights based approach. It identifies and describes the ethical principles that must be adhered to in order to ensure ethical and robust AI.
- *Chapter II – Realising Trustworthy AI*: translates these ethical principles into seven key requirements that AI systems should implement and meet throughout their entire life cycle. In addition, it offers both technical and non-technical methods that can be used for their implementation.
- *Chapter III – Assessing Trustworthy*: sets out a concrete and non-exhaustive Trustworthy AI assessment list to operationalise the requirements of Chapter II, offering AI practitioners practical guidance. This assessment should be tailored to the particular system's application.


According to these guidelines, **Trustworthy AI has three components**, which should be met throughout the system's entire life cycle. Indeed, it should be:
1. **lawful**, complying with all applicable laws and regulations; 
2. **ethical**, ensuring adherence to ethical principles and values; 
3. **robust**, both from a technical and social perspective since, even with good intentions, AI systems can cause unintentional harm. 


Each component in itself is necessary but not sufficient for the achievement of Trustworthy AI.  Ideally, all three components work in harmony and overlap in their operation. If, in practice, tensions arise between these components, society should endeavor to align them.
%We will provide some additional details on what it is intended for each of these three components.

## More in detail

In Figure {numref}`{number} <fig:hleg>`, we reported the main outcomes of the Guidelines.
First, the three pillars of Trustworthy AI are introduced. Then, in Chapter I the four ethical principles are described.
Thirdly, the seven key requirements are listed in Chapter II.
Finally, Chapter III offers a more practical way to assess Trustworthy AI.
We will briefly examine all these concepts in the following.


```{figure} ./hleg.png
---
name: fig:hleg
width: 600px
align: center
---
The Guidelines as a framework for Trustworthy AI {cite}`hleg`.
```

### The three pillars

As one can see, the three pillars (described in the document's introduction) of Trustworthy AI are that an AI system must be lawful, ethical, and robust.
We will provide some additional details on what is intended for each of these three components.

**Lawful AI.**
AI systems do not operate in a lawless world. A number of legally binding rules at European, national, and international levels already apply or are relevant to the development, deployment, and use of AI systems today. 
<!-- copied from TAI entry -->
Legal sources include, but are not limited to: EU primary law (the <a href="https://european-union.europa.eu/principles-countries-history/principles-and-values/founding-agreements\_en" target=_blank>Treaties of the European Union</a> and its <a href="https://www.europarl.europa.eu/charter/pdf/text\_en.pdf" target=_blank>Charter of Fundamental Rights</a>), EU secondary law (such as the <a href="https://gdpr-info.eu/" target=_blank>General Data Protection Regulation (GDPR)</a> {cite}`gdpr`, the <a href="https://single-market-economy.ec.europa.eu/single-market/goods/free-movement-sectors/liability-defective-products\_en" target=_blank>Product Liability Directive</a>, the <a href="https://digital-strategy.ec.europa.eu/en/policies/non-personal-data" target=_blank>Regulation on the Free Flow of Non-Personal Data</a>, <a href="https://commission.europa.eu/aid-development-cooperation-fundamental-rights/your-rights-eu/know-your-rights/equality/non-discrimination\_en" target=_blank>anti-discrimination Directives</a>, consumer law and <a href="https://osha.europa.eu/en/safety-and-health-legislation/european-directives" target=_blank>Safety and Health at Work Directives</a>, the <a href="https://www.un.org/en/about-us/universal-declaration-of-human-rights" target=_blank>UN Human Rights treaties</a> and the Council of Europe conventions (such as the <a href="https://www.coe.int/en/web/human-rights-convention/the-convention-in-1950" target=_blank>European Convention on Human Rights</a>), and numerous EU Member State laws. Besides horizontally applicable rules, various domain-specific rules exist that apply to particular AI applications (such as, for instance, the Medical Device Regulation in the healthcare sector).
<!-- end paragraph -->

The law provides both positive and negative obligations, which means that it should not only be interpreted with reference to what cannot be done but also concerning what should be done and what may be done. The law not only prohibits certain actions but also enables others. In this regard, it can be noted that the EU Charter contains articles on the 'freedom to conduct a business' and the 'freedom of the arts and sciences', alongside articles addressing areas that we are more familiar with when looking to ensure AI's trustworthiness, such as data protection and non-discrimination.

The Guidelines do not explicitly address the first component of Trustworthy AI (lawful AI) since they proceed on the assumption that all legal rights and obligations that apply to the processes and activities involved in developing, deploying, and using AI systems remain mandatory and must be duly observed.

**Ethical AI.**
Achieving Trustworthy AI requires not only compliance with the law, which is only one of its three components. Laws are not always up to speed with technological developments, can at times be out of step with ethical norms or may simply not be well suited to addressing certain issues. For AI systems to be trustworthy, they should hence also be ethical, ensuring alignment with ethical norms.

**Robust AI.**
Even if an ethical purpose is ensured, individuals and society must also be confident that AI systems will not cause any unintentional harm. Such systems should perform in a safe, secure, and reliable manner. Moreover, safeguards should be foreseen to prevent any unintended adverse impacts. It is, therefore, important to ensure that AI systems are robust. This is needed both from a technical perspective (ensuring the system’s technical robustness as appropriate in a given context, such as the application domain or life cycle phase) and from a social perspective (in due consideration of the context and environment in which the system operates).
Ethical and robust AI are hence closely intertwined and complement each other. The principles put forward in Chapter I, and the requirements derived from these principles in Chapter II, address both components.

### The four ethical principles
AI systems should improve individual and collective wellbeing. The four ethical principles, rooted in fundamental rights, must be respected in order to ensure that AI systems are developed, deployed and used in a trustworthy manner. They are specified as ethical imperatives, such that AI practitioners should always strive to adhere to them.

These are the principles of:
1. **Respect for human autonomy**;
2. **Prevention of harm**;
3. **Fairness**; and
4. **Explicability**.


Many of these are, to a large extent, already reflected in existing legal requirements for which mandatory compliance is required and hence also fall within the scope of lawful AI (for example, in the <a href="https://gdpr-info.eu/" target=_blank>GDPR</a> or in the <a href="https://commission.europa.eu/law/law-topic/consumer-protection-law\_en" target=_blank>EU consumer protection regulations</a>), which is Trustworthy AI's first component. 

In the following, we are going to shortly detail those four principles.

**The principle of respect for human autonomy.**
Humans interacting with AI systems must be able to maintain full and effective self-determination over themselves and partake in the democratic process. AI systems should not unjustifiably subordinate, coerce, deceive, manipulate, condition or herd humans. Instead, they should be designed to augment, complement, and empower human cognitive, social, and cultural skills. The allocation of functions between humans and AI systems should follow human-centric design principles and leave meaningful opportunities for human choice. This means securing human oversight over work processes in AI systems.

**The principle of prevention of harm.**
AI systems should neither cause nor exacerbate harm or otherwise adversely affect human beings, where harms are intended to be both individual or collective, and can include intangible harm to social, cultural and political environment. This entails the protection of human dignity as well as mental and physical integrity. AI systems and the environments in which they operate must be safe and secure. They must be technically robust and it should be ensured that they are not open to malicious use. Vulnerable persons should receive greater attention and be included in the development, deployment, and use of AI systems. Particular attention must also be paid to situations where AI systems can cause or exacerbate adverse impacts due to asymmetries of power or information, such as between employers and employees, businesses and consumers, or governments and citizens. Preventing harm also entails consideration of the natural environment and all living beings.

**The principle of fairness.**
The development, deployment, and use of AI systems must be fair. There are, of course, [many different interpretations of fairness](../../Diversity_Non-Discrimination_and_Fairness/Diversity_Non-Discrimination_and_Fairness), but according to the Guidelines, this dimension implies a commitment to ensuring equal and just distribution of both benefits and costs and ensuring that individuals and groups are free from unfair bias, discrimination, and stigmatization Equal opportunity in terms of access to education, goods, services and technology should also be fostered. Additionally, fairness implies that AI practitioners should respect the principle of proportionality between means and ends, and consider carefully how to balance competing interests and objectives. <!--The procedural dimension of fairness entails the ability to contest and seek effective redress against decisions made by AI systems and by the humans operating them. In order to do so, the entity accountable for the decision must be identifiable, and the decision-making processes should be explicable.-->

**The principle of explicability.**
Explicability is crucial for building and maintaining users' trust in AI systems. This means that processes need to be transparent, the capabilities and purpose of AI systems openly communicated, and decisions – to the extent possible – explainable to those directly and indirectly affected. Without such information, a decision cannot be duly contested. An explanation as to why a model has generated a particular output or decision (and what combination of input factors contributed to that) is not always possible. These cases are referred to as [''black box''](../../Transparency/blackbox_transparent) algorithms and require special attention. In those circumstances, other explicability measures (e.g., [traceability](../../Accountability/Traceability), [auditability](../../Diversity_Non-Discrimination_and_Fairness/auditing), and transparent communication on system capabilities) may be required, provided that the system as a whole respects fundamental rights. <!--The degree to which explicability is needed is highly dependent on the context and the severity of the consequences if that output is erroneous or otherwise inaccurate.-->

###The seven key requirements

The principles outlined before must be translated into concrete requirements to achieve Trustworthy AI. These requirements are applicable to different stakeholders partaking in AI systems’ life cycle: developers, deployers, and end-users, as well as the broader society. By developers, we refer to those who research, design and/or develop AI systems. By deployers, we refer to public or private organizations that use AI systems within their business processes and offer products and services to others. End-users are those engaging with the AI system, directly or indirectly. Finally, the broader society encompasses all others that are directly or indirectly affected by AI systems.

Different groups of stakeholders have different roles to play in ensuring that the requirements are met:

- developers should implement and apply the requirements to design and development processes;
- deployers should ensure that the systems they use and the products and services they offer meet the requirements;
- end-users and the broader society should be informed about these requirements and able to request that they are upheld.


The Guidelines identified a list of seven requirements (see also Figure {numref}`{number} <fig:TAIrequiremens>`), which will be analyzed more in deep in the respective chapters of this Handbook.
- [Human agency and oversight](../../Human_Agency_and_Oversight/Human_Agency_and_Oversight). Including fundamental rights, human agency, and human oversight.
- [Technical robustness and safety](../../Technical_Robustness_and_Safety/Technical_Robustness_and_Safety). Including resilience to attack and security, fall back plan and general safety, accuracy, reliability and reproducibility.
- [Privacy and data governance](../../Privacy_and_Data_Governance/Privacy_and_Data_Governance). Including respect for privacy, quality and integrity of data, and access to data.
- [Transparency](../../Transparency/Transparency). Including traceability, explainability and communication.
- [Diversity, non-discrimination and fairness](../../Diversity_Non-Discrimination_and_Fairness/Diversity_Non-Discrimination_and_Fairness) Including the avoidance of unfair bias, accessibility and universal design, and stakeholder participation.
- [Societal and environmental wellbeing](../../Societal_and_Environmental_Wellbeing/Societal_and_Environmental_Wellbeing). Including sustainability and environmental friendliness, social impact, society and democracy.
- [Accountability](../../Accountability/Accountability_and_Reproducibility). Including auditability, minimization and reporting of negative impact, trade-offs, and redress.


```{figure} ./TAIrequiremens.png
---
name: fig:TAIrequiremens
width: 600px
align: center
---
Interrelationship of the seven requirements: all are of equal importance, support each other, and should be implemented and evaluated throughout the AI system's lifecycle {cite}`hleg`.
```


### Operationalise the key requirements
Finally, Chapter III offers a more practical way to assess Trustworthy AI. In particular, the Guidelines proposed a (non-exhaustive) Trustworthy AI assessment list, based on the key requirements listed before. This list particularly applies to AI systems that directly interact with users, and is primarily addressed to developers and deployers of AI systems (whether self-developed or acquired from third parties). It is further developed in the <a href="https://futurium.ec.europa.eu/en/european-ai-alliance/pages/welcome-altai-portal" target=_blank>Assessment List for Trustworthy Artificial Intelligence (ALTAI) tool</a>. 
In addition, this chapter offers a general recommendation on how to implement the assessment list for Trustworthy AI through a governance structure embracing both operational and management levels.

```{bibliography} ../../references.bib
:style: unsrt
:filter: docname in docnames
```


> This entry was re-adapted from the Ethics guidelines for Trustworthy AI of the High-Level Expert Group on Artificial Intelligence by Francesca Pratesi and Umberto Straccia.
