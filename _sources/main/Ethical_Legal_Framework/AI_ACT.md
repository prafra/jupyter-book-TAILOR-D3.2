# The EU AI Act

## In Brief
The Artificial Intelligence Act (or AI Act, AI ACT, AIA) is a European Regulation aiming at regulating artificial intelligence (AI) to ensure better conditions for the development and use of this innovative technology.

## More in detail
On March 13, 2024, the European Parliament adopted the *Artificial Intelligence Act (AI Act)* {cite}`AIACT`. It is considered to be the world’s first comprehensive legal framework for AI {cite}`EU_first_law`. It provides for EU-wide rules on data quality, transparency, human oversight and accountability.
The first version of the text proposed in 2021 was significantly amended to take into account the technological progress in the field (for example, the development of general-purpose AI) and the instances of institutions, advocates, and associations.
One of the most significant changes follows the calls of several organizations and scholars {cite}`LetterPrivacyHub, LetterCivilForum` and introduces the obligation for some deployers - bodies governed by public law, or private operators providing public services, or operators deploying high-risk systems that evaluate the creditworthiness of natural persons, establish their credit score, or use AI for risk assessment and pricing in the case of life and health insurance - to carry out a *Fundamental Rights Impact Assessment ("FRIA")*. The FRIA is required when the aforementioned deployers put into use certain high-risk systems, as listed in Annex III of the EU AI Act {cite}`AIACT`, with the exception of the systems used for critical infrastructures. Article 27 identifies the cases in which the FRIA is mandatory and the content of the assessment, but it does not provide indications on parameters and criteria for the implementation of adequate measurement paths.

It is worth noting the scope of the AI Act, defined in <a href="https://artificialintelligenceact.eu/article/2/" target=_blank>Article 2 of the AI Act</a>:
```{admonition} Scope of the AI Act
<!--<a href="https://artificialintelligenceact.eu/article/2/" target=_blank>Article 2 of the AI Act</a> defines the scope of the Regulation:-->

1. This Regulation applies to:

(a) providers placing on the market or putting into service AI systems or placing on the market general-purpose AI models in the Union, irrespective of whether those providers are established or located within the Union or in a third country;

(b) deployers of AI systems that have their place of establishment or are located within the Union;

(c) providers and deployers of AI systems that have their place of establishment or are located in a third country, where the output produced by the AI system is used in the Union;

(d) importers and distributors of AI systems;

(e) product manufacturers placing on the market or putting into service an AI system together with their product and under their own name or trademark;

(f) authorised representatives of providers, which are not established in the Union;

(g) affected persons that are located in the Union.

2. For AI systems classified as high-risk AI systems in accordance with Article 6(1) related to products covered by the Union harmonisation legislation listed in Section B of Annex I, only Article 6(1), Articles 102 to 109 and Article 112 apply. Article 57 applies only in so far as the requirements for high-risk AI systems under this Regulation have been integrated in that Union harmonisation legislation.

3. This Regulation does not apply to areas outside the scope of Union law, and shall not, in any event, affect the competences of the Member States concerning national security, regardless of the type of entity entrusted by the Member States with carrying out tasks in relation to those competences. This Regulation does not apply to AI systems where and in so far they are placed on the market, put into service, or used with or without modification exclusively for military, defence or national security purposes, regardless of the type of entity carrying out those activities. This Regulation does not apply to AI systems which are not placed on the market or put into service in the Union, where the output is used in the Union exclusively for military, defence or national security purposes, regardless of the type of entity carrying out those activities.

4. This Regulation applies neither to public authorities in a third country nor to international organisations falling within the scope of this Regulation pursuant to paragraph 1, where those authorities or organisations use AI systems in the framework of international cooperation or agreements for law enforcement and judicial cooperation with the Union or with one or more Member States, provided that such a third country or international organisation provides adequate safeguards with respect to the protection of fundamental rights and freedoms of individuals.

5. This Regulation shall not affect the application of the provisions on the liability of providers of intermediary services as set out in Chapter II of Regulation (EU) 2022/2065.

6. This Regulation does not apply to AI systems or AI models, including their output, specifically developed and put into service for the sole purpose of scientific research and development.

7. Union law on the protection of personal data, privacy and the confidentiality of communications applies to personal data processed in connection with the rights and obligations laid down in this Regulation. This Regulation shall not affect Regulation
(EU) 2016/679 or (EU) 2018/1725, or Directive 2002/58/EC or (EU) 2016/680, without prejudice to Article 10(5) and Article 59 of this Regulation.

8. This Regulation does not apply to any research, testing or development activity regarding AI systems or AI models prior to their being placed on the market or put into service. Such activities shall be conducted in accordance with applicable Union law. Testing in real world conditions shall not be covered by that exclusion.

9. This Regulation is without prejudice to the rules laid down by other Union legal acts related to consumer protection and product safety.

10. This Regulation does not apply to obligations of deployers who are natural persons using AI systems in the course of a purely personal non-professional activity.

11. This Regulation does not preclude the Union or Member States from maintaining or introducing laws, regulations or administrative provisions which are more favourable to workers in terms of protecting their rights in respect of the use of AI systems by employers, or from encouraging or allowing the application of collective agreements which are more favourable to workers.

12. This Regulation does not apply to AI systems released under free and open-source licences, unless they are placed on the market or put into service as high-risk AI systems or as an AI system that falls under Article 5 or 50.
```

### A risk-based approach
However, the final text maintains the risk-based approach proposed by the Commission in 2021, with different rules for AI systems depending on the level of risk they pose. The technologies belonging to the high-risk category (i.e., the one that is mainly in the scope of the EU AI Act) are not written in the law itself but are listed in specific annexes to make the general law more durable: indeed, the general principles should be the most durable, while the individual technology can be added to the appropriate annex if needed.


```{figure} ./aiact_risk_pyramid.jpeg
---
name: fig:aiact_risk_pyramid
width: 600px
align: center
---
The pyramid of AI systems based on their risk
```
A graphical representation of this classification is given in Figure {numref}`{number} <fig:aiact_risk_pyramid>`, while the four categories are summarized in the following {cite}`pyramid`:

- [Unacceptable Risk](./Prohibited_AI). The technologies that create an "unacceptable risk" are completely banned.
    
- [High-Risk](./High_Risk_AI). The "high-risk" category is heavily regulated, with significant requirements for the systems and obligations for the providers, importers, distributors, and deployers of these technologies.
    
- **Limited risk**. Limited risk refers to the risks associated with a lack of transparency in AI usage. The EU AI Act introduces specific transparency obligations to ensure that humans are informed when necessary, fostering trust. For instance, when using AI systems such as chatbots, humans should be made aware that they are interacting with a machine so they can take an informed decision to continue or step back. Providers will also have to ensure that AI-generated content is identifiable. Besides, AI-generated text published with the purpose to inform the public on matters of public interest must be labelled as artificially generated. This also applies to audio and video content constituting deep fakes.
    
- **Minimal or no risk**. The EU AI Act allows the free use of minimal-risk AI. This includes applications such as AI-enabled video games or spam filters. The vast majority of AI systems currently used in the EU fall into this category.


### The structure of the EU AI ACT

The EU AI Act is composed of 180 Recitals, 113 Articles organized in 13 Chapters, and 13 Annexes.
Here, the main structure of the AI Act is provided, chapter by chapter, to help in its consultancy.

- *Chapter I - General Provisions*. Four articles where the preliminary information (such as the scope of the Regulation) and the basic definitions (such as "AI system", "risk", "deployer", "provider", "making available on the market", and "putting into service") are given.

- *Chapter II - Prohibited AI Practices*. One article listing the AI practices that shall be prohibited. We reported this list [here](./Prohibited_AI).

- *Chapter III - High-risk AI Systems*. The main part of the Regulation, it is composed of forty-four articles divided into five Sections: 
	- Classification of AI systems as high-risk (Articles 6 and 7).
	- Requirements for high-risk AI systems (Articles 8-15).
	- Obligations of providers and deployers of high-risk AI systems and other parties (Articles 16-27).
	- Notifying authorities and notified bodies (Articles 28-39).
	- Standards, conformity assessment, certificates, and registration (Articles 40-49).
  We examine more in depth the high-risk systems [here](High_Risk_AI).

- *Chapter IV - Transparency Obligations for Providers and Deployers of Certain AI Systems*. This Chapter, composed of one article only, lists all the obligations that providers and deployers of limited risk AI systems have. Indeed, such AI systems must be designed and developed in such a way that the natural persons concerned are informed that they are interacting with an AI system (e.g., chatbots, or a clear disclosure that a content has been artificially generated). 

- *Chapter V - General-Purpose AI Models*. This Chapter, composed of 6 Articles, regulates General-purpose AI models, including large generative AI models, which might also be integrated into other AI systems.  A key point of this Chapter is the obligation of transparency to understand such models better and ensure that their providers respect copyright law when training their models. In addition, some of these models could pose systemic risks, because they are widely used or very capable (for now, the threshold is fixed to have a training measured in floating point operations -or FLOPS- greater than **$10^{25}$). **Providers of such models must assess and mitigate risks, report serious incidents, conduct state-of-the-art tests and model evaluations, ensure cybersecurity, and provide information on the energy consumption of their models.

- *Chapter VI - Measures in Support of Innovation*. This Chapter is composed of seven Articles and introduces the "regulatory sandboxes"", i.e., a mechanism established to foster innovation in AI, experimenting and testing in a controlled environment new products and services under a regulator’s supervision.

- *Chapter VII - Governance*. This Chapter is composed of seven Articles, dealing with the establishment of mechanisms that can help in facilitating the application of the EU AI Act, such as the European Artificial Intelligence Board Advisory forum and the Scientific panel of independent experts. Moreover, this Chapter advocates the designation of national competent authorities and single points of contact.

- *Chapter VIII - Eu Database For High-Risk AI Systems*. This Chapter is composed of one article, where the creation of a database for high-risk AI systems listed in Annex III, controlled by the EU Commission itself, where adequate technical and administrative support should be made available to providers, prospective providers and deployers. This database shall comply with the applicable accessibility requirements, e.g., being machine-readable and (unless the provider has decided to open the information to the public) accessible only to market surveillance authorities and the Commission.

- *Chapter IX - Post-Market Monitoring, Information Sharing and Market Surveillance*. This Chapter, composed of twenty-three Articles, regulates the monitoring and surveillance after an AI system is made available in the market. The Chapter mainly deals with high-risk systems and general-purpose AI models. It covers various topic such as the reporting of serious incidents, the supervision of testing in real world conditions by market surveillance authorities, the powers of national authorities protecting fundamental rights, and the possible remedies (e.g., the right to lodge a complaint with a market surveillance authority and the right to an [explanation of individual decision-making](../../Transparency/Transparency). 
<!-- right to explaination (Art 86)-->

- *Chapter X - Codes of Conduct and Guidelines*. This Chapter, composed of two Articles, describes the contents of codes of conduct for voluntary application of specific requirements, and the commitment of the Commission to publish suitable guidelines on the implementation of the EU AI Act.

- *Chapter XI - Delegation of Power and Committee Procedure*. This Chapter, composed of two Articles, illustrates the possibility of the exercise of the delegation, and advocates that the Commission shall be assisted by a specific committee.

- *Chapter XII - Penalties*. This Chapter, composed of three Articles, describes the fines and penalties, clarifying that the penalties shall be effective, dissuasive, and proportionate (especially for SMEs, they should take into account their economic viability).

- *Chapter XIII - Final Provisions*. This Chapter, composed of twelve Articles, mostly listing amendments to previous Regulations but also explaining what happens to (general-purpose) AI systems already placed on the market or put into service.

> This entry was re-adapted from the Artificial Intelligence Act by Francesca Pratesi and Umberto Straccia.


```{bibliography} ../../references.bib
:style: unsrt
:filter: docname in docnames
```


> This entry was re-adapted from the Ethics guidelines for Trustworthy AI of the High-Level Expert Group on Artificial Intelligence by Francesca Pratesi and Umberto Straccia.
