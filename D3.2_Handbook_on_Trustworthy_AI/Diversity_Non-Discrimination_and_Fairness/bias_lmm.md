# Bias and Fairness in LLMs

## In brief

Within the Natural Language Processing (NLP) field, bias manifests in several forms, possibly leading to harms and unfairness. We review here intrinsic, lantent bias; extrinsic harms, and data selection bias in Large Language Models (LLMs).

## More in detail

Large Language Models (LLMs) are ubiquitous in NLP and are often used as a base step for fine-tuning models on downstream tasks. 
The unparalleled ability of LLMs to generalize from vast corpora is affected by an inherent reinforcement of biases (see also the entry {doc}`./bias`). Since biases are communicated and embedded in language, they manifest in texts, both learnt and produced by LLMs.
As foundation models, they are often employed in human-centric scenarios where their outputs may have undesired effects on historically marginalized groups of people, including discriminatory consequences.

In {cite}'DBLP:journals/corr/Bommasani2021Opportunities, authors introduce the concepts of \textbf{intrinsic, latent biases}, i.e., "properties of the foundation model that can lead to harm in downstream systems", and **extrinsic harms**, i.e., "specific harms from the downstream applications that are created by adapting a foundation model". Representational bias pertains to the intrinsic harms and manifests itself as misrepresentation, under-representation, and over-representation. From the extrinsic level, harms manifest as the generation of abusive content, and marked performance disparities among different demographic groups.

These issues warn that LLMs concretely impact society, posing a severe risk and limitation to the well-being of under-represented minorities, ultimately amplifying pre-existing social stereotypes, possible marginalization, and explicit harms {cite}`suresh2019framework,dixon2018measuring`.
Current research has highlighted cases emblematic of harms arising from LLMs. 
For instance, studies have shown that word embeddings can encode and perpetuate gender bias by echoing and strengthening societal stereotypes {cite}`bolukbasi2016man, nissim-etal-2020-fair`.
These biases are not merely encoded within language models' representations but are also perpetuated to downstream tasks~\cite{blodgett-etal-2021-stereotyping,stanczak2021survey}, where they can manifest in an uneven treatment of different demographic groups.
For example, automatic translation systems have been found to reproduce damaging gender and racial biases, especially towards gendered pronoun languages {cite}`savoldi-etal-2021-gender`.
Similarly, gender bias can be propagated in coreference resolution if models are trained on biased text {cite}`DBLP:conf/naacl/ZhaoWYOC18`.
Moreover, it was found that human annotators have a tendency to label social media posts written in Afro-American English as hateful more often than other messages. This harmful pattern could potentially result in the development of a biased system that reproduces and amplifies these same discriminatory attitudes {cite}`sap-etal-2019-risk`.
Recent studies have also documented the anti-Muslim sentiment exhibited by GPT-3, which generated toxic and abusive text when interrogated with prompts containing references to Islam and Muslims {cite}`DBLP:conf/aies/AbidF021`.
Summarizing, sensitive axes targeted by biases in LLMs are gender, age, sexual orientation, physical appearance, disability, nationality, ethnicity and race, socioeconomic status, religion, culture and intersectional identities. It is crucial to acknowledge how biases directed towards certain groups are yet underexplored and unaddressed by the research community {cite}`DBLP:journals/jdiq/NavigliCR23`. 

Although biases manifest differently in the various NLP tasks, they can be assessed through formal fairness notions measuring through a score the LLM output w.r.t. a social group. Fairness is evaluated using a range of metrics {cite}`DBLP:conf/nips/HardtPNS16,DBLP:conf/innovations/DworkHPRZ12`, which often present conflicting perspectives {cite}`DBLP:conf/innovations/KleinbergMR17` (see also the entry {doc}`./fairness`). Moreover, defining fairness in the NLP context is challenging, and existing works are often inaccurate, inconsistent, and contradictory in formalizing bias {cite}`DBLP:conf/acl/BlodgettBDW20`.
Nonetheless, starting from carefully auditing models' output is mandatory to mitigate and avoid stigmatization and discrimination, given the sensitive contexts in which LLMs are deployed {cite}`nozza-etal-2022-pipelines`. 

*Data selection bias* is defined as mistakes originating from texts sampled, selected and preprocessed to train LLMs, or introduced within the subsequent fine-tuning stage. These systematic errors arise from (i) skewed composition and distribution of knowledge domain and textual genre, (ii) range of time of the data gathered, (iii) demographic groups that create (and therefore represent) the data vs the affected application stakeholders, (iv) focusing mainly on high-resources languages (cultures) amplifying the gap w.r.t. low-resource languages (cultures), feeding a vicious feedback loop {cite}`DBLP:journals/jdiq/NavigliCR23`.
To address this issue, several strategies are suggested, e.g.,~starting from a sound conceptualization step, that should guide the choice of the most appropriate assessment measures and mitigation strategies that, among others, could consist of leveraging smaller, more curated datasets, together with enhancing the diversity of the cultures and languages to which the model has been exposed {cite}`DBLP:journals/jdiq/NavigliCR23`.

Investigating the other steps of the LLM life-cycle, potential entry points for bias injection are the model itself (e.g., equal treatment of different social groups when computing the loss), the evaluation step (e.g., leveraging on aggregate measures) and the deployment phase (e.g., unintended uses of the model) {cite}`DBLP:journals/corr/Gallegos23`.
Tracing back the source of these biases is extremely challenging, and attempts to mitigate them are often not successful nor effective. Indeed, in-depth data training investigation and counteracting bias by design are not doable in practice due to the huge data quantities, unfeasible to fully verify and assess, and the resources needed to develop LLMs from scratch. A recommended direction consists of collectively designing new, more accurate, holistic evaluation benchmarks, encompassing and testing different ethical desiderata {cite}`DBLP:journals/jdiq/NavigliCR23`.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was partially readapted from~\cite{DBLP:journals/corr/Marchiori23, DBLP:journals/corr/Setzu24} by Marta Marchiori Manerba}


